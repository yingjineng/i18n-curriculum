---
id: 66ed8fc1f45ce3ece4053ead
title: CSS 可访问性测验
challengeType: 8
dashedName: quiz-css-accessibility
---

# --description--

要通过本测验，你必须正确回答以下 10 道题中的至少 9 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

为什么你需要在网页上保持良好的颜色对比度？

#### --distractors--

让页面更加鲜艳。

---

满足搜索引擎优化（SEO）的要求。

---

让页面的重要元素更加突出。

#### --answer--

让页面内容对所有人都可访问且易于阅读。

### --question--

#### --text--

以下哪种工具可以让你输入背景色和前景色并检查它们的对比度比率？

#### --distractors--

TPGi 色彩对比分析器

---

Figma

---

Canva

#### --answer--

WebAIM 的色彩对比检查器

### --question--

#### --text--

以下哪种工具可以让你从网页上实时选择背景色和前景色，并检查它们的对比度比率？

#### --distractors--

Figma

---

Canva

---

WebAIM 的色彩对比检查器

#### --answer--

TPGi 色彩对比分析器

### --question--

#### --text--

为什么不应该使用 `display: none` 和 `visibility: hidden` 来视觉上隐藏内容？

#### --distractors--

这些方法会让只有辅助技术（如屏幕阅读器）才能访问隐藏内容。

---

这些方法只会在用户将鼠标移到内容上时隐藏内容。

---

这些方法在某些浏览器中不起作用。

#### --answer--

这些方法会将内容从可访问性树中移除，使屏幕阅读器无法访问隐藏内容。

### --question--

#### --text--

什么是可访问性树？

#### --distractors--

网页布局的可视化表示。

---

屏幕阅读器用于读取网页文本内容的结构。

---

DOM 树的副本。

#### --answer--

屏幕阅读器用于解释和与网页内容交互的结构。

### --question--

#### --text--

以下哪种方式可以确保图片的最小宽度为 `400px`，但当视口宽度大于 `1000px` 时图片会变宽？

#### --distractors--

```css
img {
  width: max(400px, 10vw);
}
```

---

```css
img {
  width: max(400px, 30vw);
}
```

---

```css
img {
  width: max(400px, 20vw);
}
```

#### --answer--

```css
img {
  width: max(400px, 40vw);
}
```

### --question--

#### --text--

以下哪个 `scroll-behavior` 的值可以实现平滑滚动效果？

#### --distractors--

`auto`

---

`inherit`

---

`revert`

#### --answer--

`smooth`

### --question--

#### --text--

以下哪个特性用于检测用户的动画偏好？

#### --distractors--

`prefers-contrast`

---

`display-mode`

---

`animation`

#### --answer--

`prefers-reduce-motion`

### --question--

#### --text--

`input` 元素的 `placeholder` 属性存在哪种可访问性问题？

#### --distractors--

占位符文本会阻止屏幕阅读器读取输入标签文本。

---

占位符文本会阻止屏幕阅读器读取输入值。

---

占位符文本太小，难以阅读。

#### --answer--

占位符文本可能会被误认为是实际的输入值。

### --question--

#### --text--

`hidden` 属性的作用是什么？

#### --distractors--

它隐藏内容并在悬停时显示。

---

它只从可访问性树中隐藏内容。

---

它只在视觉上隐藏内容，但内容仍在可访问性树中。

#### --answer--

它会同时从视觉和可访问性树中隐藏内容。

