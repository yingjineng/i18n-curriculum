---
id: bad87fee1348bd9aedf08827
title: Criar uma lista não ordenada de itens
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cDKVPuv'
forumTopicId: 16814
dashedName: create-a-bulleted-unordered-list
---

# --description--

HTML has a special element for creating <dfn>unordered lists</dfn>, or bullet point style lists.

Listas não ordenadas começam com o elemento `<ul>`, seguido por uma quantidade qualquer de elementos `<li>`. Por fim, são fechadas com a tag `</ul>`.

Por exemplo:

```html
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

cria uma lista de estilo itemizado de `milk` e `cheese`.

# --instructions--

Remova os dois últimos elementos `p` e crie uma lista não ordenada de três coisas que os gatos adoram na parte inferior da página.

# --hints--

Crie um elemento `ul`.

```js
assert.isNotEmpty(document.querySelectorAll('ul'));
```

Você precisa de três elementos `li` dentro do elemento `ul`.

```js
assert.lengthOf(document.querySelectorAll('ul li'),3);
```

O elemento `ul` deve ter uma tag de fechamento.

```js
assert.match(code,/<\/ul>/gi);
assert.match(code,/<ul/gi);
assert.strictEqual(code.match(/<\/ul>/gi).length,code.match(/<ul/gi).length);
```

Os elementos `li` devem ter tags de fechamento.

```js
assert.match(code,/<\/li>/gi);
assert.match(code,/<li[\s>]/gi);
assert.strictEqual(code.match(/<\/li>/gi).length,code.match(/<li[\s>]/gi).length);
```

Os elementos `li` não devem estar vazios ou ter espaços em branco.

```js
assert.isEmpty([...document.querySelectorAll('ul li')].filter((item) => item.textContent.trim() === ""));
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <ul>
    <li>milk</li>
    <li>mice</li>
    <li>catnip</li>
  </ul>
</main>
```
