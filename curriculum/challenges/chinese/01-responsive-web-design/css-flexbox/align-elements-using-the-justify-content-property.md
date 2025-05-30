---
id: 587d78ac367417b2b2512af6
title: 使用 justify-content 属性对齐元素
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVaDAv/c43gnHm'
forumTopicId: 301102
dashedName: align-elements-using-the-justify-content-property
---

# --description--

Sometimes the flex items within a flex container do not fill all the space in the container. It is common to want to tell CSS how to align and space out the flex items a certain way. Fortunately, the `justify-content` property has several options to do this. But first, there is some important terminology to understand before reviewing those options.

<a href="https://chinese.freecodecamp.org/news/flexbox-the-ultimate-css-flex-cheatsheet/" target="_blank" rel="noopener noreferrer nofollow">阅读更多关于 flex-box 属性的信息</a>

回忆一下，如果把 flex 容器设为一个行，它的子元素会从左到右逐个排列。 如果把 flex 容器设为一个列，它的子元素会从上到下逐个排列。 子元素排列的方向被称为 **main axis（主轴）**。 对一行来说，主轴水平贯穿每一个对象； 对于列，主轴垂直贯穿每一个对象。

对于如何沿主轴线排放 flex 项目，有几种选择。 常用的一种是 `justify-content: center;`：即 flex 子元素在 flex 容器中居中排列。 其他选择包括：

<ul><li><code>flex-start</code>: aligns items to the start of the flex container. For a row, this pushes the items to the left of the container. For a column, this pushes the items to the top of the container. This is the default alignment if no <code>justify-content</code> is specified.</li><li><code>flex-end</code>：从 flex 容器的终止位置开始对齐项目。 对行来说是把项目移至右边， 对于列是把项目移至底部。</li><li><code>space-between</code>：项目间保留一定间距地沿主轴居中排列。 第一个和最后一个项目被放置在容器边沿。 例如，在行中第一个项目会紧贴着容器左边，最后一个项目会紧贴着容器右边，然后其他项目均匀排布。</li><li><code>space-around</code>：与<code>space-between</code>相似，但头尾两个项目不会紧贴容器边缘，所有项目之间的空间均匀排布。</li><li><code>space-evenly</code>：在 flex 项目之间均匀分配空间，在 flex 容器的任一端都有一个完整的空间。</li></ul>

# --instructions--

这个例子可以帮助你理解这个属性。 请为 `#box-container` 元素添加 CSS 属性 `justify-content`，并将其属性值设置为 `center`。

**提示：**  
在编辑器里试试 `justify-content` 的其他可用值，看看它们之间的区别。 但要通过挑战，你必须把属性值设为 `center`。

# --hints--

`#box-container` 所选择的元素应有 `justify-content` 属性，且其属性值应为 `center`。

```js
const boxContainer = document.querySelector('#box-container');
const justifyDirection =
  window.getComputedStyle(boxContainer)['justify-content'];
assert.strictEqual(justifyDirection, 'center');
```

# --seed--

## --seed-contents--

```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 500px;

  }
  #box-1 {
    background-color: dodgerblue;
    width: 25%;
    height: 100%;
  }

  #box-2 {
    background-color: orangered;
    width: 25%;
    height: 100%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

# --solutions--

```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 500px;
    justify-content: center;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 25%;
    height: 100%;
  }

  #box-2 {
    background-color: orangered;
    width: 25%;
    height: 100%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
