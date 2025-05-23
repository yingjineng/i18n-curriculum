---
id: 587d78ad367417b2b2512afb
title: Usare la proprietà flex-shrink per ridurre gli oggetti
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVaDAv/cd3PBfr'
forumTopicId: 301113
dashedName: use-the-flex-shrink-property-to-shrink-items
---

# --description--

So far, all the properties in the challenges apply to the flex container (the parent of the flex items). However, there are several useful properties for the flex items.

La prima è la proprietà `flex-shrink`. Quando viene usata, permette ad un oggetto di rimpicciolirsi se il contenitore flex è troppo piccolo. Gli oggetti si restringono quando la larghezza del contenitore genitore è minore delle larghezze combinate di tutti gli elementi flex al suo interno.

La proprietà `flex-shrink` utilizza i numeri come valori. Più alto è il numero, più si ridurrà rispetto agli altri oggetti nel contenitore. Ad esempio, se un elemento ha un valore `flex-shrink` di `1` e l'altro ha un valore `flex-shrink` di `3`, quello con il valore di `3` si ridurrà tre volte più dell'altro.

# --instructions--

Aggiungi la proprietà CSS `flex-shrink` sia a `#box-1` che a `#box-2`. Dai a `#box-1` un valore di `1` e `#box-2` un valore di `2`.

# --hints--

L'elemento `#box-1` dovrebbe avere la proprietà `flex-shrink` impostata su un valore di `1`.

```js
const boxOne = document.querySelector('#box-1');
const flexShrink = window.getComputedStyle(boxOne)['flex-shrink'];
assert.equal(flexShrink, '1');
```

L'elemento `#box-2` dovrebbe avere la proprietà `flex-shrink` impostata su un valore di `2`.

```js
const boxTwo = document.querySelector('#box-2');
const flexShrink = window.getComputedStyle(boxTwo)['flex-shrink'];
assert.equal(flexShrink, '2');
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
    width: 100%;
    height: 200px;

  }

  #box-2 {
    background-color: orangered;
    width: 100%;
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
    width: 100%;
    height: 200px;
    flex-shrink: 1;
  }

  #box-2 {
    background-color: orangered;
    width: 100%;
    height: 200px;
    flex-shrink: 2;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
