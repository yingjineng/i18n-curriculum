---
id: 672bbeaa5afdc5a98d5ab8ff
title: 位置伪类有哪些示例？
challengeType: 11
videoId: i-J4xVUGY5c
dashedName: what-are-examples-of-location-pseudo-classes
---

# --description--

观看视频或阅读文字稿，并回答下方问题。

# --transcript--

位置伪类有哪些示例？

位置伪类用于为链接和当前文档中被定位的元素设置样式。它们可以根据链接是否被访问或元素是否处于焦点来应用不同的样式。

常见的定位伪类有：

- `:link`
- `:visited`
- `:any-link`
- `:local-link`
- `:target`
- `:target-within`

下面我们来详细了解这些伪类。

`:link` 伪类用于选中所有未被访问过的链接。你可以用它来为用户尚未点击的链接设置不同的样式。例如，你可能希望所有未访问的链接显示为蓝色或你网站的主色：

```css
a:link {
  color: magenta;
}
```

在这个例子中，用户尚未点击的链接会显示为洋红色。一旦用户点击了链接，`:link` 样式就不再应用，`:visited` 伪类就会生效。`:visited` 伪类用于选中用户已经访问过的链接。

下面是将已访问链接颜色改为紫色的示例：

```css
a:visited {
  color: purple;
}
```

`:visited` 伪类有助于用户区分已访问和未访问的链接。

`:any-link` 伪类是 `:link` 和 `:visited` 的组合。它匹配所有带有 `href` 属性的锚点元素，无论是否被访问过。

下面是将 `:any-link` 伪类的链接颜色设置为深红色的示例：

```css
a:any-link {
  color: crimson;
}
```

`:local-link` 伪类用于选中指向同一文档的链接。当你想区分内部链接和外部链接时会很有用。但目前没有浏览器支持 `:local-link` 伪类。

`:target` 伪类选中与当前 URL 片段标识符（如 `#section1`）匹配的元素。它在页面内导航时非常有用。

下面是一个页面内导航的 HTML 示例：

```html
<nav id="table-of-contents">
  <ul>
    <li><a href="#section1">介绍</a></li>
    <li><a href="#section2">功能</a></li>
  </ul>
</nav>

<section id="section1">
  <h2>介绍</h2>
  <p>这是介绍部分。</p>
</section>

<section id="section2">
  <h2>功能</h2>
  <p>本节描述功能。</p>
</section>
```

下面是使用 `:target` 伪类为被导航到的 section 设置样式的 CSS：

```css
section:target {
  background-color: green;
  border: 2px solid green;
  padding: 10px;
}
```

当用户点击导航链接时，相应的 section 背景色会变为绿色。

# --questions--

## --text--

哪个伪类可以让你为与当前 URL 片段标识符（如 `#section1`）匹配的元素设置样式？

## --answers--

`:hover`

### --feedback--

想一想如何在页面内导航时高亮显示特定部分。

---

`:focus`

### --feedback--

想一想如何在页面内导航时高亮显示特定部分。

---

`:target`

---

`:checked`

### --feedback--

想一想如何在页面内导航时高亮显示特定部分。

## --video-solution--

3

## --text--

位置伪类在什么时候特别有用？

## --answers--

当根据元素的兄弟关系设置样式时。

### --feedback--

想一想如何根据用户的交互来为链接和被定位的元素设置样式。

---

当根据链接是否被访问或元素是否处于焦点来应用样式时。

---

当根据父元素的属性为元素设置样式时。

### --feedback--

想一想如何根据用户的交互来为链接和被定位的元素设置样式。

---

当动态调整网页布局时。

### --feedback--

想一想如何根据用户的交互来为链接和被定位的元素设置样式。

## --video-solution--

2

## --text--

哪个伪类用于选中指向同一文档的链接，但目前没有任何浏览器支持？

## --answers--

`:any-link`

### --feedback--

请考虑那个用于区分内部链接和外部链接但尚未被支持的伪类。

---

`:local-link`

---

`:visited`

### --feedback--

请考虑那个用于区分内部链接和外部链接但尚未被支持的伪类。

---

`:target`

### --feedback--

请考虑那个用于区分内部链接和外部链接但尚未被支持的伪类。

## --video-solution--

2

