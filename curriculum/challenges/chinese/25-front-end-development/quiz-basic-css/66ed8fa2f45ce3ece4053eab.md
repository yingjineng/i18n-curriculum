---
id: 66ed8fa2f45ce3ece4053eab
title: 基础 CSS 测验
challengeType: 8
dashedName: quiz-basic-css
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

CSS 的全称是什么？

#### --distractors--

Cascading Style Script（级联样式脚本）

---

Concatenating Style Script（连接样式脚本）

---

Castor Sage Style（海狸鼠鼠鼠样式）

#### --answer--

Cascading Style Sheets（层叠样式表）

### --question--

#### --text--

以下哪一项是正确的 CSS 规则？

#### --distractors--

`p=red`

---

`p (color: red)`

---

`{p color: red;}`

#### --answer--

`p {color: red;}`

### --question--

#### --text--

`<meta name="viewport">` 的作用是什么？

#### --distractors--

它将外部样式表链接到网页以实现响应式设计。

---

它指定搜索引擎用于索引网页的元数据。

---

它指定网页使用的字符编码。

#### --answer--

它控制网页在不同屏幕尺寸上的形状和大小。

### --question--

#### --text--

以下哪种语法用于内联 CSS 是正确的？

#### --distractors--

`<p color =  blue></p>`

---

`<p><style = blue></p>`

---

`p {color: blue;}`

#### --answer--

`<p style="color: blue;"></p>`

### --question--

#### --text--

使用内部 CSS 时，`style` 元素应放在 HTML 的哪个位置？

#### --distractors--

在 `meta` 元素中。

---

在 `script` 元素中。

---

在 `body` 元素中。

#### --answer--

在 `head` 元素中。

### --question--

#### --text--

以下哪条规则可以同时设置宽度和高度？

#### --distractors--

`height-width: 50px;`

---

`width-and-height: 50px;`

---

`flex-width: 50px; flex-height: 50px;`

#### --answer--

`width: 50px; height: 50px;`

### --question--

#### --text--

哪个选择器能正确选中只在 `div` 内部的 `h1` 元素？

#### --distractors--

`div, h1 {}`

---

`div ~ h1 {}`

---

`div + h1 {}`

#### --answer--

`div h1 {}`

### --question--

#### --text--

哪个选择器能正确选中 `footer` 的直接子元素？

#### --distractors--

`footer ~ ul {}`

---

`footer + ul {}`

---

`footer ul {}`

#### --answer--

`footer > ul {}`

### --question--

#### --text--

哪个选择器能正确选中 `img` 的下一个兄弟元素？

#### --distractors--

`img h1 {}`

---

`img > h1 {}`

---

`img ~ h1 {}`

#### --answer--

`img + h1 {}`

### --question--

#### --text--

哪个选择器能正确选中所有紧跟在 `img` 元素之后的兄弟元素？

#### --distractors--

`img > caption {}`

---

`img caption {}`

---

`img + caption {}`

#### --answer--

`img ~ caption {}`

### --question--

#### --text--

关于块级元素，哪项说法是正确的？

#### --distractors--

块级元素默认水平排列。

---

`width` 和 `height` 属性通常不适用于块级元素，除非将其 `display` 属性设置为 `inline-block`。

---

块级元素不能包含内联元素。

#### --answer--

块级元素会从新的一行开始，并占据其父容器的全部宽度。

### --question--

#### --text--

关于 `inline-block` 值，哪项说法是正确的？

#### --distractors--

元素垂直堆叠，总是占据父容器的全部宽度。

---

元素水平排列，但不能设置垂直的内边距或外边距。

---

元素可以设置宽高，但不能包含其他元素。

#### --answer--

元素保持内联流，但可以设置宽度和高度。

### --question--

#### --text--

以下选择器中，哪个具有最高的优先级（特异性）？

#### --distractors--

`div`

---

`h1`

---

`p`

#### --answer--

`#id`

### --question--

#### --text--

以下选择器中，哪个具有最低的优先级（特异性）？

#### --distractors--

`#id`

---

`.class`

---

`div h1`

#### --answer--

`h1`

### --question--

#### --text--

`*` 选择器的作用是什么？

#### --distractors--

选中页面上的部分元素。

---

选中页面上有子元素的元素。

---

选中页面上的所有 `p` 元素。

#### --answer--

选中页面上的所有元素。

### --question--

#### --text--

CSS 中的 `!important` 有什么作用？

#### --distractors--

它使 CSS 规则只对内联样式生效，忽略外部或内部样式表中的样式。

---

它禁用应用于同一元素的所有其他 CSS 属性，使其成为唯一影响元素样式的规则。

---

它只应用于某个选择器或元素组。

#### --answer--

它会覆盖为该选择器应用的任何其他属性值。

### --question--

#### --text--

CSS 层叠算法是如何工作的？

#### --distractors--

它仅根据声明顺序决定元素的样式，不考虑其他因素。

---

它只根据书写顺序应用样式，忽略特异性。

---

它只优先考虑特异性，忽略来源和相关性。

#### --answer--

它根据特异性和声明顺序决定元素的样式。

### --question--

#### --text--

哪条规则能为所有方向设置 `32px` 的外边距？

#### --distractors--

`margin-top: 32px;`

---

`margin: 32px 0;`

---

`margin: 0 32px;`

#### --answer--

`margin: 32px;`

### --question--

#### --text--

哪条规则能为上下方向设置 `24px` 的内边距？

#### --distractors--

`padding: 24px;`

---

`padding-top-bottom: 24px;`

---

`padding: 0 24px;`

#### --answer--

`padding: 24px 0;`

### --question--

#### --text--

对于 `padding: 10px 20px 30px 40px`，值的正确顺序是什么？

#### --distractors--

右，上，左，下

---

上，左，下，右

---

上，下，右，左

#### --answer--

上，右，下，左

## --quiz--

### --question--

#### --text--

CSS 规则的主要组成部分是什么？

#### --distractors--

元素和属性

---

样式和表

---

脚本和值

#### --answer--

选择器和声明块

### --question--

#### --text--

以下哪一项是 CSS 规则的正确语法？

#### --distractors--

```css
body [
  font-family: Arial;
]
```

---

```css
font-family {
  body: Arial;
}
```

---

```css
body {
  font-family; Arial:
}
```

#### --answer--

```css
body {
  font-family: Arial;
}
```

### --question--

#### --text--

什么是浏览器默认样式？

#### --distractors--

HTML 元素在所有浏览器中具有相同的样式属性。

---

它们是你必须为特定 HTML 元素使用的强制样式。

---

它们是各种浏览器的配色主题。

#### --answer--

浏览器自动应用的 CSS 规则。

### --question--

#### --text--

`width` 属性的默认值是什么？

#### --distractors--

`none`

---

`0`

---

`100%`

#### --answer--

`auto`

### --question--

#### --text--

`min-height` 属性指定什么？

#### --distractors--

元素的起始高度。

---

元素的高度。

---

元素的最大高度。

#### --answer--

元素的最小高度。

### --question--

#### --text--

关于通配符选择器 `*`，以下哪项说法正确？

#### --distractors--

它具有最高的特异性，因为它可以为页面上的所有元素设置样式。

---

它为特异性值的所有部分都加 1。

---

它无法重置不同浏览器的样式。

#### --answer--

它的特异性值是所有选择器中最低的。

### --question--

#### --text--

哪个选择器能正确选中有序列表的 `li` 元素？

#### --distractors--

`li {}`

---

`ul li {}`

---

`ol + li {}`

#### --answer--

`ol li {}`

### --question--

#### --text--

哪个选择器能选中 `div` 元素中的段落元素？

#### --distractors--

`p div {}`

---

`div, p {}`

---

`p, div {}`

#### --answer--

`div p {}`

### --question--

#### --text--

`margin` 属性应用于哪里？

#### --distractors--

元素内部的空间。

---

内容与边框之间。

---

元素的边框上。

#### --answer--

元素外部的空间。

### --question--

#### --text--

`padding` 属性应用于哪里？

#### --distractors--

元素边框与周围元素之间。

---

元素外部的空间。

---

元素的边框上。

#### --answer--

元素内部的空间。

### --question--

#### --text--

关于块级元素，哪项说法是错误的？

#### --distractors--

它们可以拉伸以适应容器宽度。

---

常见的块级元素有 `div`、`paragraph` 和 `section`。

---

块级元素会从新的一行开始，并占据其父容器的全部宽度。

#### --answer--

它们无法占据全部可用宽度，因为被阻止了。

### --question--

#### --text--

关于 `inline-block` 值，哪项说法是错误的？

#### --distractors--

`inline-block` 元素表现为内联元素。

---

它们可以设置 `width` 和 `height` 属性。

---

元素保持内联流，但可以设置 `width` 和 `height`。

#### --answer--

它们不具备内联或块级元素的任何属性。

### --question--

#### --text--

关于 `!important` 关键字，哪项说法是正确的？

#### --distractors--

用于为重要的 CSS 属性添加注释。

---

确保 CSS 属性语法正确。

---

让 CSS 规则更易于维护。

#### --answer--

它会覆盖其他选择器的特异性。

### --question--

#### --text--

类选择器名称前面用什么字符？

#### --distractors--

`#`

---

`$`

---

`*`

#### --answer--

`.`

### --question--

#### --text--

关于内联元素，哪项说法是错误的？

#### --distractors--

它们只占用所需的空间。

---

它们不会从新的一行开始。

---

常见的内联元素有 `span` 和 `img`。

#### --answer--

它们总是从新的一行开始。

### --question--

#### --text--

内部 CSS 样式在哪里访问？

#### --distractors--

它们是项目重要样式，因此不会外部共享。

---

由于它们是项目的核心样式，所以保存在 `styles.css` 文件中，供其他网页访问。

---

当只有一个网页需要样式时，它们存储在 `body` 元素内。

#### --answer--

它们写在 `head` 元素内的 `style` 部分。

### --question--

#### --text--

使用简写语法时，`padding` 属性的应用顺序是什么？

#### --distractors--

`上`，`下`，`左`，`右`

---

`左`，`右`，`上`，`下`

---

`右`，`上`，`左`，`下`

#### --answer--

`上`，`右`，`下`，`左`

### --question--

#### --text--

使用简写语法时，`margin` 属性的应用顺序是什么？

#### --distractors--

`左`，`右`，`上`，`下`

---

`右`，`上`，`左`，`下`

---

`上`，`下`，`左`，`右`

#### --answer--

`上`，`右`，`下`，`左`

### --question--

#### --text--

内联 CSS 样式的作用是什么？

#### --distractors--

仅用于为内联元素设置样式。

---

仅用于当所有元素都出现在浏览器视口同一行时设置样式。

---

用于解决关注点分离的问题。

#### --answer--

用于直接在元素内部设置样式，而不是使用内部或外部 CSS。

### --question--

#### --text--

ID 选择器前面用什么符号？

#### --distractors--

`.`

---

`*`

---

`$`

#### --answer--

`#`

