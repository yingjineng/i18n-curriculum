---
id: 66f1adcf97e3e4c1bd89ebf5
title: Web 性能测验
challengeType: 8
dashedName: quiz-web-performance
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

在 Web 开发中，真实性能和感知性能的关键区别是什么？

#### --distractors--

真实性能关注浏览器发起的 HTTP 请求数量，而感知性能基于 CSS 渲染速度。

---

真实性能只与加载时间有关，而感知性能与动画和加载指示器等视觉元素相关。

---

真实性能仅包括服务器端处理时间，而感知性能完全是客户端的。

#### --answer--

真实性能是内容实际加载的速度，而感知性能是用户认为页面加载有多快。

### --question--

#### --text--

哪个指标最能反映网页内容出现的速度？

#### --distractors--

可交互时间（TTI）

---

页面加载时间（PLT）

---

最后内容绘制（LCP）

#### --answer--

首次内容绘制（FCP）

### --question--

#### --text--

以下哪项不是减少页面加载时间的方法？

#### --distractors--

优化媒体资源。

---

利用浏览器缓存。

---

压缩和精简文件。

#### --answer--

只使用 JPEG 文件。

### --question--

#### --text--

什么是“可用时间”？

#### --distractors--

指用户请求页面到可以与页面表单交互的时间间隔。

---

指所有图片和动画可用并可操作所需的时间。

---

指所有 CSS 和 JavaScript 动画加载到屏幕上的时间。

#### --answer--

指用户请求页面到可以有意义地与页面交互的时间间隔。

### --question--

#### --text--

首次内容绘制（FCP）衡量的是什么？

#### --distractors--

页面上所有 JavaScript 文件的总加载时间。

---

用户可以与页面任何元素交互前的延迟。

---

所有样式表完全加载和应用所需的时间。

#### --answer--

首个文本或图片渲染所需的时间。

### --question--

#### --text--

以下哪项不是常用的性能测量工具？

#### --distractors--

Chrome DevTools

---

Lighthouse

---

WebPageTest

#### --answer--

WebMeasure

### --question--

#### --text--

性能 Web API 的作用是什么？

#### --distractors--

仅用于测量 CSS 动画的性能。

---

用于自动加快网页性能。

---

为用户提供详细的性能指标表格。

#### --answer--

允许开发者直接通过代码跟踪网页加载和响应的效率。

### --question--

#### --text--

哪种策略可以有效提升感知性能？

#### --distractors--

使用大图片提升整体视觉质量。

---

最后加载 CSS 样式以优先渲染内容。

---

预加载所有脚本以确保随时可用。

#### --answer--

在内容获取期间显示加载骨架屏。

### --question--

#### --text--

以下哪项指的是请求在浏览器和服务器之间传输所需的时间？

#### --distractors--

渲染

---

INP

---

CDN

#### --answer--

延迟（latency）

### --question--

#### --text--

优化 CSS 如何影响页面性能？

#### --distractors--

它可以防止浏览器执行不必要的 JavaScript。

---

它可以减少图片的整体文件大小。

---

它可以消除图片懒加载的需求。

#### --answer--

它可以加快 HTML 的解析速度。

### --question--

#### --text--

以下哪项显示主线程被繁重 JavaScript 任务阻塞的时长？

#### --distractors--

源顺序

---

跳出率

---

WebPageTest

#### --answer--

总阻塞时间（Total Blocking Time）

### --question--

#### --text--

测量“交互到下一次绘制”（INP）时，评估的是什么？

#### --distractors--

用户交互后，页面加载所有样式和图片所需的时间。

---

用户交互与浏览器能够注册下一个用户输入之间的延迟。

---

JavaScript 执行与浏览器刷新页面内容之间的间隔。

#### --answer--

用户交互到浏览器通过渲染下一帧做出响应的时间。

### --question--

#### --text--

以下哪个 API 能以毫秒级高精度时间戳测量站点各部分加载所需时间？

#### --distractors--

`performance.delay()`

---

`performance.previous()`

---

`performance.next()`

#### --answer--

`performance.now()`

### --question--

#### --text--

以下哪个 API 能为你分解页面加载的每个阶段，从 DNS 查询到 `DOMContentLoaded`？

#### --distractors--

Permit Timing API

---

Performance Text API

---

Perform Timing API

#### --answer--

Performance Timing API

### --question--

#### --text--

以下哪个监听性能事件，如布局偏移、长任务和用户交互？

#### --distractors--

```js
const observer = new PermitObserve((list) => {  
  list.getEntries().forEach((entry) => {  
    console.log(`Long task detected: ${entry.duration}ms`);  
  });  
});  

observer.observe({ type: "longtask", buffered: true });
```

---

```js
const observer = new PerformObserver((list) => {  
  list.getEntries().forEach((entry) => {  
    console.log(`Long task detected: ${entry.duration}ms`);  
  });  
});  

observer.observe({ type: "longtask", buffered: true });
```

---

```js
const observer = new PermitObserver((list) => {  
  list.getEntries().forEach((entry) => {  
    console.log(`Long task detected: ${entry.duration}ms`);  
  });  
});  

observer.observe({ type: "longtask", buffered: true });
```

#### --answer--

```js
const observer = new PerformanceObserver((list) => {  
  list.getEntries().forEach((entry) => {  
    console.log(`Long task detected: ${entry.duration}ms`);  
  });  
});  

observer.observe({ type: "longtask", buffered: true });
```

### --question--

#### --text--

图片懒加载如何提升页面性能？

#### --distractors--

确保所有图片立即加载以获得更好的用户体验。

---

通过减小图片文件大小来加快加载速度。

---

预加载图片以防止任何加载延迟。

#### --answer--

延迟加载非关键图片，直到它们进入视口。

### --question--

#### --text--

什么是代码分割（code splitting）？

#### --distractors--

将 React 代码拆分为只执行关键任务的模块。

---

将 HTML 代码拆分为只执行非关键任务的模块。

---

将 CSS 代码拆分为关键和非关键任务的模块。

#### --answer--

将 JavaScript 代码拆分为执行关键和非关键任务的模块。

### --question--

#### --text--

以下哪种方式是图片懒加载的正确写法？

#### --distractors--

```html
<img src="placeholder.jpg" lazy="loading">
```

---

```html
<img src="placeholder.jpg" load="lazy">
```

---

```html
<img src="placeholder.jpg" lazy="load">
```

#### --answer--

```html
<img src="placeholder.jpg" loading="lazy">
```

### --question--

#### --text--

以下哪项不是提升 INP 的方法？

#### --distractors--

通过拆分长 JavaScript 任务减少主线程工作量。

---

优化事件处理程序。

---

延迟或懒加载重型资源。

#### --answer--

只使用 PNG 和 JPEG 图片。

### --question--

#### --text--

为什么能效是 Web 性能的重要方面？

#### --distractors--

它提升了网页的整体视觉吸引力。

---

它最小化了网页使用的 JavaScript 数量。

---

它减少了所需的 CSS 文件数量并加快了 CSS 的运行速度。

#### --answer--

它减少了硬件负载，节省能源并提升可持续性。

