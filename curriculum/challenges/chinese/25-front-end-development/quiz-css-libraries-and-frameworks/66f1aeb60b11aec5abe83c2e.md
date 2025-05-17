---
id: 66f1aeb60b11aec5abe83c2e
title: CSS 库与框架测验
challengeType: 8
dashedName: quiz-css-libraries-and-frameworks
---

# --description--

要通过本测验，你必须正确回答以下 10 道题中的至少 9 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

什么是 CSS 框架？

#### --distractors--

用于修复 CSS 错误的工具。

---

用于检查 CSS 文件的工具。

---

用于格式化 CSS 文件的工具。

#### --answer--

用于 CSS 样式的库。

### --question--

#### --text--

以下哪一个是流行的实用优先（utility-first）CSS 框架？

#### --distractors--

Template CSS

---

Loading CSS

---

Minimal CSS

#### --answer--

Tailwind CSS

### --question--

#### --text--

CSS 框架的一个缺点是什么？

#### --distractors--

组件太少。

---

没有自定义选项。

---

提升了浏览器支持。

#### --answer--

可能导致 CSS 文件变大。

### --question--

#### --text--

SCSS 代表什么？

#### --distractors--

超级层叠样式表（Super Cascading Style Sheets）。

---

结构化 CSS。

---

简单 CSS。

#### --answer--

Sassy CSS。

### --question--

#### --text--

以下哪一项是 Sass 的特性？

#### --distractors--

注释

---

CSS 检查。

---

内联 CSS。

#### --answer--

混入（Mixins）

### --question--

#### --text--

在 Tailwind CSS 中，以下哪种方式是正确使用实用类的？

#### --distractors--

```html
<button class="color-blue text-color font-size allow-hover round-btn">
  Button
</button>
```

---

```html
<button class="blue text font-size hover round-btn margin-full">
  Button
</button>
```

---


```html
<button class="set-blue set-text set-font set-hover round-btn padding-full">
  Button
</button>
```

#### --answer--


```html
<button class="bg-blue-500 text-white font-bold py-2 px-4 rounded-full hover:bg-blue-700">
  Button
</button>
```

### --question--

#### --text--

CSS 框架有哪两种类型？

#### --distractors--

平板优先 CSS 框架和组件化 CSS 框架。

---

实用优先 CSS 框架和懒加载 CSS 框架。

---

极简 CSS 框架和实用优先 CSS 框架。

#### --answer--

实用优先 CSS 框架和组件化 CSS 框架。

### --question--

#### --text--

SCSS 的文件扩展名是什么？

#### --distractors--

`.sass`

---

`.scsss`

---

`.css`

#### --answer--

`.scss`

### --question--

#### --text--

以下哪种方式是在 SCSS 中定义变量的正确方法？

#### --distractors--

```css
#primary-color: #3498eb;

header {
  background-color: #primary-color;
}
```

---

```css
>primary-color: #3498eb;

header {
  background-color: >primary-color;
}
```

---

```css
?primary-color: #3498eb;

header {
  background-color: ?primary-color;
}
```

#### --answer--

```css
$primary-color: #3498eb;

header {
  background-color: $primary-color;
}
```

### --question--

#### --text--

以下哪种方式是定义 mixin 的正确方法？

#### --distractors--

```css
--mixin center-flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

---

```css
>mixin center-flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

---

```css
mixin center-flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

#### --answer--

```css
@mixin center-flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

