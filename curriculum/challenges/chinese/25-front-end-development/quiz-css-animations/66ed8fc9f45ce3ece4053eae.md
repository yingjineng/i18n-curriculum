---
id: 66ed8fc9f45ce3ece4053eae
title: CSS 动画测验
challengeType: 8
dashedName: quiz-css-animations
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

CSS 中 `transform` 属性的作用是什么？

#### --distractors--

改变元素的可见性。

---

为文本应用视觉效果。

---

设置元素的尺寸。

#### --answer--

修改元素的位置、大小和形状。

### --question--

#### --text--

CSS 的 `animation-direction` 属性如何影响动画？

#### --distractors--

它指定动画是否应被重复。

---

它设置动画的持续时间。

---

它定义动画的速度。

#### --answer--

它定义动画的播放方式。

### --question--

#### --text--

哪个 CSS 属性可以让动画运行 3 次？

#### --distractors--

`animation-repeat: 3`

---

`animation-loop: 3`

---

`animation-delay: 3`

#### --answer--

`animation-iteration-count: 3`

### --question--

#### --text--

哪种 CSS 时间函数让动画从开始到结束以一致的速度运行？

#### --distractors--

`ease`

---

`ease-in`

---

`ease-in-out`

#### --answer--

`linear`

### --question--

#### --text--

CSS 中 `@keyframes` 规则定义了什么？

#### --distractors--

CSS 渐变的颜色。

---

CSS 旋转的角度。

---

元素的尺寸。

#### --answer--

CSS 动画的各个阶段。

### --question--

#### --text--

CSS 中 `translateX()` 函数的作用是什么？

#### --distractors--

它改变元素的不透明度。

---

它旋转元素。

---

它垂直重新定位元素。

#### --answer--

它水平重新定位元素。

### --question--

#### --text--

以下哪项不是 CSS 动画可能带来的问题？

#### --distractors--

它们可能会对某些用户造成不适或身体伤害。

---

用户可能会觉得它们分散注意力。

---

过度使用会导致性能下降。

#### --answer--

它们可以提升用户体验。

### --question--

#### --text--

`@keyframes` 规则应定义在哪里？

#### --distractors--

在 HTML 文件的 `body` 元素内。

---

在 HTML 文件的 `head` 元素内。

---

在 CSS 类定义内。

#### --answer--

在顶层，位于任何 CSS 选择器之外。

### --question--

#### --text--

哪个 CSS 属性可以让你暂停和恢复动画？

#### --distractors--

`animation-timing-function`

---

`animation-delay`

---

`animation-direction`

#### --answer--

`animation-play-state`

### --question--

#### --text--

CSS 中 `animation-name` 属性应该赋予什么值？

#### --distractors--

动画的持续时间（秒）。

---

动画使用的时间函数。

---

动画开始前的延迟时间（秒）。

#### --answer--

由 `@keyframes` 定义的动画名称。

### --question--

#### --text--

下面这个 `@keyframe` 规则会对动画元素做什么？

```css
@keyframes animation {
  0% {
    transform: translateX(-50px);
  }
  100% {
    transform: translateX(100px);
  }
}
```

#### --distractors--

将元素顺时针旋转 90 度。

---

将元素颜色变为蓝色。

---

将元素缩放到初始大小的 50%，然后再变为 100%。

#### --answer--

将元素从 -50px 水平移动到 100px，相对于其起始点。

### --question--

#### --text--

哪个 CSS 属性定义了动画随时间的进展方式？

#### --distractors--

`animation-delay`

---

`animation-fill-mode`

---

`animation-iteration-count`

#### --answer--

`animation-timing-function`

### --question--

#### --text--

哪个 CSS 属性用于指定动画应在 5 秒内完成？

#### --distractors--

```css
animation-name: 5s;
```

---

```css
animation-delay: 5s;
```

---

```css
animation-timing-function: 5s;
```

#### --answer--

```css
animation-duration: 5s;
```

### --question--

#### --text--

在以下 CSS `@keyframe` 规则中，`50%` 代表什么？

```css
@keyframes animation {
  0% {
    transform: translateX(-50px);
  }
  50% {
    transform: translateX(25px);
  }
  100% {
    transform: translateX(100px);
  }
}
```

#### --distractors--

动画的起点。

---

动画的终点。

---

动画的速度。

#### --answer--

动画的中间点。

### --question--

#### --text--

当应用 `transform: translateX(200px);` 属性时会发生什么？

#### --distractors--

元素会向左移动 200px。

---

元素会向下移动 200px。

---

元素会顺时针旋转 200 度。

#### --answer--

元素会向右移动 200px。

### --question--

#### --text--

如果 `animation-iteration-count` 设置为 `infinite`，动画会如何表现？

#### --distractors--

动画运行一次后停止。

---

第一次循环后暂停。

---

三次循环后停止。

#### --answer--

动画会无限循环。

### --question--

#### --text--

哪个 `@keyframes` 选择器指定动画的起点？

#### --distractors--

`50%`

---

`25%`

---

`100%`

#### --answer--

`0%`

### --question--

#### --text--

使用 `animation` 简写属性可以指定哪些动画属性？

#### --distractors--

只能指定动画名称。

---

动画名称和持续时间。

---

动画名称、持续时间和延迟。

#### --answer--

所有动画属性。

### --question--

#### --text--

哪个 CSS 属性用于应用由 `@keyframes` 定义的动画？

#### --distractors--

`animation-duration`

---

`apply`

---

`translate`

#### --answer--

`animation`

### --question--

#### --text--

哪个 CSS 属性可以设置动画开始前的延迟时间？

#### --distractors--

`animation-fill-mode`

---

`animation-timing-function`

---

`animation-iteration-count`

#### --answer--

`animation-delay`

