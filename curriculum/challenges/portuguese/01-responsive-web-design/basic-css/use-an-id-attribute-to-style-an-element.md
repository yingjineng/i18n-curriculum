---
id: bad87dee1348bd9aede07836
title: Usar um atributo id para definir o estilo de um elemento
challengeType: 0
videoUrl: 'https://scrimba.com/c/cakyZfL'
forumTopicId: 18339
dashedName: use-an-id-attribute-to-style-an-element
---

# --description--

One cool thing about `id` attributes is that, like classes, you can style them using CSS.

No entanto, um `id` não é reutilizável e deve ser aplicado apenas a um elemento. Um `id` também tem uma especificidade (importância) mais alta do que uma classe, portanto, se ambos forem aplicados ao mesmo elemento e tiverem estilos conflitantes, os estilos do `id` serão aplicados.

Aqui está um exemplo de como você pode pegar seu elemento com o atributo `id` de `cat-photo-element` e dar a ele a cor de fundo verde. No elemento `style`:

```css
#cat-photo-element {
  background-color: green;
}
```

Observe que, dentro do elemento `style`, você sempre faz referência às classes colocando um `.` na frente de seus nomes. Você sempre faz referência aos ids colocando um `#` na frente de seus nomes.

# --instructions--

Tente dar ao seu formulário, que agora tem o atributo `id` de `cat-photo-form`, um fundo verde.

# --hints--

O elemento `form` deve ter o atributo id com o valor `cat-photo-form`.

```js
assert.strictEqual(document.querySelector('form').getAttribute('id'), 'cat-photo-form');
```

O elemento `form` deve ter a propriedade `background-color` com o valor green (verde).

```js
const catPhotoForm = document.querySelector('#cat-photo-form');
const backgroundColor = window.getComputedStyle(catPhotoForm)['background-color'];
assert.strictEqual(backgroundColor, 'rgb(0, 128, 0)');
```

O elemento `form` deve ter um atributo `id`.

```js
assert.match(__helpers.removeHtmlComments(code), /<form.*cat-photo-form.*>/gi);
assert.lengthOf(__helpers.removeHtmlComments(code).match(/<form.*cat-photo-form.*>/gi), 1)
```

Você não deve fornecer ao `form` os atributos `class` ou `style`.

```js
assert.notMatch(__helpers.removeHtmlComments(code), /<form.*style.*>/gi);
assert.notMatch(__helpers.removeHtmlComments(code), /<form.*class.*>/gi);
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
    font-family: Lobster, monospace;
  }

  p {
    font-size: 16px;
    font-family: monospace;
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

  .silver-background {
    background-color: silver;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div class="silver-background">
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

  <form action="https://freecatphotoapp.com/submit-cat-photo" id="cat-photo-form">
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

  h2 {
    font-family: Lobster, monospace;
  }

  p {
    font-size: 16px;
    font-family: monospace;
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

  .silver-background {
    background-color: silver;
  }

  #cat-photo-form {
    background-color: green;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div class="silver-background">
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

  <form action="https://freecatphotoapp.com/submit-cat-photo" id="cat-photo-form">
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
