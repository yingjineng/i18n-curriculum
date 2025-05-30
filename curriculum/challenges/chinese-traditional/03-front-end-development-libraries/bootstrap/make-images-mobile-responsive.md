---
id: bad87fee1348bd9acde08812
title: 使圖片自適應移動端
challengeType: 0
forumTopicId: 18232
dashedName: make-images-mobile-responsive
---

# --description--

First, add a new image below the existing one. Set its `src` attribute to `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg`.

如果圖片的大小恰恰和我們手機屏幕尺寸大小一樣自然是最好的。

幸運的是，現在通過 Bootstrap，我們僅僅只需要爲 image 標籤上設置 class 屬性爲 `img-responsive` ， 就可以讓它完美地適應你的頁面的寬度了。

# --hints--

該頁面共有兩張圖片。

```js
assert.lengthOf(document.querySelectorAll('img'), 2);
```

新的圖片應該在舊的圖片下面並且有值包含 `img-responsive` 的 class 屬性。

```js
assert.isTrue(document.querySelectorAll('img')?.[1]?.classList?.contains('img-responsive'));
```

新圖片的 class 不應該包含 `smaller-image`。

```js
assert.isFalse(document.querySelectorAll('img')?.[1]?.classList?.contains('smaller-image'));
```

新圖片應該有一個值爲 `https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg` 的 `src` 屬性。

```js
assert.equal(document.querySelectorAll('img')?.[1]?.getAttribute('src') , 'https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg');
```

確保新的 `img` 元素有一個閉合的尖括號。

```js
assert.match(code,/<img/g);
assert.lengthOf(code.match(/<img[^<]*>/g), 2);
assert.lengthOf(code.match(/<img/g), 2);
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
  <h2 class="red-text">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
  <h2 class="red-text">CatPhotoApp</h2>

  <p>Click here for <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg" class="img-responsive">

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
