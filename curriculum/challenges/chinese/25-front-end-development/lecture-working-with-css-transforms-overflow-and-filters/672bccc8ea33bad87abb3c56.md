---
id: 672bccc8ea33bad87abb3c56
title: content-box 和 border-box 有什么区别？
challengeType: 11
videoId: znOuWo58jgY
dashedName: what-is-the-difference-between-content-box-and-border-box
---

# --description--

观看视频或阅读文字稿并回答下列问题。

# --transcript--

在 CSS 中，`content-box` 和 `border-box` 有什么区别？

`box-sizing` 属性可以设置为 `content-box` 或 `border-box`，用于控制元素宽度和高度的计算方式。你可以看到 `box-sizing` 属性及其两个可选值：

```css
box-sizing: content-box;
```

```css
box-sizing: border-box;
```

你可以在通配选择器（`*`）上设置该属性，使其应用于文档中的所有元素：

```css
* {
  box-sizing: border-box;
}
```

`box-sizing` 属性的默认值是 `content-box`，但你也可以根据需要选择 `border-box`。我们先来了解 `content-box`，然后再介绍 `border-box`。

要理解这些模型的工作原理，你需要熟悉 CSS 盒模型的四个核心概念。我们快速回顾一下：内容区域是元素内容所占的空间；内边距（padding）是内容区域与边框之间的空间；边框（border）包围着内容区域和内边距；外边距（margin）是边框外部将元素与其他元素分隔开的空间。

在 `content-box` 模型中，你为元素设置的宽度和高度只决定内容区域的尺寸，不包括内边距、边框或外边距。当你需要精确控制内容区域的尺寸时，可以使用 `content-box`。所以，当你用 `width` 和 `height` 属性设置元素的宽高时，实际上只设置了内容区域的尺寸。`width` 是内容的宽度，`height` 是内容的高度。

要计算元素的总宽度（即你在屏幕上实际看到的宽度），还需要加上左右内边距和左右边框。所以，总宽度 = 内容宽度 + 左右内边距 + 左右边框。

同样，元素的总高度 = 内容高度 + 上下内边距 + 上下边框。

例如，下面是一个针对所有 `div` 元素的 CSS 类型选择器：

```css
div {
  width: 300px;
  height: 200px;
  padding: 20px;
  border: 4px solid black;
}
```

在这种情况下，如果使用 `content-box`，内容区域的宽度为 300 像素，高度为 200 像素。但实际显示的总宽度是内容宽度（300 像素）+ 左右内边距（40 像素）+ 左右边框（8 像素）。

同理，总高度 = 内容高度（200 像素）+ 上下内边距（40 像素）+ 上下边框（8 像素）。

接下来我们来了解 `border-box`。`border-box` 与 `content-box` 有所不同，元素的宽度和高度包括内容区域、内边距和边框，但不包括外边距。当你需要元素尺寸在内边距或边框变化时保持不变时，可以使用 `border-box`。这对于响应式网页设计也很有帮助，因为内容区域会自动调整以适应设定的尺寸。

内边距和边框都包含在盒子内部，所以当你设置元素的 `width` 和 `height` 属性时，实际上设置的是盒子内部的总宽高。下面是和之前一样的 `div` 示例：

```css
div {
  width: 300px;
  height: 200px;
  padding: 20px;
  border: 4px solid black;
}
```

使用 `border-box` 时，`width` 属性的值等于内容宽度 + 左右内边距 + 左右边框。

同理，`height` 属性的值等于内容高度 + 上下内边距 + 上下边框。外边距不包含在宽高内。

如果你在浏览器中分别用 `content-box` 和 `border-box` 检查 `div` 的尺寸，会发现它们有很大的区别。下面是 HTML 中的两个 `div`：

```html
<div id="red-div"></div>
<div id="blue-div"></div>
```

我们为它们分别设置了 `id`，以便在 CSS 中单独选择。以下是 `#red-div` 和 `#blue-div` 的 CSS 规则：

```css
#red-div {
  box-sizing: content-box;
  width: 300px;
  height: 200px;
  padding: 20px;
  border: 4px solid black;
  margin: 10px;
  background-color: red;
}

#blue-div {
  box-sizing: border-box;
  width: 300px;
  height: 200px;
  padding: 20px;
  border: 4px solid black;
  margin: 10px;
  background-color: blue;
}
```

你可以看到它们的 `width`、`height`、`padding`、`border` 和 `margin` 都相同，唯一的区别是颜色和 `box-sizing` 属性的值。这个小小的区别会对最终尺寸产生很大影响。

选择 `content-box` 还是 `border-box`，取决于你项目的具体需求。`border-box` 因其简单和灵活性越来越受欢迎，但理解这两种模型对于实现高效的 CSS 布局非常重要。

# --questions--

## --text--

以下哪一项是大多数浏览器中 `box-sizing` 属性的默认值？

## --answers--

`content-box`

---

`border-box`

### --feedback--

想一想元素尺寸的默认计算方式。

---

`padding-box`

### --feedback--

想一想元素尺寸的默认计算方式。

---

`margin-box`

### --feedback--

想一想元素尺寸的默认计算方式。

## --video-solution--

1

## --text--

使用 `border-box` 创建响应式布局的主要优势是什么？

## --answers--

它让计算变得更复杂。

### --feedback--

想一想 `border-box` 如何在指定的 `width` 和 `height` 内处理 `padding` 和 `border`。

---

它允许更精确地控制元素尺寸。

### --feedback--

想一想 `border-box` 如何在指定的 `width` 和 `height` 内处理 `padding` 和 `border`。

---

它确保无论 `padding` 或 `border` 如何变化，元素都能保持指定的尺寸。

---

它提升了浏览器兼容性。

### --feedback--

想一想 `border-box` 如何在指定的 `width` 和 `height` 内处理 `padding` 和 `border`。

## --video-solution--

3

## --text--

在 `content-box` 模型中，元素指定的 `width` 代表什么？

## --answers--

元素的总宽度，包括 `padding`、`border` 和 `margin`。

### --feedback--

想一想在 `content-box` 模型中内容区域与整体元素尺寸的关系。

---

仅内容区域的宽度。

---

`border` 的宽度。

### --feedback--

想一想在 `content-box` 模型中内容区域与整体元素尺寸的关系。

---

`padding` 的宽度。

### --feedback--

想一想在 `content-box` 模型中内容区域与整体元素尺寸的关系。

## --video-solution--

2

