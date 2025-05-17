---
id: 671a98fbaabfba994e3d9a7c
title: CSS 变量复习
challengeType: 24
dashedName: review-css-variables
---

# --description--

## CSS 自定义属性（CSS 变量）

- **定义**：CSS 自定义属性，也称为 CSS 变量，是由 CSS 作者定义的实体，包含可在整个文档中重复使用的特定值。它们是一项强大的功能，使样式表更加高效、可维护和灵活。自定义属性在创建可主题化设计时尤其有用。你可以为不同主题定义一组属性：

```css
:root {
  --bg-color: white;
  --text-color: black;
}

.dark-theme {
  --bg-color: #333;
  --text-color: white;
}

body {
  background-color: var(--bg-color);
  color: var(--text-color);
}
```

## `@property` 规则

- **定义**：`@property` 规则是一项强大的 CSS 功能，允许开发者对自定义属性的行为进行更精细的控制，包括它们如何动画以及初始值。

```css
@property --property-name {
  syntax: '<type>';
  inherits: true | false;
  initial-value: <value>;
}
```

- **`--property-name`**：这是你要定义的自定义属性名称。和所有自定义属性一样，必须以两个短横线开头。`--property-name` 可以是 `<color>`、`<length>`、`<number>`、`<percentage>` 或更复杂的类型。
- **`syntax`**：定义属性的类型。
- **`inherits`**：指定该属性是否应从父元素继承值。
- **`initial-value`**：设置属性的默认值。
- **使用 `@property` 规则的渐变示例**：此示例创建了一个在元素悬停时平滑动画的渐变。

```html
<div class="gradient-box"></div>
```

```css
@property --gradient-angle {
  syntax: "<angle>";
  inherits: false;
  initial-value: 0deg;
}

.gradient-box {
  width: 100px;
  height: 100px;
  background: linear-gradient(var(--gradient-angle), red, blue);
  transition: --gradient-angle 0.5s;
}

.gradient-box:hover {
  --gradient-angle: 90deg;
}
```

- **回退值**：使用自定义属性时，可以像标准自定义属性一样，在 `var()` 函数中提供回退值：

```css
.button {
  background-color: var(--main-color, #3498db);
}
```

# --assignment--

复习 CSS 变量相关主题和概念。

