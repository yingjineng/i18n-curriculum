---
id: 5efada803cbd2bbdab94e332
title: Крок 31
challengeType: 0
dashedName: step-31
---

# --description--

В межах елемента `figure`, який ви щойно додали, вкладіть елемент `img` з атрибутом `src` зі значенням `https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg`.

# --hints--

Другий елемент `figure` повинен мати початковий тег. Початкові теги мають такий синтаксис: `<elementName>`.

```js
assert.isAtLeast(document.querySelectorAll('figure').length, 2);
```

Другий елемент `figure` повинен мати кінцевий тег. Кінцеві теги мають `/` одразу після символу `<`.

```js
assert.isAtLeast(code.match(/<\/figure>/g)?.length, 2);
```

Одразу над кінцевим тегом другого елемента `section` має бути другий елемент `figure`. Вони знаходяться в неправильному порядку.

```js
assert.equal(document.querySelectorAll('main > section')[1]?.lastElementChild.nodeName, 'FIGURE');
```

Третій елемент `img` має бути вкладеним в елементі `figure`.

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.exists(
  catsImg
);
```

Третє зображення повинне мати атрибут `src` зі значенням `https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg`.

```js
const catsImg = document.querySelectorAll('figure > img')[1];
assert.equal(
    catsImg?.getAttribute('src')?.toLowerCase(), 'https://cdn.freecodecamp.org/curriculum/cat-photo-app/cats.jpg'
);
```

Хоча ви встановили значення атрибута `src` нового зображення як правильне посилання, значення атрибута краще писати в лапках.

```js
assert.notMatch(code, /\<img\s+.+\s+src\s*=\s*https:\/\/cdn\.freecodecamp\.org\/curriculum\/cat-photo-app\/cats\.jpg/);
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
--fcc-editable-region--
        <figure>

        </figure>
--fcc-editable-region--
      </section>
    </main>
  </body>
</html>
```
