---
id: bad87fee1348bd9aede08830
title: 創建一個表單
challengeType: 0
forumTopicId: 16817
dashedName: create-a-form-element
---

# --description--

You can build web forms that actually submit data to a server using nothing more than pure HTML. You can do this by specifying an `action` attribute on your `form` element.

舉個例子：

```html
<form action="url-where-you-want-to-submit-form-data">
  <input>
</form>
```

# --instructions--

把現有的 `input` 元素嵌套到一個表單 `form` 元素裏，然後設置 `form` 元素的 `action` 屬性值爲 `"https://www.freecatphotoapp.com/submit-cat-photo"`。

# --hints--

現有的 `input` 輸入框應位於新創建的 `form` 表單裏面。

```js
const inputElem = document.querySelector('form input');
assert.strictEqual(inputElem.getAttribute('type'),'text'); 
assert.strictEqual(inputElem.getAttribute('placeholder'),'cat photo URL');
```

`form` 的 `action` 屬性值應爲 `https://www.freecatphotoapp.com/submit-cat-photo`。

```js
const action = document.querySelector('form').getAttribute('action');
assert.match(action,/^https:\/\/(www\.)?freecatphotoapp\.com\/submit-cat-photo$/i);
```

`form` 元素應有開始標籤和結束標籤。

```js
assert.match(code,/<\/form>/g);
assert.match(code,/<form [^<]*>/g);
assert.strictEqual(code.match(/<\/form>/g).length,code.match(/<form [^<]*>/g).length);
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
  <input type="text" placeholder="cat photo URL">
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <input type="text" placeholder="cat photo URL">
  </form>
</main>
```
