---
id: bad87fee1348bd9aedf08820
title: 给图片添加链接
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cRdBnUr'
forumTopicId: 18327
dashedName: turn-an-image-into-a-link
---

# --description--

You can make elements into links by nesting them within an `a` element.

如果我们要把图片嵌套进 `a` 元素， 这是一个示例：

```html
<a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera."></a>
```

如果把 `a` 的 `href` 属性值设置为 `#`，创建的是一个死链接（不跳转到其他画面）。

# --instructions--

请把现存的图片嵌套进 `a`（ *锚点*）元素中。

完成后，请你把鼠标光标悬停在你的图像上， 鼠标光标将变成点击光标。 于是图片就变成了链接。

# --hints--

应将 `img` 嵌套进 `a` 元素中。

```js
const anchor = document.querySelectorAll('a')[1];
const children = anchor.querySelectorAll("img");
assert.notEmpty(children);
```

你的 `a` 元素应该是一个死链接，具有值为 `#` 的 `href` 属性。

```js
const anchor = document.querySelectorAll('a')[1];
const parentHREF = anchor.querySelector("img").parentNode.getAttribute('href');
assert.match(parentHREF,new RegExp('#'));
```

每个 `a` 元素都应该有一个结束标签。

```js
assert.match(code,/<\/a>/g);
assert.match(code,/<a/g);
assert.strictEqual(code.match(/<\/a>/g).length, code.match(/<a/g).length)
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
