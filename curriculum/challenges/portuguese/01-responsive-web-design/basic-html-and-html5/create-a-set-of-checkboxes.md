---
id: bad87fee1348bd9aedf08835
title: Criar um grupo de caixas de seleção
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cqrkJsp'
forumTopicId: 16821
dashedName: create-a-set-of-checkboxes
---

# --description--

Forms commonly use <dfn>checkboxes</dfn> for questions that may have more than one answer.

As caixas de seleção são um tipo de `input`.

Cada uma das caixas de seleção deve estar dentro de seu próprio elemento `label`. Ao envolver um elemento `input` em um elemento `label`, este último vai estar automaticamente associado ao input da caixa de seleção em questão.

Todos os inputs de caixa de seleção correspondentes a uma mesma pergunta devem ter o atributo `name` de mesmo valor.

É uma prática recomendada definir claramente a relação entre o `input` de uma caixa de seleção e seu elemento `label` correspondente por meio da definição do atributo `for` no elemento `label`, de modo que este atributo corresponda ao atributo `id` associado ao elemento `input`.

Aqui vemos um exemplo de caixa de seleção:

```html
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
```

# --instructions--

Adicione ao formulário um grupo de três caixas de seleção. Cada caixa de seleção deve estar dentro de seu próprio elemento `label`. As três devem compartilhar o atributo `name` de valor `personality`.

# --hints--

A página deve ter três elementos de caixa de seleção.

```js
assert.lengthOf(document.querySelectorAll('input[type="checkbox"]'),3);
```

Cada uma das três caixas de seleção deve estar dentro de seu próprio elemento `label`.

```js
assert.lengthOf(document.querySelectorAll('label > input[type="checkbox"]:only-child'),3);
```

Verifique se cada um dos elementos `label` tem uma tag de fechamento.

```js
assert.match(code,/<\/label>/g);
assert.match(code,/<label/g);
assert.strictEqual(code.match(/<\/label>/g).length,code.match(/<label/g).length)
```

As caixas de seleção devem ter o atributo `name` com o valor de `personality`.

```js
assert.lengthOf([...document.querySelectorAll('label > input[type="checkbox"]')].filter(x => x.name === "personality"),3);
```

Todas as suas caixas de seleção dever ser adicionadas dentro da tag `form`.

```js
assert.strictEqual(document.querySelector('label').parentNode.tagName,'FORM');
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
    <label for="playful"><input id="playful" type="checkbox" name="personality">Playful</label>
    <label for="lazy"><input id="lazy" type="checkbox" 
name="personality">Lazy</label>
    <label for="evil"><input id="evil" type="checkbox" 
name="personality">Evil</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
