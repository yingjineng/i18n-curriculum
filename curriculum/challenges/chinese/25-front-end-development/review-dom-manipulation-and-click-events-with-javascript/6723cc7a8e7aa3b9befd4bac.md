---
id: 6723cc7a8e7aa3b9befd4bac
title: 使用 JavaScript 操作 DOM 和点击事件复习
challengeType: 24
dashedName: review-dom-manipulation-and-click-events-with-javascript
---

# --description--

## 操作 DOM 和 Web API

- **API**：API（应用程序编程接口）是一组规则和协议，使软件应用程序能够相互通信并高效交换数据。
- **Web API**：Web API 专为 Web 应用设计，通常分为两类：浏览器 API 和第三方 API。
- **浏览器 API**：这些 API 暴露浏览器中的数据，Web 开发者可以用 JavaScript 访问和操作这些数据。
- **第三方 API**：这些 API 并非浏览器默认内置，需要通过某种方式获取其代码。通常会有详细文档说明如何使用。例如 Google Maps API，可用于在网站上显示交互式地图。
- **DOM**：DOM（文档对象模型）是一种编程接口，允许你与 HTML 文档交互。通过 DOM，可以添加、修改或删除网页上的元素。DOM 树的根节点是 `html` 元素，是 HTML 文档所有内容的顶级容器，其他节点都是其后代。根节点下有其他层级节点，父节点包含其他元素，子节点被包含在其他元素中。
- **`navigator` 接口**：提供有关浏览器环境的信息，如用户代理字符串、平台和浏览器版本。用户代理字符串是标识浏览器和操作系统的文本字符串。
- **`window` 接口**：代表包含 DOM 文档的浏览器窗口，提供与浏览器窗口交互的方法和属性，如调整窗口大小、打开新窗口、跳转不同 URL 等。

## 使用 `querySelector()`、`querySelectorAll()` 和 `getElementById()` 方法

- **`getElementById()` 方法**：用于获取指定 `id` 的 HTML 元素对象。id 在每个 HTML 文档中必须唯一，因此该方法只会返回一个元素对象。

```html
<div id="container"></div>
```

```js
const container = document.getElementById("container");
```

- **`querySelector()` 方法**：用于获取文档中第一个匹配指定 CSS 选择器的元素。

```html
<section class="section"></section>
```

```js
const section = document.querySelector(".section");
```

- **`querySelectorAll()` 方法**：用于获取所有匹配指定 CSS 选择器的 DOM 元素列表。

```html
<ul class="ingredients">
  <li>糖</li>
  <li>牛奶</li>
  <li>鸡蛋</li>
</ul>
```

```js
const ingredients = document.querySelectorAll('ul.ingredients li');
```

## 使用 `innerText`、`innerHTML`、`createElement()` 和 `textContent` 属性/方法

- **`innerHTML` 属性**：用于设置或更新 HTML 标记的部分内容。

```html
<div id="container">
  <!-- 在这里添加新元素 -->
</div>
```

```js
const container = document.getElementById("container");
container.innerHTML = '<ul><li>奶酪</li><li>番茄</li></ul>';
```

- **`createElement` 方法**：用于创建一个 HTML 元素。

```js
const img = document.createElement("img");
```

- **`innerText`**：表示元素及其后代的可见文本内容。

```html
<div id="container">
  <p>Hello, World!</p>
  <p>我在学习 JavaScript</p>
</div>
```

```js
const container = document.getElementById("container");
console.log(container.innerText);
```

- **`textContent`**：返回元素及其所有后代的纯文本内容。

```html
<div id="container">
  <p>Hello, World!</p>
  <p>我在学习 JavaScript</p>
</div>
```

```js
const container = document.getElementById("container");
console.log(container.textContent);
```

## 使用 `appendChild()` 和 `removeChild()` 方法

- **`appendChild()` 方法**：用于将一个节点添加到指定父节点的子节点列表末尾。

```html
<ul id="desserts">
  <li>蛋糕</li>
  <li>派</li>
</ul>
```

```js
const dessertsList = document.getElementById("desserts");
const listItem = document.createElement("li");

listItem.textContent = "曲奇";
dessertsList.appendChild(listItem);
```

- **`removeChild()` 方法**：用于从 DOM 中移除一个节点。

```html
<section id="example-section">
  <h2>示例子标题</h2>
  <p>第一段</p>
  <p>第二段</p>
</section>
```

```js
const sectionEl = document.getElementById("example-section");
const lastParagraph = document.querySelector("#example-section p:last-of-type");

sectionEl.removeChild(lastParagraph);
```

## 使用 `setAttribute()` 方法

- **定义**：用于为指定元素设置属性。如果属性已存在，则更新其值，否则添加新属性。

```html
<p id="para">我是一个段落</p>
```

```js
const para = document.getElementById("para");
para.setAttribute("class", "my-class");
```

## 事件对象

- **定义**：`Event` 对象是在用户与网页交互时触发的有效载荷。这些交互可以是点击按钮、聚焦输入框，甚至摇动移动设备。所有 `Event` 对象都有 `type` 属性，表示触发事件的类型，如 keydown 或 click。这些值与传递给 `addEventListener()` 的事件类型一致，可以捕获并利用 `Event` 对象。

## `addEventListener()` 和 `removeEventListener()` 方法

- **`addEventListener` 方法**：用于监听事件。接收两个参数：要监听的事件类型和事件发生时调用的函数。常见事件有点击、输入、变化等。

```js
const btn = document.getElementById("btn");

btn.addEventListener("click", () => alert("你点击了按钮"));
```

- **`removeEventListener()` 方法**：用于移除之前通过 `addEventListener()` 添加的事件监听器。当你想停止监听某个事件时很有用。

```js
const bodyEl = document.querySelector("body");
const para = document.getElementById("para");
const btn = document.getElementById("btn");

let isBgColorGrey = true;

function toggleBgColor() {
  bodyEl.style.backgroundColor = isBgColorGrey ? "blue" : "grey";
  isBgColorGrey = !isBgColorGrey;
}

btn.addEventListener("click", toggleBgColor);

para.addEventListener("mouseover", () => {
  btn.removeEventListener("click", toggleBgColor);
});
```

- **内联事件处理器**：内联事件处理器是 HTML 元素上的特殊属性，用于在事件发生时执行 JavaScript 代码。现代 JavaScript 不推荐使用内联事件处理器，更推荐使用 `addEventListener` 方法。

```html
<button onclick="alert('Hello World!')">显示提示</button>
```

## Change 事件

- **定义**：change 事件是在用户修改某些输入元素的值时触发的。例如勾选复选框或单选按钮，或在日期选择器、下拉菜单中做出选择。

```html
<label>
  选择一种编程语言：
  <select class="language" name="language">
    <option value="">---请选择---</option>
    <option value="JavaScript">JavaScript</option>
    <option value="Python">Python</option>
    <option value="C++">C++</option>
  </select>
</label>

<p class="result"></p>
```

```js 
const selectEl = document.querySelector(".language");
const result = document.querySelector(".result");

selectEl.addEventListener("change", (e) => {
  result.textContent = `你喜欢用 ${e.target.value} 编程。`;
});
```

## 事件冒泡

- **定义**：事件冒泡（或传播）指事件在被触发后会“冒泡”到父对象的过程。
- **`stopPropagation()` 方法**：用于阻止事件的进一步传播。

## 事件委托

- **定义**：事件委托是指监听已经冒泡到父元素的事件，而不是直接在触发事件的元素上处理。

## DOMContentLoaded

- **定义**：`DOMContentLoaded` 事件在 HTML 文档加载和解析完成后触发。它不会等待外部样式表或图片加载完成，只会等待 HTML 加载完成。

## 操作 `style` 和 `classList`

- **`Element.style` 属性**：只读属性，表示元素的内联样式。可用于获取或设置元素的样式。

```js
const paraEl = document.getElementById("para");
paraEl.style.color = "red";
```

- **`Element.classList` 属性**：只读属性，可用于添加、移除或切换元素的类名。

```js
// 添加类
const paraEl = document.getElementById("para");
paraEl.classList.add("highlight");

// 移除类
paraEl.classList.remove("blue-background");

// 切换类
const menu = document.getElementById("menu");
const toggleBtn = document.getElementById("toggle-btn");

toggleBtn.addEventListener("click", () => menu.classList.toggle("show"));
```

## 使用 `setTimeout()` 和 `setInterval()` 方法

- **`setTimeout()` 方法**：用于延迟指定时间后执行某个操作。

```js
setTimeout(() => {
 console.log('3 秒后运行'); 
}, 3000);
```

- **`setInterval()` 方法**：用于每隔一段时间重复执行代码。若要停止 `setInterval()`，需使用 `clearInterval()` 方法。

```js
setInterval(() => {
 console.log('每 2 秒运行一次');
}, 2000);

// 使用 clearInterval 的示例
const intervalID = setInterval(() => {
 console.log('5 秒后停止');
}, 1000);

setTimeout(() => {
 clearInterval(intervalID);
}, 5000);
```

## `requestAnimationFrame()` 方法

- **定义**：该方法允许你在下次屏幕重绘前安排动画的下一步，从而实现流畅的视觉体验。屏幕重绘指浏览器刷新网页视觉显示的时刻，通常每秒约 60 次（60 帧）。

```js
function animate() {
 // 更新动画...
 // 例如移动元素、改变样式等
 update();
 // 请求下一帧
 requestAnimationFrame(animate);
}
```

## Web Animations API

- **定义**：Web Animations API 允许你直接在 JavaScript 中创建和控制动画。

```js
const square = document.querySelector('#square');

const animation = square.animate(
 [{ transform: 'translateX(0px)' }, { transform: 'translateX(100px)' }],
 {
   duration: 2000, // 动画持续 2 秒
   iterations: Infinity, // 无限循环
   direction: 'alternate', // 来回移动
   easing: 'ease-in-out', // 平滑缓动
 }
);
```

## Canvas API

- **定义**：Canvas API 是一个强大的工具，允许你在 JavaScript 文件中绘制和操作图形。首先需要在 HTML 中提供一个 `canvas` 元素，作为绘图表面。该 API 包含如 `HTMLCanvasElement`、`CanvasRenderingContext2D`、`CanvasGradient`、`CanvasPattern` 和 `TextMetrics` 等接口，可用于创建图形。

```html
<canvas id="my-canvas" width="400" height="400"></canvas>
```

```js
const canvas = document.getElementById('my-canvas');

// 获取 canvas 的绘图上下文
// "2d" 表示二维绘图
const ctx = canvas.getContext('2d');

// 设置背景色
ctx.fillStyle = 'crimson';

// 绘制矩形
ctx.fillRect(1, 1, 150, 100);
```

## 使用 JavaScript 打开和关闭对话框与模态框

- **模态框与对话框定义**：对话框用于向用户显示重要信息或操作。HTML 内置的 dialog 元素可以轻松创建对话框（包括模态和非模态）。模态对话框会强制用户先与其交互，才能访问页面其他部分；非模态对话框则不会阻止用户访问其他内容。
- **`showModal()` 方法**：用于打开模态对话框。

```html
<dialog id="my-modal">
   <p>这是一个模态对话框。</p>
</dialog>
<button id="open-modal">打开模态对话框</button>
```

```js
const dialog = document.getElementById('my-modal');
const openButton = document.getElementById('open-modal');

openButton.addEventListener('click', () => {
  dialog.showModal();
});
```

- **`close()` 方法**：用于关闭模态框。

```html
<dialog id="my-modal">
   <p>这是一个模态对话框。</p>
   <button id="close-modal">关闭模态框</button>
</dialog>
<button id="open-modal">打开模态对话框</button>
```

```js
const dialog = document.getElementById('my-modal');
const openButton = document.getElementById('open-modal');
const closeButton = document.getElementById('close-modal');

openButton.addEventListener('click', () => {
  dialog.show();
});

closeButton.addEventListener('click', () => {
  dialog.close();
});
```

# --assignment--

复习 JavaScript 的 DOM 操作和点击事件相关主题与概念。

