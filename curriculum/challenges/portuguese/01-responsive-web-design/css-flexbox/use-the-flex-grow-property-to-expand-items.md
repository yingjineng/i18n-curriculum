---
id: 587d78ae367417b2b2512afc
title: Usar a propriedade flex-grow para expandir flex items
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVaDAv/c2p78cg'
forumTopicId: 301111
dashedName: use-the-flex-grow-property-to-expand-items
---

# --description--

The opposite of `flex-shrink` is the `flex-grow` property. Recall that `flex-shrink` controls the size of the items when the container shrinks. The `flex-grow` property controls the size of items when the parent container expands.

Usando um exemplo semelhante ao do último desafio, se um item tem um `flex-grow` com o valor de `1` e o outro tem um `flex-grow` com o valor de `3`, aquele com o valor de `3` crescerá três vezes mais do que o outro.

# --instructions--

Adicione a propriedade CSS `flex-grow` aos elementos de id `#box-1` e `#box-2`. Dê para `#box-1` o valor `1` e `#box-2` o valor `2`.

# --hints--

O elemento de id `#box-1` deve ter a propriedade `flex-grow` com o valor de `1`.

```js
const boxOne = document.querySelector('#box-1');
const flexGrow = window.getComputedStyle(boxOne)['flex-grow'];
assert.equal(flexGrow, '1');
```

O elemento de id `#box-2` deve ter a propriedade `flex-grow` com o valor de `2`.

```js
const boxTwo = document.querySelector('#box-2');
const flexGrow = window.getComputedStyle(boxTwo)['flex-grow'];
assert.equal(flexGrow, '2');
```

# --seed--

## --seed-contents--

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;

  }

  #box-2 {
    background-color: orangered;
    height: 200px;

  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

# --solutions--

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-grow: 1;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-grow: 2;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
