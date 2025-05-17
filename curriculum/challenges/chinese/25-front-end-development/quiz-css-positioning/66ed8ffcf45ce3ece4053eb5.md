---
id: 66ed8ffcf45ce3ece4053eb5
title: CSS 定位测验
challengeType: 8
dashedName: quiz-css-positioning
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

以下哪一项不是 `position` 属性的有效值？

#### --distractors--

`fixed`

---

`absolute`

---

`relative`

#### --answer--

`above`

### --question--

#### --text--

CSS 中 `float` 属性的主要作用是什么？

#### --distractors--

浮动用于将元素从页面的正常流中移除，并自动将其定位在网页的右上角。

---

浮动用于将元素从页面的正常流中移除，并将其定位在其容器的顶部。

---

浮动用于将元素从页面的正常流中移除，并自动将其定位在网页的右下角。

#### --answer--

浮动用于将元素从页面的正常流中移除，并将其定位在其容器的左侧或右侧。

### --question--

#### --text--

以下哪一个是让盒子元素向左浮动的示例？

#### --distractors--

```css
.box {
  left: float;
  margin-right: 15px;
  width: 50px;
  height: 50px;
  background-color: black;
}
```

---

```css
.box {
  position: float-left;
  margin-right: 15px;
  width: 50px;
  height: 50px;
  background-color: black;
}
```

---

```css
.box {
  float: left-side;
  margin-right: 15px;
  width: 50px;
  height: 50px;
  background-color: black;
}
```

#### --answer--

```css
.box {
  float: left;
  margin-right: 15px;
  width: 50px;
  height: 50px;
  background-color: black;
}
```

### --question--

#### --text--

`clear` 属性的作用是什么？

#### --distractors--

用于判断元素是否需要移动到页面底部。

---

用于判断元素是否需要从页面中完全清除。

---

用于判断元素是否需要固定在页面顶部。

#### --answer--

用于判断元素是否需要移动到浮动内容的下方。

### --question--

#### --text--

哪个 CSS 属性用于控制页面上重叠定位元素的垂直堆叠顺序？

#### --distractors--

`position`

---

`bg-green`

---

`float`

#### --answer--

`z-index`

### --question--

#### --text--

以下哪一项是相对定位的正确语法？

#### --distractors--

```css
.relative {
  position: relative-position;
  top: 30px;
  left: 30px;
}
```

---

```css
.relative {
  relative-position: relative;
  top: 30px;
  left: 30px;
}
```

---

```css
.relative {
  relative: position;
  top: 30px;
  left: 30px;
}
```

#### --answer--

```css
.relative {
  position: relative;
  top: 30px;
  left: 30px;
}
```

### --question--

#### --text--

要将元素固定在页面的某个位置，使其在滚动时不会移动，应使用哪个 CSS 属性？

#### --distractors--

`position: no-scroll;`

---

`position: relative;`

---

`display: block;`

#### --answer--

`position: fixed;`

### --question--

#### --text--

绝对定位会对元素产生什么影响？

#### --distractors--

绝对定位用于判断元素是否需要移动到浮动内容下方。

---

绝对定位用于将元素定位在正常文档流中。

---

绝对定位用于控制页面上重叠定位元素的垂直堆叠顺序。

#### --answer--

绝对定位可以将元素从正常文档流中移除，使其独立于其他元素进行定位。

### --question--

#### --text--

以下哪一项不是绝对定位时可以使用的属性？

#### --distractors--

`right`

---

`bottom`

---

`top`

#### --answer--

`side`

### --question--

#### --text--

相对定位和绝对定位的关键区别是什么？

#### --distractors--

绝对定位将元素设置为粘性位置，而相对定位会将元素从正常文档流中移除。

---

相对定位将元素设置为固定位置，而绝对定位会将元素从正常文档流中移除。

---

绝对定位在正常文档流中定位元素，而相对定位会将元素从正常文档流中移除。

#### --answer--

相对定位在正常文档流中定位元素，而绝对定位会将元素从正常文档流中移除。

### --question--

#### --text--

以下哪一个是将盒子定位在页面左上角的示例？

#### --distractors--

```css
.box {
  position: absolute;
  bottom: 0;
  left: 0;
  background-color: coral;
  width: 50px;
  height: 50px;
}
```

---

```css
.box {
  position: absolute;
  top: 0;
  right: 0;
  background-color: coral;
  width: 50px;
  height: 50px;
}
```

---

```css
.box {
  position: absolute;
  bottom: 0;
  right: 0;
  background-color: coral;
  width: 50px;
  height: 50px;
}
```

#### --answer--

```css
.box {
  position: absolute;
  top: 0;
  left: 0;
  background-color: coral;
  width: 50px;
  height: 50px;
}
```

### --question--

#### --text--

哪种定位方式可以让元素在滚动到某个点时才固定在指定位置？

#### --distractors--

浮动定位。

---

固定定位。

---

绝对定位。

#### --answer--

粘性定位（Sticky positioning）。

### --question--

#### --text--

以下哪一个是使用粘性定位的正确示例？

#### --distractors--

```css
.box {
  sticky: position;
  top: 30px;
  right: 30px;
  width: 50px;
  height: 50px;
  background-color: red;
}
```

---

```css
.box {
  position: sticky-fixed;
  top: 30px;
  right: 30px;
  width: 50px;
  height: 50px;
  background-color: red;
}
```

---

```css
.box {
  position: sticky-top;
  right: 30px;
  width: 50px;
  height: 50px;
  background-color: red;
}
```

#### --answer--

```css
.box {
  position: sticky;
  top: 30px;
  right: 30px;
  width: 50px;
  height: 50px;
  background-color: red;
}
```

### --question--

#### --text--

粘性定位和固定定位有什么区别？

#### --distractors--

粘性元素只能用于表格布局，而固定元素可用于任何类型的 CSS 布局。

---

粘性元素始终保持在同一位置，而固定元素会先固定到某个点，然后表现为相对元素。

---

固定元素会相对于其正常位置定位，而粘性元素只会在滚动到某个点时固定，然后表现为相对元素。

#### --answer--

固定元素始终保持在屏幕的同一位置，而粘性元素只会在滚动到某个点时固定，然后表现为相对元素。

### --question--

#### --text--

在使用浮动时，`clearfix` hack 解决了什么问题？

#### --distractors--

`clearfix` hack 解决了浮动元素被移出正常文档流并被固定在页面上的问题。

---

`clearfix` hack 解决了浮动元素在移动端和平板布局下不响应的问题。

---

`clearfix` hack 解决了浮动元素从页面消失的问题。

#### --answer--

`clearfix` hack 解决了多个浮动元素并排时布局重叠和塌陷的问题。

### --question--

#### --text--

以下哪一个是使用 `clearfix` hack 的正确示例？

#### --distractors--

```css
.clearfix::before {
  position: fixed;
  top: 0;
  width: 100%;
  clear: both;
}
```

---

```css
.clearfix::after {
  position: relative;
  top: 30px;
  left: 30px;
  clear: all;
}
```

---

```css
.clearfix::before {
  top: 30px;
  clear: none;
}
```

#### --answer--

```css
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

### --question--

#### --text--

什么是静态定位？

#### --distractors--

用于将元素从页面的正常流中移除，并自动将其定位在网页的右上角。

---

允许你将元素从正常文档流中移除，使其独立于其他元素进行定位。

---

允许元素在滚动到某个点时才固定在指定位置。

#### --answer--

这是文档的正常流。元素依次从上到下、从左到右排列。

### --question--

#### --text--

以下哪一个是使用固定定位将导航栏设置在页面顶部的示例？

#### --distractors--

```css
.navbar {
  fixed: top;
  top: 0;
  width: 100%;
}
```

---

```css
.navbar {
  upper: fixed;
  width: 100%;
}
```

---

```css
.navbar {
  position: fixed-top;
  top: 0;
  width: 100%;
}
```

#### --answer--

```css
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
}
```

### --question--

#### --text--

以下哪一项是 `z-index` 属性的有效值？

#### --distractors--

`12.0`

---

`none`

---

`up`

#### --answer--

`1`

### --question--

#### --text--

以下哪一项是 `position` 属性的默认值？

#### --distractors--

`inherit`

---

`initial`

---

`relative`

#### --answer--

`static`

