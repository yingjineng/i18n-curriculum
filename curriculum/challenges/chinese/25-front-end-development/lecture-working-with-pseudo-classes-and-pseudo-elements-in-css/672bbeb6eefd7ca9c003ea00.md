---
id: 672bbeb6eefd7ca9c003ea00
title: 树结构伪类有哪些例子？
challengeType: 11
videoId: 7lQACnY4opw
dashedName: what-are-examples-of-tree-structural-pseudo-classes
---

# --description--

观看视频或阅读文字稿并回答下方问题。

# --transcript--

树结构伪类有哪些例子？

树结构伪类允许你根据元素在文档树中的位置进行选择和样式设置。文档树指的是 HTML 文档中元素的层级结构。

以下是树结构伪类的列表：

- `:root`
- `:empty`
- `:nth-child(n)`
- `:nth-last-child(n)`
- `:first-child`
- `:last-child`
- `:only-child`
- `:nth-of-type`
- `:first-of-type`
- `:last-of-type`
- `:only-of-type`

让我们逐一了解这些树结构伪类，并配以示例。

​​`:root` 伪类通常指根元素 `html`。它可以帮助你选中文档的最高层级，从而为整个文档应用统一样式。

```css
:root {
  background: black;
  color: aliceblue;
}
```

`:root` 伪类也常用于设置 CSS 变量：

```css
:root {
  --main-font: 'Arial, sans-serif';
  --primary-color: blue; 
  --secondary-color: green; 
}
```

通过 CSS 变量，你可以存储值并在样式表中复用。你将在后续学习更多相关内容。

空元素，即除了空白字符外没有任何子元素的元素，也包含在文档树中。因此有 `:empty` 伪类用于选中空元素。例如，下面的 HTML 代码有两个空的列表项：

```html
<ul>
  <li>Item 1</li>
  <li></li> <!-- 这是一个空列表项 -->
  <li>Item 2</li>
  <li></li> <!-- 另一个空列表项 -->
  <li>Item 3</li>
</ul>
```

使用 `:empty` 伪类，你可以为空的列表项设置不同的样式：

```css
:empty {
  background: black;
}
```

最常见的做法可能是直接隐藏这些空列表项：

```css
:empty {
  display: none;
}
```

`:nth-child(n)` 可以根据元素在父元素中的位置进行选择，而 `:nth-last-child(n)` 则是从末尾开始计数选择元素。`n` 可以是具体数字，也可以是 `odd` 或 `even` 等关键字。这在根据位置为表格单元格设置样式时非常有用，比如区分奇偶行。

下面是一个水果价格表的 HTML 示例：

```html
<table>
  <tr>
    <th>Item</th>
    <th>Price</th>
  </tr>
  <tr>
    <td>Apple</td>
    <td>$1.00</td>
  </tr>
  <tr>
    <td>Banana</td>
    <td>$0.50</td>
  </tr>
  <tr>
    <td>Orange</td>
    <td>$0.80</td>
  </tr>
</table>
```

使用 `:nth-child` 伪类为表格行设置奇偶样式的 CSS 如下：

```css
th,
td {
  border: 1px solid lightgray;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: orangered;
}

tr:nth-child(odd) {
  background-color: lightgreen;
}
```

`:first-child`、`:last-child` 和 `:only-child` 伪类都作用于父容器或整个文档中的元素。

- `:first-child` 选择父元素或文档中的第一个元素。
- `:last-child` 选择父元素或文档中的最后一个元素。
- `:only-child` 选择父元素或文档中唯一的元素。

在如下 HTML 中，`:first-child` 和 `:last-child` 都会选中 `Item 1` 和 `Item 3`：

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

对应的 CSS：

```css
li:first-child {
  background-color: orangered;
}

li:last-child {
  background-color: lightgreen;
}
```

如果页面上有多个无序列表，需要更具体地选择：

```css
ul li:first-child {
  background-color: orangered;
}

ul li:last-child {
  background-color: lightgreen;
}
```

下面通过两个 `div` 元素的例子说明 `:only-child` 伪类的用法：

```html
<div class="container">
  <div>这是该容器中唯一的元素。</div>
</div>

<div class="container">
  <div>这是该容器中的第一个元素。</div>
  <div>这是第二个元素。</div>
</div>
```

使用 `:only-child` 伪类，只会选中只有一个子元素的 `div`：

```css
.container div:only-child {
  border: 2px solid crimson;
  padding: 10px;
  background-color: lightblue;
}
```

`:first-of-type` 和 `:last-of-type` 伪类分别选择父元素中某一类型的第一个和最后一个元素。它们适用于为同类元素的首个或末个实例设置特殊样式。

在下面的 HTML 中，`:first-of-type` 和 `:last-of-type` 分别作用于 `section` 元素内的第一个和最后一个 `p` 元素：

```html
<section>
  <h2>Introduction</h2>
  <p>这是第一节中的第一段</p>
  <p>这是第一节中的第二段</p>
</section>
<section>
  <h2>Details</h2>
  <p>这是第二节中的第一段。</p>
  <p>这是第二节中的第二段。</p>
</section>
```

对应的 CSS：

```css
section p:first-of-type {
  background-color: lightgreen;
}

section p:last-of-type {
  background-color:lightblue;
}
```

`:nth-of-type(n)` 可以根据同类型兄弟元素中的位置选择特定元素。例如，下面的 HTML 中，`:nth-of-type(2)` 选中容器中的第二个 `p` 元素：

```html
<div class="container">
  <p>第一段</p>
  <h2>第一个标题</h2>
  <p>第二段</p>
  <p>第三段</p>
  <h2>第二个标题</h2>
</div>
```

对应的 CSS：

```css
p:nth-of-type(2) {
  color: red;
  font-weight: bold;
}
```

`:only-of-type` 选择父元素中唯一的某类型元素。这对于突出显示单个元素或在其不属于组时进行特殊样式设置很有用。

下面的 HTML 中有两个 `div`，其中一个只有一个 `p` 元素：

```html
<div class="container">
  <p>唯一的段落</p>
</div>

<div class="container">
  <p>第一个段落</p>
  <p>第二个段落</p>
</div>
```

只对第一个容器生效的 CSS 如下：

```css
p:only-of-type {
  border: 4px solid green;
}
```

# --questions--

## --text--

`:first-of-type` 和 `:last-of-type` 伪类有什么区别？

## --answers--

`:first-of-type` 选中父元素中某一类型的第一个元素，而 `:last-of-type` 选中父元素中同类型的最后一个元素。

---

`:first-of-type` 和 `:last-of-type` 都选中某一类型元素的第一个实例，但分别作用于文档的不同部分。

### --feedback--

思考这些伪类如何帮助你为特定标签（如 `p` 或 `h1`）的首个和末个实例设置样式。

---

`:first-of-type` 选中父元素中某一类型的第一个元素，而 `:last-of-type` 选中父元素中同类型的最后一个元素。

---

`:last-of-type` 为文档中的首个和末个元素应用样式，而 `:last-of-type` 为所有特定类型的元素应用样式。

### --feedback--

思考这些伪类如何帮助你为特定标签（如 `p` 或 `h1`）的首个和末个实例设置样式。

## --video-solution--

3

## --text--

`:first-child` 和 `:last-child` 伪类有什么区别？

## --answers--

`:first-child` 选中父元素中的第一个元素，而 `:last-child` 选中不同父元素中的最后一个元素。

### --feedback--

思考这两个伪类如何帮助你为同一父容器中的首个和末个元素设置样式。

---

`:first-child` 选中父元素中的第一个元素，而 `:last-child` 选中同一父元素中的最后一个元素。

---

`:first-child` 选中父元素中某一类型的第一个元素，而 `:last-child` 选中同一父元素中不同类型的最后一个元素。

### --feedback--

思考这两个伪类如何帮助你为同一父容器中的首个和末个元素设置样式。

---

`:first-child` 选中父元素中的首个和末个元素，而 `:last-child` 选中所有其他元素。

### --feedback--

思考这两个伪类如何帮助你为同一父容器中的首个和末个元素设置样式。

## --video-solution--

2

## --text--

哪个伪类可以选中没有任何子元素（包括只包含空白字符的元素）的元素？

## --answers--

`:empty`

---

`:first-child`

### --feedback--

思考如何为没有内容的元素设置样式。

---

`:last-child`

### --feedback--

思考如何为没有内容的元素设置样式。

---

`:only-of-type`

### --feedback--

思考如何为没有内容的元素设置样式。

## --video-solution--

1

