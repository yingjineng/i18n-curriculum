---
id: bad88fee1348ce8acef08815
title: 使用 Bootstrap Grid 並排放置元素
challengeType: 0
forumTopicId: 18371
dashedName: use-the-bootstrap-grid-to-put-elements-side-by-side
---

# --description--

Bootstrap uses a responsive 12-column grid system, which makes it easy to put elements into rows and specify each element's relative width. Most of Bootstrap's classes can be applied to a `div` element.

Bootstrap 有不同的列寬屬性，它根據用戶的屏幕寬度來使用相應的寬度。 比如，手機的屏幕窄，而筆記本電腦的屏幕更寬。

以 Bootstrap 的 `col-md-*` class 爲例， 在這裏， `md` 表示 medium （中等的）， 而 `*` 是一個數字，說明了這個元素佔有多少個列寬度。 這個例子就是指定了中等大小屏幕（例如筆記本電腦）下元素所佔的列寬度。

在 Cat Photo App 中，將使用 `col-xs-*` ， 其中 `xs` 是 extra small 的縮寫 (比如窄屏手機屏幕)， `*` 是填寫的數字，代表一行中的元素該佔多少列寬。

將 `Like`、`Info` 和 `Delete` 三個按鈕並排放入一個 `<div class="row">` 元素中，然後將每個按鈕都各用一個 `<div class="col-xs-4">` 元素包裹起來。

當 `div` 元素設置了 `row` class 之後，那幾個按鈕便會嵌入其中了。

# --hints--

所有按鈕都需要嵌入到同一個 `div` 元素中， 並且該元素包含 `row` class 屬性。

```js
const row = document.querySelector('div.row');
const rowChildren = row?.querySelectorAll(`:scope ${'button'}`); 
assert.lengthOf(rowChildren, 3);
```

每個 Bootstrap 按鈕都需要嵌入各自的 `div` 元素，並且該元素包含 class 屬性 `col-xs-4`。

```js
const columns = document.querySelectorAll('div.col-xs-4');

const firstButton = columns?.[0]?.querySelectorAll(`:scope ${'button'}`)
assert.lengthOf(firstButton,1);

const secondButton = columns?.[1]?.querySelectorAll(`:scope ${'button'}`)
assert.lengthOf(secondButton,1);

const thirdButton = columns?.[2]?.querySelectorAll(`:scope ${'button'}`)
assert.lengthOf(thirdButton,1);

```

確保每一個 `button` 元素都有一個閉合標籤。

```js
assert.match(code,/<\/button>/g);
assert.match(code,/<button/g);
assert.equal(code.match(/<\/button>/g).length , code.match(/<button/g).length);
```

確保每一個 `div` 元素都有一個閉合標籤。

```js
assert.match(code,/<\/div>/g);
assert.match(code,/<div/g);
assert.equal(code.match(/<\/div>/g).length , code.match(/<div/g).length);
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
  <button class="btn btn-block btn-primary">Like</button>
  <button class="btn btn-block btn-info">Info</button>
  <button class="btn btn-block btn-danger">Delete</button>
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
