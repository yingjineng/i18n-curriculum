---
id: 5c6c06847491271903d37cfd
title: Usar o atributo value nos inputs do tipo radio e checkbox
challengeType: 0
forumTopicId: 301099
dashedName: use-the-value-attribute-with-radio-buttons-and-checkboxes
---

# --description--

When a form gets submitted, the data is sent to the server and includes entries for the options selected. Inputs of type `radio` and `checkbox` report their values from the `value` attribute.

Por exemplo:

```html
<label for="indoor">
  <input id="indoor" value="indoor" type="radio" name="indoor-outdoor">Indoor
</label>
<label for="outdoor">
  <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor">Outdoor
</label>
```

Aqui, temos dois inputs do tipo `radio`. Quando o usuário envia o formulário com a opção `indoor` selecionada, os dados do formulário incluirão a linha: `indoor-outdoor=indoor`. Essas informações vêm dos atributos `name` e `value` do input "indoor".

Se você omitir o atributo `value`, o formulário enviado usa o valor padrão, que é `on`. Neste cenário, mesmo que o usuário clicasse na opção "indoor" e enviasse o formulário, os dados resultantes do formulário seriam `indoor-outdoor=on`, o que não é útil. Por isso, o atributo `value` precisa ser definido com algo que identifique a opção.

# --instructions--

Dê a cada um dos inputs do tipo `radio` e do tipo `checkbox` existentes o atributo `value`. Não crie elementos novos do tipo botão de opção ou do tipo caixa de seleção. Use o texto do label do input, em letras minúsculas, como o valor do atributo.

# --hints--

Um dos botões de seleção (radio) deve ter o atributo `value` definido com o valor de `indoor`.

```js
const indoorRadioButton = [...document.querySelectorAll('label > input[type="radio"]')].filter(x => x.value === "indoor");
assert.notEmpty(indoorRadioButton)
```

Um dos botões de seleção (radio) deve ter o atributo `value` definido com o valor de `outdoor`.

```js
const outdoorRadioButton = [...document.querySelectorAll('label > input[type="radio"]')].filter(x => x.value === "outdoor");
assert.notEmpty(outdoorRadioButton);
```

Uma das caixas de seleção (checkbox) deve ter o atributo `value` definido com o valor de `loving`.

```js
const lovingCheckbox = [...document.querySelectorAll('label > input[type="checkbox"]')].filter(x => x.value === "loving");
assert.notEmpty(lovingCheckbox); 
```

Uma das caixas de seleção (checkbox) deve ter o atributo `value` definido com o valor de `lazy`.

```js
const lazyCheckbox = [...document.querySelectorAll('label > input[type="checkbox"]')].filter(x => x.value === "lazy");
assert.notEmpty(lazyCheckbox); 
```

Uma das caixas de seleção (checkbox) deve ter o atributo `value` definido com o valor de `energetic`.

```js
const energeticCheckbox =  [...document.querySelectorAll('label > input[type="checkbox"]')].filter(x => x.value === "energetic");
assert.notEmpty(energeticCheckbox);
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
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor"> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality"> Energetic</label><br>
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
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor" value="indoor"> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality" value="loving"> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality" value="lazy"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality" value="energetic"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
