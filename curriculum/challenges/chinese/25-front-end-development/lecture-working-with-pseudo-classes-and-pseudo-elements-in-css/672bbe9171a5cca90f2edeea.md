---
id: 672bbe9171a5cca90f2edeea
title: 元素用户操作伪类有哪些例子？
challengeType: 11
videoId: M80PYgBglmY
dashedName: what-are-examples-of-element-user-action-pseudo-classes
---

# --description--

观看视频或阅读文字稿，并回答下方问题。

# --transcript--

元素用户操作伪类有哪些例子？

用户反馈是网页设计中的关键元素。例如，当用户与网站上的元素交互时（如悬停在按钮上或点击链接），为用户提供视觉提示非常重要。这种反馈有助于用户理解交互元素的状态，比如指示链接是否已被访问。

CSS 中的用户操作伪类是一种特殊关键字，可以让你无需 JavaScript 或其他编程语言就能提供这种反馈。

这些伪类包括 `:hover`、`:active`、`:focus` 和 `:visited` 等。它们允许你根据用户的交互改变元素的外观，从而提升整体用户体验。

让我们来看看一些常见的用户操作伪类及其工作方式。

`:active` 伪类在元素被用户激活时应用样式。例如，当用户点击按钮或链接时，它会立即提供视觉反馈，让用户知道他们的操作已被识别。

```css
a:active {
  color: crimson;
}
```

`:hover` 伪类在用户用鼠标或其他指针设备悬停在元素上时触发。开发者常用它为按钮、链接或任何需要响应用户关注的元素创建视觉反馈。下面是一个用户悬停后会变化的按钮：

```html
<button class="btn">悬停我</button>
```

以下 CSS 会在用户悬停按钮时改变其颜色、背景色和鼠标指针：

```css
.btn:hover {
  background-color: darkgreen;
  color: white;
  cursor: pointer;
}
```

`:focus` 伪类在元素获得焦点时应用样式，通常通过键盘导航或点击表单输入获得。这不仅用于反馈，也是无障碍设计的重要部分。它确保依赖键盘的用户可以轻松识别当前交互的元素。

下面是一个表单中的输入框：

```html
<form>
  <input type="text" />
</form>
```

以下 CSS 会在用户点击输入框时为其添加深绿色实线边框和圆角：

```css
input:focus {
  outline: 2px solid darkgreen;
  border-radius: 4px;
}
```

`:visited` 伪类用于选中用户已访问过的链接。这有助于用户区分已访问和未访问的页面。下面是一个将已访问链接文本颜色改为青色的例子：

```css
a:visited {
  color: cyan;
}
```

`:checked` 伪类可以为被选中的表单元素（如复选框和单选按钮）设置样式。即使浏览器有默认样式，这个伪类也能让你自定义这些元素的外观，提升用户体验。

下面是一个常见的“同意条款”复选框：

```html
<form>
  同意 <input class="checkbox" type="checkbox" />
</form>
```

以下 CSS 会在复选框被选中时显示红色背景：

```css
.checkbox:checked {
  appearance: none;
  width: 12px;
  height: 12px;
  background-color: red;
}
```

在这个例子中，我们用 `appearance: none` 移除了浏览器默认样式。当用户勾选复选框时，它会显示为红色背景。

其他用户操作伪类还有：

- `:focus-within`：当元素本身或其任意后代获得焦点时应用样式。
- `:enabled`：选中当前可用的表单按钮或其他元素。
- `:disabled`：选中当前不可用的表单按钮或其他元素。
- `:target`：为 URL 片段（#号后部分）指向的元素应用样式。

# --questions--

## --text--

用户操作伪类允许你做什么？

## --answers--

它们可以实现动画和过渡效果。

### --feedback--

想一想如何仅用 CSS 与用户交互。

---

它们允许你动态修改 DOM 结构。

### --feedback--

想一想如何仅用 CSS 与用户交互。

---

它们让你无需依赖 JavaScript 就能为用户提供反馈。

---

它们让你为列表中的最后一个元素设置样式。

### --feedback--

想一想如何仅用 CSS 与用户交互。

## --video-solution--

3

## --text--

CSS 中的 `:checked` 伪类有什么作用？

## --answers--

它在元素被禁用时选中该元素。

### --feedback--

想一想表单如何处理用户选择。

---

它在元素被悬停时选中该元素。

### --feedback--

想一想表单如何处理用户选择。

---

它为被选中的复选框或单选按钮等元素设置样式。

---

它在元素获得焦点时设置样式。

### --feedback--

想一想表单如何处理用户选择。

## --video-solution--

3

## --text--

`:focus` 伪类的作用是什么？

## --answers--

它在元素被鼠标悬停时选中该元素。

### --feedback--

想一想用户如何用键盘操作表单。

---

它在元素获得焦点（通常通过键盘导航或点击）时应用样式。

---

它在表单提交后选中该元素。

### --feedback--

想一想用户如何用键盘操作表单。

---

它在元素被禁用时应用样式。

### --feedback--

想一想用户如何用键盘操作表单。

## --video-solution--

2

