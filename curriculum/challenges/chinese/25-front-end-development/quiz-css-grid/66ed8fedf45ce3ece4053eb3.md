---
id: 66ed8fedf45ce3ece4053eb3
title: CSS Grid 测验
challengeType: 8
dashedName: quiz-css-grid
---

# --description--

要通过本测验，你必须正确回答以下 20 道题中的至少 18 道。

# --quizzes--

## --quiz--

### --question--

#### --text--

什么是 CSS Grid？

#### --distractors--

一种用于在网站上显示表格的方法。

---

一种用于平铺图片的方法。

---

一种用于在 HTML 元素周围显示轮廓的方法。

#### --answer--

一种用于 HTML 文档的二维布局方式。

### --question--

#### --text--

以下哪种方式可以正确创建一个 grid 容器？

#### --distractors--

`display: grid-area;`

---

`grid: grid-template;`

---

`grid-template: set;`

#### --answer--

`display: grid;`

### --question--

#### --text--

`grid-template-columns` 属性的作用是什么？

#### --distractors--

为 grid 容器定义两列三行。

---

将所有列设置为固定长度。

---

创建一个两列的 grid 布局容器。

#### --answer--

定义 grid 布局中的列数。

### --question--

#### --text--

`grid-template-rows` 属性的作用是什么？

#### --distractors--

指定 grid 项在布局中的大小和位置。

---

为创建新的 grid 行创建模板。

---

指定 grid 容器中默认的行高。

#### --answer--

指定 grid 布局中每一行的数量和高度。

### --question--

#### --text--

`minmax()` 函数的作用是什么？

#### --distractors--

根据可用空间在两个值之间切换。

---

返回两个输入值的平均值。

---

为全屏模式下工作的浏览器设置元素的最小尺寸。

#### --answer--

为轨道设置最小和最大尺寸。

### --question--

#### --text--

`column-gap` 和 `row-gap` 属性的简写是什么？

#### --distractors--

`gap-column-row`

---

`gutters`

---

`grid-gap`

#### --answer--

`gap`

### --question--

#### --text--

隐式网格和显式网格有什么区别？

#### --distractors--

隐式网格使用 `grid-template-columns` 属性，而显式网格使用 `grid-template-rows` 属性。

---

显式网格使用 `grid-template-columns` 属性，而隐式网格使用 `grid-template-rows` 属性。

---

隐式网格使用 `grid-template-columns` 或 `grid-template-rows` 属性创建列，而行和列会在显式网格中自动创建。

#### --answer--

显式网格使用 `grid-template-columns` 或 `grid-template-rows` 属性创建列，而行和列会在隐式网格中自动创建。

### --question--

#### --text--

以下哪个单位表示 grid 容器内空间的分数？

#### --distractors--

`fractional`

---

`frac`

---

`f`

#### --answer--

`fr`

### --question--

#### --text--

什么是网格线（grid lines）？

#### --distractors--

行和列的简写。

---

网格元素的轮廓线。

---

创建 grid 列和行的线。

#### --answer--

每个 grid 项目开始和结束的线。

### --question--

#### --text--

`grid-column` 属性的作用是什么？

#### --distractors--

将一个新的 grid 元素作为其应用元素的子元素添加。

---

垂直对齐 grid 项中的文本。

---

为 grid 容器设置两列。

#### --answer--

指定 grid 项应从哪条网格线开始和结束。

### --question--

#### --text--

如何创建四列等宽的布局？

#### --distractors--

`grid-template-columns: repeat(4);`

---

`grid-template-columns: repeat(1, 4);`

---

`grid-template-columns: repeat(1fr, 4);`

#### --answer--

`grid-template-columns: repeat(4, 1fr);`

### --question--

#### --text--

`grid-template-areas` 属性的作用是什么？

#### --distractors--

用于指定项目在 grid 容器中从哪一行开始。

---

用于在容器的轨道之间创建间隙。

---

用于在轨道列表中重复部分。

#### --answer--

用于为你要在 grid 上定位的项目提供名称。

### --question--

#### --text--

`grid-auto-flow` 属性的作用是什么？

#### --distractors--

控制 grid 项的显示顺序。

---

调整 grid 元素之间的间距。

---

自动调整元素以适应 grid。

#### --answer--

控制自动放置的元素如何插入到 grid 中。

### --question--

#### --text--

以下哪种方式正确使用了 `grid-template-areas` 属性？

#### --distractors--

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr; 
  grid-template-rows: auto 1fr auto; 
  grid-template-areas: set(
    "header header"
    "sidebar main"
    "footer footer" 
  );
  gap: 20px; 
}
```

---

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr; 
  grid-template-rows: auto 1fr auto; 
  grid-template-areas: apply(
    "header header"
    "sidebar main"
    "footer footer" 
  );
  gap: 20px; 
}
```

---

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr; 
  grid-template-rows: auto 1fr auto; 
  grid-template-areas: set-areas;
  gap: 20px; 
}
```

#### --answer--

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr; 
  grid-template-rows: auto 1fr auto; 
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer"; 
  gap: 20px; 
}
```

### --question--

#### --text--

以下哪种方式正确使用了 `grid-auto-flow` 属性？

#### --distractors--

```css
.social-icons {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-flow: none;
  grid-auto-columns: 1fr;
}
```

---

```css
.social-icons {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-flow: allow;
  grid-auto-columns: 1fr;
}
```

---

```css
.social-icons {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-flow: set;
  grid-auto-columns: 1fr;
}
```

#### --answer--

```css
.social-icons {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-flow: column;
  grid-auto-columns: 1fr;
}
```

### --question--

#### --text--

以下哪个不是有效的 grid 属性？

#### --distractors--

`gap`

---

`grid-column`

---

`grid-template-columns`

#### --answer--

`grid-set`

### --question--

#### --text--

以下哪些属性可以用于在 grid 元素内居中项目？

#### --distractors--

`allow-items`

---

`set-items`

---

`center-items`

#### --answer--

`align-items`

### --question--

#### --text--

以下哪个是 `grid-auto-columns` 属性的正确值？

#### --distractors--

`grid-auto-columns: unset-grid;`

---

`grid-auto-columns: revert-grid;`

---

`grid-auto-columns: set-content(20%);`

#### --answer--

`grid-auto-columns: 1fr;`

### --question--

#### --text--

什么是 grid 轨道（grid tracks）？

#### --distractors--

行和列的简写。

---

可以用来动画 grid 项移动的线。

---

每个 grid 项目开始和结束的线。

#### --answer--

两条相邻网格线之间的空间。

### --question--

#### --text--

以下哪种方式正确使用了 `minmax()` 函数？

#### --distractors--

```css
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(apply);
}
```

---

```css
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax();
}
```

---

```css
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(set);
}
```

#### --answer--

```css
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(150px, auto);
}
```

