---
id: 587d78b1367417b2b2512b0c
title: Створення адаптивної типографії
challengeType: 0
videoUrl: 'https://scrimba.com/p/pzrPu4/crzN7T8'
forumTopicId: 301141
dashedName: make-typography-responsive
---

# --description--

Instead of using `em` or `px` to size text, you can use viewport units for responsive typography. Viewport units, like percentages, are relative units, but they are based off different items. Viewport units are relative to the viewport dimensions (width or height) of a device, and percentages are relative to the size of the parent container element.

Чотири різних одиниць області перегляду:

<ul><li><code>vw</code> (viewport width): <code>10vw</code> would be 10% of the viewport's width.</li><li><code>vh</code> (висота перегляду): <code>3vh</code> складатиме 3% від висоти області перегляду.</li><li><code>vmin</code> (мінімальний перегляд): <code>70vmin</code> складатиме 70% від найменшого розміру області перегляду (висоти чи ширини).</li><li><code>vmax</code> (максимальний перегляд): <code>100vmax</code> складатиме 100% від найбільшого розміру області перегляду (висоти чи ширини).</li></ul>

Ось приклад, який встановлює тег `body` на 30% від ширини області перегляду.

```css
body {
  width: 30vw;
}
```

# --instructions--

Встановіть `width` тегу `h2` на 80% від ширини області перегляду, а `width` абзацу - на 75% від найменшого розміру області перегляду.

# --hints--

Ваш тег `h2` повинен містити `width` 80vw.

```js
assert.match(
  __helpers.removeCssComments(code),
  /h2\s*?{\s*?width:\s*?80vw;\s*?}/g
);
```

Ваш тег `p` повинен містити `width` 75vmin.

```js
assert.match(
  __helpers.removeCssComments(code),
  /p\s*?{\s*?width:\s*?75vmin;\s*?}/g
);
```

# --seed--

## --seed-contents--

```html
<style>

</style>

<h2>Importantus Ipsum</h2>
<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus quis tempus
  massa. Aenean erat nisl, gravida vel vestibulum cursus, interdum sit amet
  lectus. Sed sit amet quam nibh. Suspendisse quis tincidunt nulla. In hac
  habitasse platea dictumst. Ut sit amet pretium nisl. Vivamus vel mi sem.
  Aenean sit amet consectetur sem. Suspendisse pretium, purus et gravida
  consequat, nunc ligula ultricies diam, at aliquet velit libero a dui.
</p>
```

# --solutions--

```html
<style>
  h2 {
    width: 80vw;
  }
  p {
    width: 75vmin;
  }
</style>

<h2>Importantus Ipsum</h2>
<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus quis tempus
  massa. Aenean erat nisl, gravida vel vestibulum cursus, interdum sit amet
  lectus. Sed sit amet quam nibh. Suspendisse quis tincidunt nulla. In hac
  habitasse platea dictumst. Ut sit amet pretium nisl. Vivamus vel mi sem.
  Aenean sit amet consectetur sem. Suspendisse pretium, purus et gravida
  consequat, nunc ligula ultricies diam, at aliquet velit libero a dui.
</p>
```
