---
id: 587d78b1367417b2b2512b09
title: 使图片自适应设备尺寸
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

设置 `max-width` 值为 `100%` 可确保图片不超出父容器的范围；设置 `height` 属性为 `auto` 可以保持图片的原始宽高比。

# --instructions--

给 `responsive-img` 添加样式规则，使其成为响应式的图片。 它不应该超出父容器（在本例中，即预览窗口）的范围，并保持宽高比不变。 添加代码后，拖动浏览器窗口，看看图片发生什么变化。

# --hints--

`responsive-img` 类应将 `max-width` 设置为 `100%`。

```js
assert.strictEqual(getComputedStyle(document.querySelector('.responsive-img')).maxWidth, '100%');
```

`responsive-img` 类应将 `height` 设置为 `auto`。

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
