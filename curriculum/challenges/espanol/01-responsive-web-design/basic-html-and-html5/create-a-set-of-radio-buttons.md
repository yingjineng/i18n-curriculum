---
id: bad87fee1348bd9aedf08834
title: Crea un conjunto de botones de radio
challengeType: 0
forumTopicId: 16822
dashedName: create-a-set-of-radio-buttons
---

# --description--

Puedes usar <dfn>botones de radio</dfn> para preguntas en las que quieres que el usuario solo te dé una respuesta a partir de múltiples opciones.

Los botones de radio son un tipo de entrada `input`.

Cada uno de tus botones de radio puede anidarse dentro de su propio elemento `label`. Envolver un elemento `input` dentro de un elemento `label` asociará automáticamente la entrada del botón de radio con el elemento label que lo rodea.

Todos los botones de radio relacionados deben tener el mismo atributo `name` para crear un grupo de botones de radio. Al crear un grupo de radio, si se selecciona cualquier botón de radio se deselecciona automáticamente los otros botones dentro del mismo grupo, asegurándose que el usuario proporcione solo una respuesta.

Aquí hay un ejemplo de un botón de radio:

```html
<label> 
  <input type="radio" name="indoor-outdoor">Indoor 
</label>
```

Se considera buena práctica establecer un atributo `for` en el elemento `label`, con un valor que coincida con el valor del atributo `id` del elemento `input`. Esto permite a las tecnologías asistivas establecer una relación de vínculo entre la etiqueta y el elemento `input` relacionado. Por ejemplo:

```html
<input id="indoor" type="radio" name="indoor-outdoor">
<label for="indoor">Indoor</label>
```

También podemos anidar el elemento `input` dentro de las etiquetas `label`:

```html
<label for="indoor"> 
  <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
</label>
```

# --instructions--

Añade un par de botones de radio a tu formulario, cada uno de ellos anidado en su propio elemento `label`. Uno debe tener la opción de `indoor` y el otro debe tener la opción de `outdoor`. Ambos deben compartir el atributo `name` de `indoor-outdoor` para crear un grupo de radio.

# --hints--

Tu página debe tener dos elementos de botón de `radio`.

```js
assert.lengthOf(document.querySelectorAll('input[type="radio"]'),2);
```

Tus botones de radio deben poseer el atributo `name` con el valor `indoor-outdoor`.

```js
assert.lengthOf([...document.querySelectorAll('input[type="radio"]')].filter(input => input.name === "indoor-outdoor"),2);
```

Cada uno de tus dos elementos de botón de radio debe estar anidado en su propio elemento `label`.

```js
assert.lengthOf(document.querySelectorAll('label > input[type="radio"]:only-child'),2);
```

Cada uno de tus elementos `label` debe tener una etiqueta de cierre.

```js
assert.match(code,/<\/label>/g);
assert.match(code,/<label/g);
assert.strictEqual(code.match(/<\/label>/g).length,code.match(/<label/g).length);
```

Uno de tus botones de radio debe tener la etiqueta `indoor`.

```js
const labelTexts = [...document.querySelectorAll('label')].map(label => label.textContent);
const hasMatch = labelTexts.some(label =>  label.match(/indoor/gi));
assert.isTrue(hasMatch); 
```

Uno de tus botones de radio debe tener la etiqueta `outdoor`.

```js
const labelTexts = [...document.querySelectorAll('label')].map(label => label.textContent);
const hasMatch = labelTexts.some(label => label.match(/outdoor/gi));
assert.isTrue(hasMatch); 
```

Cada uno de tus elementos de botón de radio debe ser agregado dentro de la etiqueta `form`.

```js
const labelParent = document.querySelector('label').parentNode;
assert.strictEqual(labelParent.tagName,'FORM');
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
  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
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
   <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor"> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
