---
id: bad87fee1348bd9aefe08806
title: CSS 클래스를 사용하여 여러 요소의 스타일 지정하기
challengeType: 0
videoUrl: 'https://scrimba.com/c/cRkVbsQ'
forumTopicId: 18311
dashedName: style-multiple-elements-with-a-css-class
---

# --description--

클래스를 사용하면 여러 HTML 요소에 동일한 CSS 스타일을 사용할 수 있습니다. `red-text` 클래스를 첫번째 `p` 요소에 적용하면 이를 확인할 수 있습니다.

# --hints--

`h2` 요소는 빨간색이어야 합니다.

```js
const h2Element = document.querySelector('h2');
const color = window.getComputedStyle(h2Element)['color']; 
assert.strictEqual(color, 'rgb(255, 0, 0)');
```

`h2` 요소는 `red-text` 클래스가 있어야 합니다.

```js
assert.isTrue(document.querySelector('h2').classList.contains('red-text'));
```

첫 번째 `p` 요소는 빨간색이어야 합니다.

```js
const paragraph = document.querySelectorAll('p')[0];
const color = window.getComputedStyle(paragraph )['color'];
assert.strictEqual(color, 'rgb(255, 0, 0)');
```

두 번째와 세 번째 `p` 요소는 빨간색이 아니어야 합니다.

```js
const paragraph2 = document.querySelectorAll('p')[1];
const paragraph3 = document.querySelectorAll('p')[2];

const color2 = window.getComputedStyle(paragraph2)['color'];
const color3 = window.getComputedStyle(paragraph3)['color'];

assert.notStrictEqual(color2, 'rgb(255, 0, 0)');
assert.notStrictEqual(color3, 'rgb(255, 0, 0)');
```

첫 번째 `p` 요소는 `red-text` 클래스가 있어야 합니다.

```js
assert.isTrue(document.querySelectorAll('p')[0].classList.contains('red-text'));
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: red;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div>
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
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```

# --solutions--

```html
<style>
  .red-text {
    color: red;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div>
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
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
