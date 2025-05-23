---
id: 587d78ae367417b2b2512afe
title: Verwende die Kurzform der flex Eigenschaft
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVaDAv/cbpW2tE'
forumTopicId: 301112
dashedName: use-the-flex-shorthand-property
---

# --description--

There is a shortcut available to set several flex properties at once. The `flex-grow`, `flex-shrink`, and `flex-basis` properties can all be set together by using the `flex` property.

Zum Beispiel würde `flex: 1 0 10px;` ein Element auf `flex-grow: 1;`, `flex-shrink: 0;`, und `flex-basis: 10px;` setzen.

Die Standardwerte sind `flex: 0 1 auto;`.

# --instructions--

Füge die CSS-Eigenschaft `flex` sowohl zu `#box-1` als auch zu `#box-2` hinzu. Setze die Werte von `#box-1` so, dass `flex-grow` einen Wert von `2` hat, `flex-shrink` `2` ist und seine `flex-basis` `150px` entspricht. Weise `#box-2` Werte zu, sodass `flex-grow` `1` ist, sein `flex-shrink` `1` entspricht und eine `flex-basis` von `150px` hat.

Diese Werte werden auslösen, dass sich `#box-1` doppelt so viel ausdehnt, um Leerraum zu füllen, wie `#box-2` wenn der Container größer als 300px ist und doppelt so viel schrumpfen wie `#box-2`, wenn der Container kleiner als 300px ist. 300px ist die gemeinsame Größe der `flex-basis` Werte beider Boxen.

# --hints--

Das `#box-1` Element sollte eine `flex` Eigenschaft mit einem Wert von `2 2 150px` besitzen.

```js
const boxOne = document.querySelector('#box-1');
const flexGrow = window.getComputedStyle(boxOne)['flex-grow'];
const flexShrink = window.getComputedStyle(boxOne)['flex-shrink'];
const flexBasis = window.getComputedStyle(boxOne)['flex-basis'];

assert.equal(flexGrow, '2');
assert.equal(flexShrink, '2');
assert.equal(flexBasis, '150px');
```

Das `#box-2` Element sollte eine `flex` Eigenschaft mit einem Wert von `1 1 150px` haben.

```js
const boxTwo = document.querySelector('#box-2');
const flexGrow = window.getComputedStyle(boxTwo)['flex-grow'];
const flexShrink = window.getComputedStyle(boxTwo)['flex-shrink'];
const flexBasis = window.getComputedStyle(boxTwo)['flex-basis'];

assert.equal(flexGrow, '1');
assert.equal(flexShrink, '1');
assert.equal(flexBasis, '150px');
```

Dein Code sollte die `flex` Eigenschaft für `#box-1` und `#box-2` verwenden.

```js
assert.lengthOf(code.match(/flex:\s*?\d\s+?\d\s+?150px;/g), 2);
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
    flex: 2 2 150px;
    height: 200px;
  }

  #box-2 {
    background-color: orangered;
    flex: 1 1 150px;
    height: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
