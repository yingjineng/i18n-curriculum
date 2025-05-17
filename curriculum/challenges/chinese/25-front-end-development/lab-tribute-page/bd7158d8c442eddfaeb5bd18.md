---
id: bd7158d8c442eddfaeb5bd18
title: 制作一个致敬页
challengeType: 25
demoType: onClick
dashedName: build-a-tribute-page
---

# --description--

完成以下用户故事并通过所有测试以完成本实验。

**用户需求：**

1. 你的致敬页应包含一个 `main` 元素，并且其 `id` 为 `main`，该元素包含所有其他元素。
1. 你应该看到一个 `id` 为 `title` 的元素，包含描述致敬页主题的文本（例如：“诺曼·博劳格博士”）。
1. 你应该看到一个 `id` 为 `img-div` 的 `figure` 或 `div` 元素。
1. 在 `#img-div` 元素内，你应该看到一个 `id="image"` 的 `img` 元素。
1. 在 `#img-div` 元素内，你应该看到一个 `id="img-caption"` 的元素，包含描述 `#img-div` 中图片的文本内容。
1. 你应该看到一个 `id="tribute-info"` 的元素，包含描述致敬页主题的文本内容。
1. 你应该看到一个带有 `id="tribute-link"` 的 `a` 元素，该元素链接到包含致敬页主题更多信息的外部网站。提示：你必须为该元素添加 `target="_blank"` 属性，使链接在新标签页中打开。
1. 你的 `#image` 应使用 `max-width` 和 `height` 属性，使其相对于父元素宽度自适应缩放，且不超过原始尺寸。
1. 你的 `img` 元素应在其父元素内居中。

**注意：** 请确保在 HTML 中链接样式表并应用 CSS。

# --hints--

你的页面应该包含一个 `main` 元素，且它有一个值为`main` 的`id`属性。

```js
const el = document.getElementById('main');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'MAIN');
```

你的 `#img-div`、`#image`、`#img-caption`、`#tribute-info` 和 `#tribute-link` 应该是 `#main` 的子元素。

```js
const el1 = document.querySelector('#main #img-div');
const el2 = document.querySelector('#main #image');
const el3 = document.querySelector('#main #img-caption');
const el4 = document.querySelector('#main #tribute-info');
const el5 = document.querySelector('#main #tribute-link');
assert.isNotNull(el1);
assert.isNotNull(el2);
assert.isNotNull(el3);
assert.isNotNull(el4);
assert.isNotNull(el5);
```

你应该有一个 `id` 为 `title` 的元素。

```js
const el = document.getElementById('title');
assert.isNotNull(el);
```

你的 `#title` 元素不应为空。

```js
const el = document.getElementById('title');
assert.isNotNull(el);
assert.isNotEmpty(el.innerText, 0);
```

你应该有一个 `id` 为 `img-div` 的 `figure` 或 `div` 元素。

```js
const el = document.getElementById('img-div');
assert.isNotNull(el);
assert.isTrue(el.tagName === 'DIV' || el.tagName === 'FIGURE');
```

你应该有一个 `id` 为 `image` 的 `img` 元素。

```js
const el = document.getElementById('image');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'IMG');
```

你的 `#image` 元素应该是 `#img-div` 元素的子元素。

```js
const el = document.querySelector('#img-div #image');
assert.isNotNull(el);
```

你应该有一个 `id` 为 `img-caption` 的 `figcaption` 元素或 `div` 元素。

```js
const el = document.getElementById('img-caption');
assert.isNotNull(el);
assert.isTrue(el.tagName === 'DIV' || el.tagName === 'FIGCAPTION');
```

你的 `#img-caption` 元素应该是 `#img-div` 元素的子元素。

```js
const el = document.querySelector('#img-div #img-caption');
assert.isNotNull(el);
```

你的 `#img-caption` 不应为空。

```js
const el = document.getElementById('img-caption');
assert.isNotNull(el);
assert.isNotEmpty(el.innerText);
```

你应该有一个 `id` 为 `tribute-info` 的元素。

```js
const el = document.getElementById('tribute-info');
assert.isNotNull(el);
```

你的 `#tribute-info` 不应为空。

```js
const el = document.getElementById('tribute-info');
assert.isNotNull(el);
assert.isNotEmpty(el.innerText);
```

你应该有一个 `id` 为 `tribute-link` 的 `a` 元素。

```js
const el = document.getElementById('tribute-link');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'A');
```

你的 `#tribute-link` 应该有一个 `href` 属性和值。

```js
const el = document.getElementById('tribute-link');
assert.isNotNull(el);
assert.isNotNull(el.href);
assert.isNotEmpty(el.href);
```

你的 `#tribute-link` 元素应该有一个值为 `_blank` 的 `target` 属性。

```js
const el = document.getElementById('tribute-link');
assert.isNotNull(el);
assert.strictEqual(el.target, '_blank');
```

你的 `img` 元素应该具有 `display` 值为 `block`。

```js
const img = document.getElementById('image');
const imgStyle = window.getComputedStyle(img);
const style = imgStyle?.getPropertyValue('display');
assert.strictEqual(style, 'block');
```

你的 `#image` 应该具有 `max-width` 值为 `100%`。

```js
const img = document.getElementById('image');
const imgStyle = window.getComputedStyle(img);
const style = imgStyle?.getPropertyValue('max-width');
assert.strictEqual(style, '100%');
```

你的 `#image` 应该具有 `height` 值为 `auto`。

```js
// taken from the testable-projects repo
const img = document.getElementById('image');
const imgStyle = window.getComputedStyle(img);
const oldDisplayValue = imgStyle.getPropertyValue('display');
const oldDisplayPriority = imgStyle.getPropertyPriority('display');
img?.style.setProperty('display', 'none', 'important');
const heightValue = imgStyle?.getPropertyValue('height');
img?.style.setProperty('display', oldDisplayValue, oldDisplayPriority);
assert.strictEqual(heightValue, 'auto');
```

你的 `#image` 元素应该在其父元素内居中。

```js
// taken from the testable-projects repo
const img = document.getElementById('image'),
  imgParent = img?.parentElement,
  imgLeft = img?.getBoundingClientRect().left,
  imgRight = img?.getBoundingClientRect().right,
  parentLeft = imgParent?.getBoundingClientRect().left,
  parentRight = imgParent?.getBoundingClientRect().right,
  leftMargin = imgLeft - parentLeft,
  rightMargin = parentRight - imgRight;
assert.isBelow(leftMargin - rightMargin, 6);
assert.isBelow(rightMargin - leftMargin, 6);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="UTF-8" />
    <title>致敬页</title>
  </head>

  <body></body>
</html>
```

```css

```

# --solutions--

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <main id="main">
      <h1 id="title">诺曼·博劳格博士</h1>
      <p>拯救十亿生命的人</p>
      <figure id="img-div">
        <img
          id="image"
          src="https://cdn.freecodecamp.org/testable-projects-fcc/images/tribute-page-main-image.jpg"
          alt="诺曼·博劳格博士与一群生物学家站在墨西哥小麦田中"
        />
        <figcaption id="img-caption">
          诺曼·博劳格博士（左三）在墨西哥培训生物学家，教授如何提高小麦产量——这是他毕生致力于消除饥饿事业的一部分。
        </figcaption>
      </figure>
      <section id="tribute-info">
        <h3 id="headline">以下是博劳格博士的人生时间线：</h3>
        <ul>
          <li><strong>1914年</strong> - 出生于爱荷华州克雷斯科</li>
          <li>
            <strong>1933年</strong> - 离开家乡农场，凭借“大萧条”时期的“国家青年管理局”项目进入明尼苏达大学
          </li>
          <li>
            <strong>1935年</strong> - 因经济原因辍学打工，参与平民保护团，帮助饥饿的美国人。他说：“我看到食物如何改变了他们，这一切在我心中留下了伤痕。”
          </li>
          <li>
            <strong>1937年</strong> - 大学毕业，进入美国林务局工作
          </li>
          <li>
            <strong>1938年</strong> - 与玛格丽特·吉布森结婚（婚姻持续69年），因预算削减被裁员。受埃尔文·查尔斯·斯塔克曼启发，重返校园师从斯塔克曼，学习抗虫害植物育种。
          </li>
          <li>
            <strong>1941年</strong> - 珍珠港事件后试图参军被拒，军方要求其实验室研发防水胶、控制疟疾的DDT、消毒剂等应用科学项目。
          </li>
          <li>
            <strong>1942年</strong> - 获得遗传学与植物病理学博士学位
          </li>
          <li>
            <strong>1944年</strong> - 拒绝杜邦公司100%加薪，离开怀孕的妻子，飞往墨西哥主持新植物病理项目。16年间，他的团队培育出6000种抗病小麦品种，涵盖地球各大气候类型。
          </li>
          <li>
            <strong>1945年</strong> - 发现一年可种植两季小麦，使产量翻倍
          </li>
          <li>
            <strong>1953年</strong> - 将矮壮高产的小麦与美国高产品种杂交，培育出适合施肥的品种，最终占墨西哥小麦产量的95%。
          </li>
          <li>
            <strong>1962年</strong> - 访问德里，将高产小麦品种带到印度次大陆，帮助缓解因人口激增导致的大规模饥荒
          </li>
          <li><strong>1970年</strong> - 获得诺贝尔和平奖</li>
          <li>
            <strong>1983年</strong> - 帮助七个非洲国家大幅提高玉米和高粱产量
          </li>
          <li>
            <strong>1984年</strong> - 成为德克萨斯农工大学杰出教授
          </li>
          <li>
            <strong>2005年</strong> - 提出“到2050年我们必须使全球粮食供应翻倍”，认为转基因作物是唯一可行途径，并表示“我们很早以前就在对动植物进行基因改良，这并不危险。”
          </li>
          <li><strong>2009年</strong> - 享年95岁去世。</li>
        </ul>
        <blockquote
          cite="http://news.rediff.com/report/2009/sep/14/pm-pays-tribute-to-father-of-green-revolution-borlaug.htm"
        >
          <p>
            “博劳格的一生和成就证明了一个人的卓越智慧、坚持和科学远见能为人类和平与进步做出多么深远的贡献。”
          </p>
          <cite>—— 印度总理 曼莫汉·辛格</cite>
        </blockquote>
        <h3>
          如果你有时间，建议阅读
          <a
            id="tribute-link"
            href="https://zh.wikipedia.org/wiki/%E8%AF%BA%E6%9B%BC%C2%B7%E5%8D%9A%E5%8A%B3%E6%A0%BC"
            target="_blank"
            >他的维基百科词条</a
          >，了解这位杰出人物的更多事迹。
        </h3>
      </section>
    </main>
  </body>
</html>
```

```css
html {
  /* 设置基础字体大小为10px，便于rem计算
     说明：1rem === 10px，1.5rem === 15px，2rem === 20px，以此类推
   */
  font-size: 10px;
}

body {
  /* 原生字体栈 https://getbootstrap.com/docs/4.2/content/reboot/#native-font-stack */
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto',
    'Helvetica Neue', Arial, sans-serif;
  font-size: 1.6rem;
  line-height: 1.5;
  text-align: center;
  color: #333;
  margin: 0;
}

h1 {
  font-size: 4rem;
  margin-bottom: 0;
}

@media (max-width: 460px) {
  h1 {
    font-size: 3.5rem;
    line-height: 1.2;
  }
}

h2 {
  font-size: 3.25rem;
}

a {
  color: #477ca7;
}

a:visited {
  color: #74638f;
}

#main {
  margin: 30px 8px;
  padding: 15px;
  border-radius: 5px;
  background: #eee;
}

@media (max-width: 460px) {
  #main {
    margin: 0;
  }
}

img {
  max-width: 100%;
  display: block;
  height: auto;
  margin: 0 auto;
}

#img-div {
  background: white;
  padding: 10px;
  margin: 0;
}

#img-caption {
  margin: 15px 0 5px 0;
}

@media (max-width: 460px) {
  #img-caption {
    font-size: 1.4rem;
  }
}

#headline {
  margin: 50px 0;
  text-align: center;
}

ul {
  max-width: 550px;
  margin: 0 auto 50px auto;
  text-align: left;
  line-height: 1.6;
}

li {
  margin: 16px 0;
}

blockquote {
  font-style: italic;
  max-width: 545px;
  margin: 0 auto 50px auto;
  text-align: left;
}
```

