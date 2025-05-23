---
id: 56533eb9ac21ba0edf2244bf
title: Ambito locale e funzioni
challengeType: 1
forumTopicId: 18227
dashedName: local-scope-and-functions
---

# --description--

Variables which are declared within a function, as well as the function parameters, have <dfn>local</dfn> scope. That means they are only visible within that function.

Ecco una funzione `myTest` con una variabile locale chiamata `loc`.

```js
function myTest() {
  const loc = "foo";
  console.log(loc);
}

myTest();
console.log(loc);
```

La chiamata alla funzione `myTest()` mostrerà la stringa `foo` nella console. La riga `console.log(loc)` (al di fuori della funzione `myTest`) lancerà un errore visto che `loc` non è definito al di fuori della funzione.

# --instructions--

L'editor ha due `console.log` per aiutarti a vedere cosa sta succedendo. Controlla la console mentre scrivi il codice per vedere come cambia. Dichiara una variabile locale `myVar` all'interno di `myLocalScope` ed esegui i test.

**Nota:** La console mostrerà ancora `ReferenceError: myVar is not defined`, ma questo non causerà il fallimento dei test.

# --hints--

Il codice non dovrebbe contenere una variabile globale `myVar`.

```js
function declared() {
  myVar;
}

assert.throws(declared, ReferenceError);
```

Dovresti aggiungere una variabile locale `myVar`.

```js
assert(
  /functionmyLocalScope\(\)\{.*(var|let|const)myVar[\s\S]*}/.test(
    __helpers.removeWhiteSpace(__helpers.removeJSComments(code))
  )
);
```

# --seed--

## --seed-contents--

```js
function myLocalScope() {
  // Only change code below this line

  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```

# --solutions--

```js
function myLocalScope() {
  // Only change code below this line
  let myVar;
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```
