---
id: bad87fee1348cd8acef08812
title: 創建一個 Bootstrap 塊級元素按鈕
challengeType: 0
forumTopicId: 16810
dashedName: create-a-block-element-bootstrap-button
---

# --description--

Normally, your `button` elements with the `btn` and `btn-default` classes are only as wide as the text that they contain. 舉個例子：

```html
<button class="btn btn-default">Submit</button>
```

這個按鈕的寬度應該和文本 `Submit` 的寬度相同。

<button class='btn btn-default'>Submit</button>

通過爲按鈕添加 class 屬性 `btn-block` 使其成爲塊級元素，按鈕會伸展並填滿頁面的整個水平空間，後續的元素會流到這個塊級元素的下方，即 "另起一行"。

```html
<button class="btn btn-default btn-block">Submit</button>
```

這個按鈕會 100% 佔滿所有的可用寬度。

<button class='btn btn-default btn-block'>提交</button>

注意，這些按鈕仍然需要 `btn` 這個 class。

給剛創建的 Bootstrap 按鈕添加 Bootstrap 的 `btn-block` class。

# --hints--

按鈕仍然應該有 `btn` 和 `btn-default` class。

```js
assert.isTrue(document.querySelector('button')?.classList?.contains('btn'));
assert.isTrue(document.querySelector('button')?.classList?.contains('btn-default'));
```

按鈕應該有 `btn-block` class。

```js
assert.isTrue(document.querySelector('button')?.classList?.contains('btn-block'));
```

所有 `button` 元素都應該有閉合標籤。

```js
assert.match(code,/<\/button>/g);
assert.match(code,/<button/g);
assert.equal(code.match(/<\/button>/g).length, code.match(/<button/g).length);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>

<div class="container-fluid">
  <h2 class="red-text text-center">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <button class="btn btn-default">Like</button>
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
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>

<div class="container-fluid">
  <h2 class="red-text text-center">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive" alt="Three kittens running towards the camera.">
  <button class="btn btn-block btn-default">Like</button>
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
