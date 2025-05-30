---
id: 5efae0543cbd2bbdab94e333
title: 步驟 32
challengeType: 0
dashedName: step-32
---

# --description--

爲了提高你剛剛添加的圖像的可訪問性，添加具有以下文本的 `alt` 屬性。

`Five cats looking around a field.`

# --hints--

你的 `figure` 元素應該有一個開始標籤。 開始標籤的書寫語法爲：`<elementName>`。

```js
assert(document.querySelectorAll('figure').length === 2);
```

你的 `figure` 元素應該有一個結束標籤。 結束標籤在 `<` 字符後面要有一個 `/`。

```js
assert(code.match(/<\/figure>/g).length === 2);
```

最後一個 `section` 元素的結束標籤的上方應該有一個 `figure` 元素。

```js
assert.strictEqual(document.querySelectorAll('main > section')?.[1]?.lastElementChild?.nodeName, 'FIGURE');
```

貓咪的 `img` 元素應該嵌套在 `figure` 元素中。

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.exists(catsImg);
```

The third image should have a `src` attribute set to `https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg`.

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.strictEqual(
  catsImg?.src?.toLowerCase(), 'https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg'
);
```

貓咪的 `img` 元素應該有一個 `alt` 屬性，其值爲 `Five cats looking around a field.`。

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.match(catsImg?.getAttribute('alt')?.replace(/\s+/g, ' '), /^Five cats looking around a field\.?$/i);
```

# --seed--

## --seed-contents--

```html
<html>
  <body>
    <main>
      <h1>CatPhotoApp</h1>
      <section>
        <h2>Cat Photos</h2>
        <p>Everyone loves <a href="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg">cute cats</a> online!</p>
        <p>See more <a target="_blank" href="https://freecatphotoapp.com">cat photos</a> in our gallery.</p>
        <a href="https://freecatphotoapp.com"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
      </section>
      <section>
        <h2>Cat Lists</h2>
        <h3>Things cats love:</h3>
        <ul>
          <li>catnip</li>
          <li>laser pointers</li>
          <li>lasagna</li>
        </ul>
        <figure>
          <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/lasagna.jpg" alt="A slice of lasagna on a plate.">
          <figcaption>Cats <em>love</em> lasagna.</figcaption>  
        </figure>
        <h3>Top 3 things cats hate:</h3>
        <ol>
          <li>flea treatment</li>
          <li>thunder</li>
          <li>other cats</li>
        </ol>
        <figure>
--fcc-editable-region--
          <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg">
--fcc-editable-region--
        </figure>
      </section>
    </main>
  </body>
</html>
```

