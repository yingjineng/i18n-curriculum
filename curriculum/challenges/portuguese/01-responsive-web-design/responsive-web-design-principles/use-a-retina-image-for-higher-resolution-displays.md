---
id: 587d78b1367417b2b2512b0a
title: Usar uma imagem Retina para telas de resolução mais alta
challengeType: 0
videoUrl: 'https://scrimba.com/p/pzrPu4/cVZ4Rfp'
forumTopicId: 301142
dashedName: use-a-retina-image-for-higher-resolution-displays
---

# --description--

With the increase of internet connected devices, their sizes and specifications vary, and the displays they use could be different externally and internally. Pixel density is an aspect that could be different on one device from others and this density is known as Pixel Per Inch(PPI) or Dots Per Inch(DPI). The most famous such display is the one known as a "Retina Display" on the latest Apple MacBook Pro notebooks, and recently iMac computers. Due to the difference in pixel density between a "Retina" and "Non-Retina" displays, some images that have not been made with a High-Resolution Display in mind could look "pixelated" when rendered on a High-Resolution display.

A maneira mais simples de fazer com que suas imagens apareçam de maneira adequada em telas de alta resolução, como a "tela retina" do MacBook Pro, é definir os valores de largura (`width`) e altura (`height`) da imagem para a metade do arquivo original. Aqui vemos um exemplo de imagem que usa apenas metade da altura e largura originais:

```html
<style>
  img {
    height: 250px;
    width: 250px;
  }
</style>
<img src="coolPic500x500" alt="A most excellent picture" />
```

# --instructions--

Defina a largura (`width`) e a altura (`height`) da tag `img` para a metade de seus valores originais. Nesse caso, a altura (`height`) original e a largura (`width`) original são `200px`.

# --hints--

A tag `img` deve ter a propriedade `width` com o valor de 100 pixels.

```js
assert.strictEqual(document.querySelector('img').width, 100);
```

A tag `img` deve ter a propriedade `height` com o valor de 100 pixels.

```js
assert.strictEqual(document.querySelector('img').height, 100);
```

# --seed--

## --seed-contents--

```html
<style></style>

<img
  src="https://cdn.freecodecamp.org/curriculum/responsive-web-design-principles/FCCStickers-CamperBot200x200.jpg"
  alt="freeCodeCamp sticker that says 'Because CamperBot Cares'"
/>
```

# --solutions--

```html
<style>
  img {
    height: 100px;
    width: 100px;
  }
</style>

<img
  src="https://cdn.freecodecamp.org/curriculum/responsive-web-design-principles/FCCStickers-CamperBot200x200.jpg"
  alt="freeCodeCamp sticker that says 'Because CamperBot Cares'"
/>
```
