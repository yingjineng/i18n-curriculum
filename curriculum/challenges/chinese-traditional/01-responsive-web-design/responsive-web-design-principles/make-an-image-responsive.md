---
id: 587d78b1367417b2b2512b09
title: 使圖片自適應設備尺寸
challengeType: 0
forumTopicId: 301140
dashedName: make-an-image-responsive
---

# --description--

Making images responsive with CSS is actually very simple. You just need to add these properties to an image:

```css
img {
  max-width: 100%;
  height: auto;
}
```

設置 `max-width` 值爲 `100%` 可確保圖片不超出父容器的範圍；設置 `height` 屬性爲 `auto` 可以保持圖片的原始寬高比。

# --instructions--

給 `responsive-img` 添加樣式規則，使其成爲響應式的圖片。 它不應該超出父容器（在本例中，即預覽窗口）的範圍，並保持寬高比不變。 添加代碼後，拖動瀏覽器窗口，看看圖片發生什麼變化。

# --hints--

`responsive-img` 類應將 `max-width` 設置爲 `100%`。

```js
assert.strictEqual(getComputedStyle(document.querySelector('.responsive-img')).maxWidth, '100%');
```

`responsive-img` 類應將 `height` 設置爲 `auto`。

```js
assert.match(code, /height:\s*?auto;/g);
```

# --seed--

## --seed-contents--

```html
<style>
.responsive-img {


}

img {
  width: 600px;
}
</style>

<img
  class="responsive-img"
  src="https://cdn.freecodecamp.org/curriculum/responsive-web-design-principles/FCCStickerPack.jpg"
  alt="freeCodeCamp stickers set"
/>
<img
  src="https://cdn.freecodecamp.org/curriculum/responsive-web-design-principles/FCCStickerPack.jpg"
  alt="freeCodeCamp stickers set"
/>
```

# --solutions--

```html
<style>
  .responsive-img {
    max-width: 100%;
    height: auto;
  }

  img {
    width: 600px;
  }
</style>

<img
  class="responsive-img"
  src="https://cdn.freecodecamp.org/curriculum/responsive-web-design-principles/FCCStickerPack.jpg"
  alt="freeCodeCamp stickers set"
/>
<img
  src="https://cdn.freecodecamp.org/curriculum/responsive-web-design-principles/FCCStickerPack.jpg"
  alt="freeCodeCamp stickers set"
/>
```
