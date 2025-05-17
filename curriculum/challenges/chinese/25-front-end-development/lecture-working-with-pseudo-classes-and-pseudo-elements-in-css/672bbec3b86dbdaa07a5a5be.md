---
id: 672bbec3b86dbdaa07a5a5be
title: 功能性伪类有哪些例子？
challengeType: 11
videoId: eQwf6Y3N_kY
dashedName: what-are-examples-of-functional-pseudo-classes
---

# --description--

观看视频或阅读文字稿并回答下方问题。

# --transcript--

功能性伪类有哪些例子？

功能性伪类允许你根据更复杂的条件或关系选择元素。与普通伪类（如 `:hover`、`:focus` 等根据元素状态选择）不同，功能性伪类可以在括号中接受参数，因此被称为“功能性伪类”。

功能性伪类的例子有：

- `:is()`
- `:where()`
- `:has()`
- `:not()`

下面我们通过示例详细了解这些功能性伪类。

`:is()` 伪类适用于你想要为一组具有部分相同特征的元素设置样式时。例如，你可能想为网站上的不同类型按钮设置样式，包括 `button` 元素、样式为按钮的链接以及类型为 `submit` 和 `reset` 的 `input` 元素。HTML 示例：

```html
<button>点击我</button>
<a href="#" class="button">我也可以点击</a>
<input type="submit" value="提交" />
<input type="reset" value="重置" />
```

如果不用 `:is()`，你需要写如下复杂的选择器：

```css
button,
a.button,
input[type='submit'],
input[type='reset'] {
  background-color: darkblue;
  color: white;
  border: 1px solid darkblue;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
  cursor: pointer;
  display: inline-block;
  margin: 5px;
  font-size: 16px;
  text-align: center;
}

button:hover,
a.button:hover,
input[type='submit']:hover,
input[type='reset']:hover {
  background-color: lightblue;
  border-color: lightblue;
}
```

使用 `:is()`，你可以写得更简洁：

```css
:is(button, a.button, input[type='submit'], input[type='reset']) {
  background-color: darkblue;
  color: white;
  border: 1px solid darkblue;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
  cursor: pointer;
  display: inline-block;
  margin: 5px;
  font-size: 16px;
  text-align: center;
}

:is(button, a.button, input[type='submit'], input[type='reset']):hover {
  background-color: blue;
  border-color: blue;
}
```

`:where()` 伪类的功能与 `:is()` 类似，但不会增加选择器的特异性。这使得它非常适合应用样式而不影响其他规则的特异性。

例如，你可以用 `:where()` 为所有标题元素去除外边距和内边距，不会影响后续更具体的样式。HTML 示例：

```html
<h1>页面标题</h1>
<h2>副标题</h2>
<h3>要点</h3>
```

CSS 示例：

```css
:where(h1, h2, h3) {
  margin: 0;
  padding: 0;
}
```

以前很难根据子元素的状态为父元素设置样式，直到 `:has()` 伪类出现。它允许你根据子元素的存在或状态为父元素设置样式。

例如，下面的 CSS 只会应用于包含 `h2` 的 `article` 元素：

```css
article:has(h2) {
  border: 2px solid hotpink;
}
```

HTML 示例：

```html
<article>
  <h2>副标题</h2>
  <p>Lorem ipsum dolor sit amet.</p>
</article>

<article>
  <h3>要点</h3>
  <p>Lorem ipsum dolor sit amet.</p>
  <p>Lorem ipsum dolor sit amet.</p>
</article>
```

`:not()` 伪类适用于你想为一组元素设置样式，但排除一个或多个特定元素的情况。如下 CSS，除了主按钮外，其他按钮都为灰色背景：

```css
button {
  padding: 10px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  border: none;
  color: white;
}

button.primary {
  background-color: deepskyblue;
}

button:not(.primary) {
  background-color: grey;
}
```

按钮的 HTML 示例：

```html
<button class="primary">主按钮</button>
<button class="secondary">次按钮</button>
<button class="danger">另一个次按钮</button>
```

# --questions--

## --text--

哪个伪类的作用类似于 `:is()`，但不会增加选择器的特异性？

## --answers--

`:not()`

### --feedback--

这个伪类非常适合应用广泛且不影响特异性的样式。

---

`:has()`

### --feedback--

这个伪类非常适合应用广泛且不影响特异性的样式。

---

`:where()`

---

`:empty`

### --feedback--

这个伪类非常适合应用广泛且不影响特异性的样式。

## --video-solution--

3

## --text--

以下哪个不是功能性伪类？

## --answers--

`:is()`

### --feedback--

功能性伪类使用括号并接受参数。

---

`:first-child`

### --feedback--

功能性伪类使用括号并接受参数。

---

`:has()`

### --feedback--

功能性伪类使用括号并接受参数。

---

`:where()`

### --feedback--

功能性伪类使用括号并接受参数。

## --video-solution--

2

## --text--

哪个伪类非常适合在为一组元素设置样式时排除一两个特定元素？

## --answers--

`:has()`

### --feedback--

想一想如何排除特定元素不被样式覆盖。

---

`:is()`

### --feedback--

想一想如何排除特定元素不被样式覆盖。

---

`:not()`

---

`:where()`

### --feedback--

想一想如何排除特定元素不被样式覆盖。

## --video-solution--

3

