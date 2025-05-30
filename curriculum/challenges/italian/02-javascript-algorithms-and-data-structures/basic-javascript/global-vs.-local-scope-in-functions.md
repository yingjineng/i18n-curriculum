---
id: 56533eb9ac21ba0edf2244c0
title: Ambito globale e ambito locale nelle funzioni
challengeType: 1
forumTopicId: 18194
dashedName: global-vs--local-scope-in-functions
---

# --description--

It is possible to have both <dfn>local</dfn> and <dfn>global</dfn> variables with the same name. When you do this, the local variable takes precedence over the global variable.

In questo esempio:

```js
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```

La funzione `myFun` restituirà la stringa `Head` perché è presente la versione locale della variabile.

# --instructions--

Aggiungi una variabile locale alla funzione `myOutfit` per sovrascrivere il valore di `outerWear` con la stringa `sweater`.

# --hints--

Non dovresti cambiare il valore della variabile globale `outerWear`.

```js
assert(outerWear === 'T-Shirt');
```

`myOutfit` dovrebbe restituire la stringa `sweater`.

```js
assert(myOutfit() === 'sweater');
```

Non dovresti cambiare l'istruzione return.

```js
assert(/return outerWear/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --seed-contents--

```js
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line

  // Only change code above this line
  return outerWear;
}

myOutfit();
```

# --solutions--

```js
const outerWear = "T-Shirt";
function myOutfit() {
  const outerWear = "sweater";
  return outerWear;
}
```
