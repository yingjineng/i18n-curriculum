---
id: bad87fee1348bd9aedf08845
title: 使用 span 创建行内元素
challengeType: 0
forumTopicId: 18370
dashedName: use-a-span-to-target-inline-elements
---

# --description--

You can use spans to create inline elements. Remember when we used the `btn-block` class to make the button fill the entire row?

<button class='btn' style='background-color: rgb(0, 100, 0);  color: rgb(255, 255, 255);'>normal button</button>

<button class='btn btn-block' style='background-color: rgb(0, 100, 0);  color: rgb(255, 255, 255);'>块级按钮</button>

上面的例子就是 "inline" （行内）元素和 "block" （块级）元素的区别。

通过使用行内元素 `span`，可以把不同的元素放在同一行，甚至能为一行的不同部分指定不同样式。

使用一个 `span` 元素，将文本 `love` 嵌入现在包含文本 `Things cats love` 的 `p` 元素中。 然后给 `span` 元素设置 class `text-danger`，使文本变成红色。

对含有文本 `Top 3 things cats hate` 的 `p` 元素这样处理：

```html
<p>Top 3 things cats <span class="text-danger">hate:</span></p>
```

# --hints--

`span` 元素应该在 `p` 元素内。

```js
assert.lengthOf(document.querySelectorAll('p span'),1);
```

`span` 元素应该有文本 `love`。

```js
assert.match(document.querySelector('p span')?.textContent,/love/i);
assert.notMatch(document.querySelector('p span')?.textContent, /Things cats/i);
```

`span` 元素应该有 `text-danger` class。

```js
assert.isTrue(document.querySelector('span')?.classList?.contains('text-danger'));
```

`span` 元素应该有一个闭合标签。

```js
assert.match(code,/<\/span>/g);
assert.match(code,/<span/g);
assert.equal(code.match(/<\/span>/g).length,code.match(/<span/g).length);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>

  h2 {
    font-family: Lobster, Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

</style>

<div class="container-fluid">
  <h2 class="text-primary text-center">CatPhotoApp</h2>

  <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats love:</p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```

# --solutions--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>

  h2 {
    font-family: Lobster, Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

</style>

<div class="container-fluid">
  <h2 class="text-primary text-center">CatPhotoApp</h2>

  <a href="#"><img class="img-responsive thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <div class="row">
    <div class="col-xs-4">
      <button class="btn btn-block btn-primary">Like</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-info">Info</button>
    </div>
    <div class="col-xs-4">
      <button class="btn btn-block btn-danger">Delete</button>
    </div>
  </div>
  <p>Things cats <span class="text-danger">love</span>:</p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>
  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor"> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
    <label><input type="checkbox" name="personality"> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Crazy</label>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</div>
```
