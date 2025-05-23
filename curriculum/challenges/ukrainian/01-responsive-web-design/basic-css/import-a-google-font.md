---
id: bad87fee1348bd9aedf08807
title: Імпорт шрифтів з Google Font
challengeType: 0
videoUrl: 'https://scrimba.com/c/cM9MRsJ'
forumTopicId: 18200
dashedName: import-a-google-font
---

# --description--

In addition to specifying common fonts that are found on most operating systems, we can also specify non-standard, custom web fonts for use on our website. There are many sources for web fonts on the Internet. For this example we will focus on the Google Fonts library.

Google Fonts – це безоплатна бібліотека вебшрифтів, які можна використати у CSS, посилаючись на URL-адресу шрифту.

Що ж, давайте почнемо імпортувати і застосувати шрифт Google (зауважте, що якщо Google заблокований у вашій країні, то вам потрібно пропустити це завдання).

Щоб імпортувати шрифт Google, можна скопіювати URL-адресу шрифту з бібліотеки Google Fonts, а потім вставити її у свій HTML. У цьому завданні ми імпортуємо шрифт `Lobster`. Для цього скопіюйте наступний фрагмент коду і вставте його у верхній частині вашого редактора коду (перед відкриттям елемента `style`):

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```

Тепер ви можете використовувати шрифт `Lobster` у вашому CSS, скориставшись `Lobster` як FAMILY_NAME як і у прикладі нижче:

```css
font-family: FAMILY_NAME, GENERIC_NAME;
```

GENERIC_NAME не є обов'язковим, і є резервним шрифтом, якщо інший вказаний шрифт недоступний. Це розглядається в наступному завданні.

Назви шрифтів чутливі до регістру і повинні бути поміщені в лапки, якщо у назві є пробіл. Наприклад, вам потрібні лапки для використання шрифту `"Open Sans"`, але для шрифту `Lobster` — ні.

# --instructions--

Імпортуйте шрифт `Lobster` на вашу веб-сторінку. Потім скористайтеся селектором елементів для встановлення `Lobster` у якості `font-family` для вашого елемента `h2`.

# --hints--

Вам слід імпортувати шрифт `Lobster`.

```js
assert.exists(document.querySelector('link[href*="googleapis" i]'));
```

Елемент `h2` має використовувати шрифт `Lobster`.

```js
const h2 = document.querySelector('h2'); 
const fontFamily = window.getComputedStyle(h2)['font-family']; 
assert.match(fontFamily, /lobster/i);
```

Ви повинні використовувати селектор елементу `h2`, щоб змінити шрифт.

```js
assert.match(__helpers.removeHtmlComments(code), /\s*[^\.]h2\s*\{\s*font-family\s*:\s*('|"|)Lobster\1\s*(,\s*('|"|)[a-z -]+\3\s*)?(;\s*\}|\})/gi);
```

Елемент `p` все ще повинен використовувати шрифт `monospace`.

```js
const paragraphElement = document.querySelector('p');
const fontFamily = window.getComputedStyle(paragraphElement)['font-family']; 
assert.match(fontFamily, /monospace/i);
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: red;
  }

  p {
    font-size: 16px;
    font-family: monospace;
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

# --solutions--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  p {
    font-size: 16px;
    font-family: monospace;
  }

  h2 {
    font-family: Lobster;
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
