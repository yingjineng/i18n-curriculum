---
id: bad87fee1348bd9aec908855
title: Dale un id único a cada elemento
challengeType: 0
forumTopicId: 18191
dashedName: give-each-element-a-unique-id
---

# --description--

También vamos a querer poder usar jQuery para seleccionar cada botón por su id único.

Dale a cada uno de tus botones un id único, empezando con `target1` y finalizando con `target6`.

Asegúrate de que `target1` a `target3` se encuentren en `#left-well` y `target4` a `target6` se encuentren en `#right-well`.

# --hints--

Un elemento `button` debe tener el id `target1`.

```js
const leftWall = document.querySelector('#left-well'); 
const targetOne = leftWall?.querySelectorAll(`:scope ${'#target1'}`)
assert.lengthOf(targetOne,1);
```

Un elemento `button` debe tener el id `target2`.

```js
const leftWall = document.querySelector('#left-well'); 
const targetTwo = leftWall?.querySelectorAll(`:scope ${'#target2'}`)
assert.lengthOf(targetTwo,1);
```

Un elemento `button` debe tener el id `target3`.

```js
const leftWall = document.querySelector('#left-well'); 
const targetThree = leftWall?.querySelectorAll(`:scope ${'#target3'}`)
assert.lengthOf(targetThree,1);
```

Un elemento `button` debe tener el id `target4`.

```js
const leftWall = document.querySelector('#right-well'); 
const targetFour = leftWall?.querySelectorAll(`:scope ${'#target4'}`)
assert.lengthOf(targetFour,1);
```

Un elemento `button` debe tener el id `target5`.

```js
const leftWall = document.querySelector('#right-well'); 
const targetFive = leftWall?.querySelectorAll(`:scope ${'#target5'}`)
assert.lengthOf(targetFive,1);
```

Un elemento `button` debe tener el id `target6`.

```js
const leftWall = document.querySelector('#right-well'); 
const targetSix = leftWall?.querySelectorAll(`:scope ${'#target6'}`)
assert.lengthOf(targetSix,1);
```

# --seed--

## --seed-contents--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
        <button class="btn btn-default target"></button>
      </div>
    </div>
  </div>
</div>
```

# --solutions--

```html
<div class="container-fluid">
  <h3 class="text-primary text-center">jQuery Playground</h3>
  <div class="row">
    <div class="col-xs-6">
      <h4>#left-well</h4>
      <div class="well" id="left-well">
        <button class="btn btn-default target" id="target1"></button>
        <button class="btn btn-default target" id="target2"></button>
        <button class="btn btn-default target" id="target3"></button>
      </div>
    </div>
    <div class="col-xs-6">
      <h4>#right-well</h4>
      <div class="well" id="right-well">
        <button class="btn btn-default target" id="target4"></button>
        <button class="btn btn-default target" id="target5"></button>
        <button class="btn btn-default target" id="target6"></button>
      </div>
    </div>
  </div>
</div>
```
