---
id: 672bccae6e556cd81cef6af2
title: 什么是外边距折叠，它是如何工作的？
challengeType: 11
videoId: MMWBC8duT_0
dashedName: what-is-margin-collapsing
---

# --description--

观看视频或阅读文字稿并回答下列问题。

# --transcript--

什么是外边距折叠，它是如何工作的？

外边距折叠是 CSS 中一个基础但常让新手开发者困惑的概念。

当相邻元素的垂直外边距重叠时，会发生这种行为，最终只保留较大的那个外边距。

理解外边距折叠对于精确控制网页设计中的间距和布局非常重要。下面我们来详细了解外边距折叠的工作原理，并探讨一些常见的应用场景。

在 CSS 中，当两个垂直外边距相遇时，它们会折叠，也就是说不会相加，而是取较大的那个作为元素之间的间距。这种行为只适用于垂直外边距（上和下），不适用于水平外边距（左和右）。下面用一个例子来说明这个概念：

```html
<style>
  .box1 {
    margin-bottom: 20px;
    background-color: lightblue;
  }
  .box2 {
    margin-top: 30px;
    background-color: lightgreen;
  }
</style>

<div class="box1">Box 1</div>
<div class="box2">Box 2</div>
```

在这个例子中，你可能会认为 `.box1` 和 `.box2` 之间的总间距是 50 像素（20 像素加 30 像素）。但由于外边距折叠，实际间距是 30 像素，也就是两者中较大的那个。

如前面的例子所示，相邻兄弟元素的外边距会折叠。这是外边距折叠最直接的情况。我们再来看一些其他可能发生折叠的场景。

外边距也可能在父元素与其第一个或最后一个子元素之间折叠。如果没有边框、内边距、内联内容或清除来分隔父元素和子元素的外边距，它们就会折叠。

```html
<style>
  .parent {
    margin-top: 40px;
    background-color: lightyellow;
  }
  .child {
    margin-top: 30px;
    background-color: lightpink;
  }
</style>

<div class="parent">
  <div class="child">Child element</div>
</div>
```

在这个例子中，你可能认为子元素距离顶部有 70 像素（40 像素加 30 像素）。但实际上外边距会折叠，最终取较大的 40 像素。

如果一个元素没有内容、内边距或边框，它的上下外边距也会折叠为一个外边距。

```html
<style>
  .empty-block {
    margin-top: 20px;
    margin-bottom: 10px;
    height: 0;
  }
  .next-block {
    background-color: lightgray;
  }
</style>

<div class="empty-block"></div>
<div class="next-block">Next block</div>
```

在这个例子中，`empty-block` 的上外边距和下外边距会折叠为 30 像素，也就是两者中较大的那个。

下面是一个通过内边距防止折叠的例子：

```html
<style>
  .parent {
    margin-top: 40px;
    padding-top: 1px;
    background-color: lightyellow;
  }
  .child {
    margin-top: 30px;
    background-color: lightpink;
  }
</style>

<div class="parent">
  <div class="child">Child element</div>
</div>
```

在这个例子中，父元素设置了 1 像素的内边距，阻止了外边距折叠，因此从父元素顶部到子元素内容顶部的总间距为 71 像素。

理解外边距折叠对于精确控制 CSS 布局和间距非常重要。虽然有时会带来意想不到的结果，但它的设计初衷是让文档的间距更美观、更一致。了解外边距折叠发生的时机以及如何防止它，可以让你的网页布局更加可预测和易于维护。

# --questions--

## --text--

外边距折叠发生在哪个方向？

## --answers--

仅水平外边距。

### --feedback--

想一想哪些外边距（上、下、左、右）会受到这种行为的影响。

---

仅垂直外边距。

---

水平和垂直外边距都会。

### --feedback--

想一想哪些外边距（上、下、左、右）会受到这种行为的影响。

---

对角线方向的外边距。

### --feedback--

想一想哪些外边距（上、下、左、右）会受到这种行为的影响。

## --video-solution--

2

## --text--

当两个相邻元素有不同的外边距时会发生什么？

## --answers--

外边距会相加。

### --feedback--

想一想外边距折叠时“胜出”的是哪一个。

---

使用较小的外边距。

### --feedback--

想一想外边距折叠时“胜出”的是哪一个。

---

使用较大的外边距。

---

使用两者的平均值。

### --feedback--

想一想外边距折叠时“胜出”的是哪一个。

## --video-solution--

3

## --text--

下列哪一项不会阻止父元素与其第一个子元素之间的外边距折叠？

## --answers--

为父元素添加 `border`。

### --feedback--

想一想哪些属性会在父元素和子元素的外边距之间产生分隔。

---

为父元素设置 `padding-top: 1px;`。

### --feedback--

想一想哪些属性会在父元素和子元素的外边距之间产生分隔。

---

为子元素设置 `display: inline-block;`。

### --feedback--

想一想哪些属性会在父元素和子元素的外边距之间产生分隔。

---

为子元素设置 `margin-top: 0;`。

## --video-solution--

4

