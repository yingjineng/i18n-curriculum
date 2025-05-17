---
id: 67e2a513dbffdc8dcf1700af
title: 什么是 useOptimistic 钩子，它是如何工作的？
challengeType: 11
videoId: ZmjYqlrU4g0
dashedName: what-is-the-useoptimistic-hook-and-how-does-it-work
---

# --description--

观看视频或阅读文字稿并回答下列问题。

# --transcript--

什么是 `useOptimistic` 钩子，它是如何工作的？

React 的最新版本引入了服务器组件和服务器操作，将部分渲染和逻辑责任转移到服务器端。

随着这些更新，React 增加了一个新的钩子 `useOptimistic`，用于在等待异步操作在后台完成时保持 UI 的响应性。

虽然它通常用于从服务器获取数据，但并不仅限于此。这个钩子通常用于处理异步操作，确保在操作运行时 UI 保持流畅和可交互。

让我们来看看 `useOptimistic` 钩子是什么，以及它如何帮助实现流畅和响应迅速的 UI。

`useOptimistic` 钩子帮助管理 UI 中的“乐观更新”，这是一种根据操作的预期结果立即更新 UI 的策略，比如等待服务器响应时。

以下是 `useOptimistic` 钩子的基本语法：

```js
const [optimisticState, addOptimistic] = useOptimistic(actualState, updateFunction);
```

- `optimisticState` 是临时状态，会立即更新以提升用户体验。

- `addOptimistic` 是在实际状态改变前应用乐观更新的函数。

- `actualState` 是来自操作结果的真实状态值，比如从服务器获取的数据。

- `updateFunction` 是在调用时决定乐观状态如何更新的函数。

乍一看，`useOptimistic` 钩子似乎只是另一种处理 React 加载状态的方法。但它不仅如此。

加载状态控制在后台发生某些事情时，UI 是否显示加载动画、消息或其他指示器。

而 `useOptimistic` 钩子则是在你发起 API 请求之前，就根据预期结果即时更新 UI。这个钩子让你有机会显示加载指示或消息，优雅地处理潜在错误，并即时反馈，让 UI 更加流畅。

通过一些示例，你会更清楚地理解 `useOptimistic` 钩子的工作方式。

下面是一个模拟将任务保存到服务器的操作。它会延迟 1 秒后返回任务，类似真实 API 请求的情况：

```js
export async function saveTask(task) {
  await new Promise((res) => setTimeout(res, 1000));

  return task;
}
```

下面是通过导入和初始化 `useOptimistic` 钩子，并设置 `handleSubmit` 函数将输入发送到操作的代码：

```js
"use client";

import { useOptimistic } from "react";

export default function TaskList({ tasks, addTask }) {
  const [optimisticTasks, addOptimisticTask] = useOptimistic(
    tasks,
    (state, newTask) => [...state, { text: newTask, pending: true }]
  );

  async function handleSubmit(e) {
    e.preventDefault();
    const formData = new FormData(e.target);

    addOptimisticTask(formData.get("task"));

    addTask(formData);
    e.target.reset();
  }

  return <>{/* UI */}</>;
}
```

在这段代码中，`useOptimistic` 钩子维护了一个临时任务列表，当你添加新任务时会立即更新。

`(state, newTask) => [...state, { text: newTask, pending: true }]` 这一行确保新任务会以 pending 状态出现，即使服务器还未确认表单内容。

当表单提交时，`handleSubmit` 函数提取任务，并通过 `addOptimisticTask` 参数“乐观地”添加它。然后 `addTask` 作为 prop 发送任务到服务器。最后通过 `e.target.reset()` 重置表单。

下面是 `TaskList` 组件：

```js
"use client";
import { useOptimistic, startTransition } from "react";

export default function TaskList({ tasks, addTask }) {
  const [optimisticTasks, addOptimisticTask] = useOptimistic(
    tasks,
    (state, newTask) => [...state, { text: newTask, pending: true }]
  );

  async function handleSubmit(e) {
    e.preventDefault();
    const formData = new FormData(e.target);

    startTransition(() => {
      addOptimisticTask(formData.get("task"));
    });

    addTask(formData);
    e.target.reset();
  }

  return (
    <div className="max-w-md mx-auto p-4">
      <h3 className="text-xl font-medium mb-3">任务列表</h3>

      <ul className="space-y-2 mb-4">
        {optimisticTasks.map((task, index) => (
          <li key={index} className="p-2 border-b">
            {task.text}
            {task.pending && (
              <small className="ml-2 text-gray-500 text-sm">
                正在添加任务...
              </small>
            )}
          </li>
        ))}
      </ul>

      <form onSubmit={handleSubmit} className="flex gap-2">
        <input
          type="text"
          name="task"
          placeholder="输入任务..."
          className="flex-1 p-2 border"
        />
        <button type="submit" className="bg-gray-200 px-3 py-2 cursor-pointer">
          提交
        </button>
      </form>
    </div>
  );
}
```

这里，我们遍历 `optimisticTasks` 参数来展示任务。当 `task.pending` 为 `true` 时，会在任务旁边显示“正在添加任务...”，表明任务已被乐观地添加，尚未获得服务器确认。

下面是管理表单状态的 `Task` 组件。它调用 action 中的 `saveTask` 函数以添加任务，并在收到服务器返回的新任务后追加到列表：

```js
"use client";

import { useState } from "react";
import TaskList from "./TaskList";
import { saveTask } from "./actions";

export default function Tasks() {
  const [tasks, setTasks] = useState([]);

  async function addTask(formData) {
    const newTaskText = formData.get("task");

    const savedTask = await saveTask(newTaskText);
    setTasks((prev) => [...prev, { text: savedTask, pending: false }]);
  }

  return <TaskList tasks={tasks} addTask={addTask} />;
}
```

这样可以通过即时反馈实现流畅的 UI 更新，而无需等待响应。一旦任务保存完成，`pending` 属性会被移除，最终任务列表会相应更新。

在 UI 中，有两件事本不该发生。首先，“正在添加任务...”文本看不到，因为它出现和消失得太快。其次，添加任务后会出现错误。

我们需要做两件事来解决这些问题。

首先，需要从 React 导入 `startTransition` 并用它包裹 `addOptimisticTask(formData.get('task'))` 这一行：

```js
startTransition(() => {
  addOptimisticTask(formData.get("task"));
});
```

其次，需要让“正在添加任务...”文本在消失前可见一段时间。

为此，可以用 pending 状态修改 `addTask` 函数，并用 `setTimeout()` 模拟几秒延迟：

```js
async function addTask(formData) {
  const newTaskText = formData.get("task");

  // 添加带 pending 状态的乐观任务
  const tempTask = { id: Date.now(), text: newTaskText, pending: true };
  setTasks((prev) => [...prev, tempTask]);

  // 模拟 3 秒延迟后将任务标记为已完成
  setTimeout(async () => {
    const savedTask = await saveTask(newTaskText);

    setTasks((prev) =>
      prev.map((task) =>
        task.id === tempTask.id
          ? { ...task, text: savedTask, pending: false }
          : task
      )
    );
  }, 3000);
}
```

这样一来，一切就能正常工作了。

# --questions--

## --text--

`useOptimistic` 钩子的作用是什么？

## --answers--

它允许组件在渲染 UI 之前从服务器获取数据。

### --feedback--

该钩子确保 UI 在异步操作完成前反映预期的变化。

---

它通过在等待异步操作（如服务器响应）时立即更新 UI，帮助管理乐观更新。

---

它让 React 应用自动处理错误并在 API 请求失败时回滚。

### --feedback--

该钩子确保 UI 在异步操作完成前反映预期的变化。

---

它通过批量处理状态更新来提升性能。

### --feedback--

该钩子确保 UI 在异步操作完成前反映预期的变化。

## --video-solution--

2

## --text--

`useOptimistic` 钩子与加载状态有何不同？

## --answers--

加载状态在等待响应时显示 UI 反馈，而 `useOptimistic` 会基于预期结果立即更新 UI。

---

加载状态会立即修改服务器数据，而 `useOptimistic` 只更新客户端 UI。

### --feedback--

乐观更新会在服务器收到请求前就更新 UI。

---

`useOptimistic` 钩子用于处理错误，而加载状态只用于显示加载动画。

### --feedback--

乐观更新会在服务器收到请求前就更新 UI。

---

两者一样，但 `useOptimistic` 会为失败请求自动重试。

### --feedback--

乐观更新会在服务器收到请求前就更新 UI。

## --video-solution--

1

## --text--

在下面的 `useOptimistic` 钩子语法中，`addOptimistic` 的作用是什么？

```js
const [optimisticState, addOptimistic] = useOptimistic(actualState, updateFunction);
```

## --answers--

它会在实际状态改变前应用乐观更新，带来更流畅的用户体验。

---

它从服务器获取真实状态并相应更新 UI。

### --feedback--

该函数会在实际状态改变前更新 UI。

---

它在收到服务器响应后用临时状态替换实际状态。

### --feedback--

该函数会在实际状态改变前更新 UI。

---

它会在将乐观更新应用到 UI 前校验服务器数据。

### --feedback--

该函数会在实际状态改变前更新 UI。

## --video-solution--

1

