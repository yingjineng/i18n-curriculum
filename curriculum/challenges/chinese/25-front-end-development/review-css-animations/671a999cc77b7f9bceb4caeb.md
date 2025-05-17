---
id: 671a999cc77b7f9bceb4caeb
title: CSS 动画复习
challengeType: 24
dashedName: review-css-animations
---

# --description--

## CSS 动画基础

- **定义**：CSS 动画允许你在网页上创建动态且具有视觉吸引力的效果，无需 JavaScript 或复杂的编程。它们提供了一种在指定持续时间内平滑地将元素从一种样式过渡到另一种样式的方法。
- **`@keyframes` 规则**：该规则定义了动画的各个阶段和样式。它指定了动画过程中元素在不同时间点应具有的样式。

```css
@keyframes slide-in {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(0);
  }
}
```

- **`animation` 属性**：这是用于应用动画的简写属性。
- **`animation-name`**：指定要使用的 `@keyframes` 规则的名称。
- **`animation-duration`**：设置动画完成所需的时间。
- **`animation-timing-function`**：定义动画随时间的进展方式（如 ease、linear、ease-in-out）。
- **`animation-delay`**：指定动画开始前的延迟时间。
- **`animation-iteration-count`**：设置动画重复的次数。
- **`animation-direction`**：决定动画是正向播放、反向播放还是交替播放。
- **`animation-fill-mode`**：指定动画开始前和结束后元素的样式表现。
- **`animation-play-state`**：允许你暂停和恢复动画。

## 可访问性与 `prefers-reduced-motion` 媒体查询

- **`prefers-reduced-motion` 媒体查询**：动画的一个主要可访问性问题是它们可能会让部分用户感到不适，甚至造成身体伤害。患有前庭障碍或对运动敏感的人在屏幕上看到某些类型的运动时，可能会感到头晕、恶心或头痛。`prefers-reduced-motion` 媒体查询允许开发者检测用户是否在系统层面请求了最小化动画或运动效果。

```css
.animated-element {
  transition: transform 0.3s ease-in-out;
}

@media (prefers-reduced-motion: reduce) {
  .animated-element {
    transition: none;
  }
}
```

# --assignment--

复习 CSS 动画的相关主题和概念。

