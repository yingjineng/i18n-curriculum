---
id: 587d78b1367417b2b2512b09
title: Ein Bild responsiv gestalten
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

Die `max-width` von `100%` sorgt dafür, dass das Bild nie breiter ist als der Container, in dem es sich befindet, und die `height` von `auto` sorgt dafür, dass das Bild sein ursprüngliches Seitenverhältnis behält.

# --instructions--

Füge die Stilregeln zur Klasse `responsive-img` hinzu, um sie responsive zu gestalten. Es sollte nie größer als sein Container sein (in diesem Fall ist es das Vorschaufenster) und es sollte sein ursprüngliches Seitenverhältnis beibehalten. Nachdem du deinen Code hinzugefügt hast, kannst du die Größe der Vorschau ändern, um zu sehen, wie sich deine Bilder verhalten.

# --hints--

Deine Klasse `responsive-img` sollte eine `max-width` besitzen, die auf `100%` gesetzt ist.

```js
assert.strictEqual(getComputedStyle(document.querySelector('.responsive-img')).maxWidth, '100%');
```

Deine Klasse `responsive-img` sollte eine `height` besitzen, die auf `auto` eingestellt ist.

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
