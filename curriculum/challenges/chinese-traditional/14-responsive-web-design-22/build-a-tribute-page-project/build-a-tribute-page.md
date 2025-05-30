---
id: bd7158d8c442eddfaeb5bd18
title: 製作一個致敬頁
challengeType: 14
forumTopicId: 301147
dashedName: build-a-tribute-page
---

# --description--

**目標：** 構建一個應用，它在功能上類似於 <a href="https://tribute-page.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://tribute-page.freecodecamp.rocks</a>。 **請勿複製此演示項目**。

**用戶需求:**

1. 你的致敬頁應該包含一個 `id` 爲 `main` 的 `main` 元素，它包含所有其他元素。
1. 你的頁面應該包含一個元素，它的屬性 `id` 值爲`title`,，元素中包含一個字符串（例如 text）描述致敬頁的主題（例如 "Dr. Norman Borlaug"）
1. 你應該有一個 `id` 爲 `img-div` 的 `figure` 或 `div` 元素
1. 在 `#img-div` 元素中，你應該看到一個 `id="image"` 的 `img` 元素
1. 在 `#img-div` 元素內，你應該看到一個 `id="img-caption"` 的元素，其中包含對 `#img-div` 中圖像的文本描述
1. 你應該看到一個 `id="tribute-info"` 的元素，其中包含描述致敬頁主題的文本內容
1. 你應該看到一個帶有相應 `id="tribute-link"` 的 `a` 元素，該元素鏈接到外部站點，其中包含有關致敬頁面主題的附加信息。 提示：你必須爲元素提供 `target` 屬性，並設置其爲 `_blank`，以便可以在新選項卡中打開鏈接。
1. 你的 `#image` 應該使用 `max-width` 和 `height` 屬性來響應式調整大小，相對於其父元素的寬度，但不超過其原始大小
1. 你的 `img` 元素應該在其父元素內居中

完成需求並通過下面的所有測試來完成這個項目。 使用你自己的個人風格樣式。 編程愉快！

**注意：** 請在你的 HTML 中添加 `<link rel="stylesheet" href="styles.css">` 以鏈接你的樣式表並應用你的 CSS

# --hints--

你應該有一個 `main` 元素且該元素的 `id` 爲 `main`.

```js
const el = document.getElementById('main');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'MAIN');
```

你的 `#img-div`、`#image`、`#img-caption`、`#tribute-info` 和 `#tribute-link` 應該是 `#main` 的子元素。

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

你應該有一個`id`爲`title`的元素。

```js
const el = document.getElementById('title');
assert.isNotNull(el);
```

id爲 `#title` 的元素不應爲空。

```js
const el = document.getElementById('title');
assert.isNotNull(el);
assert.isNotEmpty(el.innerText, 0);
```

你應該有一個 `id` 爲 `img-div` 的 `figure` 或 `div` 元素。

```js
const el = document.getElementById('img-div');
assert.isNotNull(el);
assert.isTrue(el.tagName === 'DIV' || el.tagName === 'FIGURE');
```

你應該有一個 `id` 爲 `image` 的 `img` 元素。

```js
const el = document.getElementById('image');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'IMG');
```

你的 `#image` 元素應該是 `#img-div` 元素的子元素。

```js
const el = document.querySelector('#img-div #image');
assert.isNotNull(el);
```

你應該有一個 `id` 爲 `img-caption` 的 `figcaption` 元素或 `div` 元素。

```js
const el = document.getElementById('img-caption');
assert.isNotNull(el);
assert.isTrue(el.tagName === 'DIV' || el.tagName === 'FIGCAPTION');
```

你的 `#img-caption` 元素應該是 `#img-div` 元素的子元素。

```js
const el = document.querySelector('#img-div #img-caption');
assert.isNotNull(el);
```

id爲 `#img-caption` 的元素不應爲空。

```js
const el = document.getElementById('img-caption');
assert.isNotNull(el);
assert.isNotEmpty(el.innerText);
```

你應該有一個 `id` 爲 `tribute-info` 的元素。

```js
const el = document.getElementById('tribute-info');
assert.isNotNull(el);
```

id爲 `#tribute-info` 的元素不應爲空。

```js
const el = document.getElementById('tribute-info');
assert.isNotNull(el);
assert.isNotEmpty(el.innerText);
```

你應該有一個 `id` 爲 `tribute-link` 的 `a` 元素。

```js
const el = document.getElementById('tribute-link');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'A');
```

id爲 `#tribute-link` 的元素的 `href` 屬性應該有值。

```js
const el = document.getElementById('tribute-link');
assert.isNotNull(el);
assert.isNotNull(el.href);
assert.isNotEmpty(el.href);
```

id爲 `#tribute-link` 的元素的 `target` 屬性應該設置爲 `_blank`。

```js
const el = document.getElementById('tribute-link');
assert.isNotNull(el);
assert.strictEqual(el.target, '_blank');
```

`img` 元素應該有 `display` 樣式且值應爲 `block`。

```js
const img = document.getElementById('image');
const imgStyle = window.getComputedStyle(img);
const style = imgStyle?.getPropertyValue('display');
assert.strictEqual(style, 'block');
```

id爲 `#image` 的元素應該有 `max-width` 樣式且值爲 `100%`。

```js
const img = document.getElementById('image');
const imgStyle = window.getComputedStyle(img);
const style = imgStyle?.getPropertyValue('max-width');
assert.strictEqual(style, '100%');
```

id爲 `#image` 的元素的 `height` 樣式值應爲 `auto`。

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

id爲 `#image` 的元素應該在其父元素內居中。

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

```

```css

```

# --solutions--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link
      href="https://fonts.googleapis.com/css?family=Pacifico"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css?family=Lobster"
      rel="stylesheet"
    />
    <link href="styles.css" rel="stylesheet" />
    <title>Tribute Page</title>
  </head>
  <body>
    <h1>Tribute Page</h1>
    <p>The below card was designed as a tribute page for freeCodeCamp.</p>
    <main id="main">
      <div id="img-div">
        <img
          id="image"
          class="border"
          src="https://upload.wikimedia.org/wikipedia/en/5/53/Pok%C3%A9mon_Togepi_art.png"
          alt="An image of Togepi"
        />
        <figcaption id="img-caption">Togepi, happy as always.</figcaption>
      </div>
      <h2 id="title">Togepi</h2>
      <hr />
      <div id="tribute-info">
        <p>
          Togepi was first discovered in the Johto region, when Ash Ketchum
          discovered a mysterious egg. However, when the egg hatched, Togepi saw
          Ash's friend Misty first and imprinted on her. Like many other
          creatures, this imprinting process created a bond and Togepi views
          Misty as his mother.
        </p>
        <p>
          Togepi is a very childlike Pokemon, and is very emotionally
          expressive. He demonstrates extreme levels of joy and sadness.
        </p>
        <hr />
        <p><u>Battle Information</u></p>
        <ul style="list-style-type: none">
          <li>Type: Fairy</li>
          <li>Evolutions: Togepi -> Togetic -> Togekiss</li>
          <li>Moves: Growl, Pound, Sweet Kiss, Charm</li>
          <li>Weaknesses: Poison, Steel</li>
          <li>Resistances: Dragon</li>
        </ul>
        <p>
          Check out this
          <a
            id="tribute-link"
            href="https://bulbapedia.bulbagarden.net/wiki/Togepi_(Pok%C3%A9mon)"
            target="_blank"
            rel="noopener noreferrer"
            >Bulbapedia article on Togepi</a
          >
          for more information on this great Pokemon.
        </p>
      </div>
    </main>
  </body>
  <footer>
    <a href="../">Return to Project List</a> |
    <a href="https://www.nhcarrigan.com">Return to HomePage</a>
  </footer>
</html>
```

```css
body {
  background-color: #3a3240;
  color: white;
}
main {
  background-color: #92869c;
  font-family: Lobster;
  max-width: 500px;
  margin: 20px auto;
  color: black;
  border-radius: 50px;
  box-shadow: 10px 10px rgba(0, 0, 0, 0.5);
}
h2 {
  text-align: center;
  font-size: 20pt;
  font-family: Pacifico;
}
body {
  text-align: center;
  font-size: 12pt;
}
footer {
  text-align: center;
  font-size: 10pt;
}
.border {
  border-color: black;
  border-width: 5px;
  border-style: solid;
}
#image {
  height: auto;
  display: block;
  margin: auto;
  max-width: 100%;
  border-radius: 50%;
}
#img-caption {
  font-size: 10pt;
}
a:not(#tribute-link) {
  color: white;
}
hr {
  border-color: black;
}
```
