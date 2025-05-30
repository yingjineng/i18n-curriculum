---
id: cf1111c1c12feddfaeb3bdef
title: Usare la logica condizionale con le istruzioni If
challengeType: 1
forumTopicId: 18348
dashedName: use-conditional-logic-with-if-statements
---

# --description--

`if` statements are used to make decisions in code. The keyword `if` tells JavaScript to execute the code in the curly braces under certain conditions, defined in the parentheses. These conditions are known as `Boolean` conditions and they may only be `true` or `false`.

Quando la condizione valuta un `true`, il programma esegue la dichiarazione all'interno delle parentesi graffe. Quando la condizione booleana valuta un `false`, la dichiarazione all'interno delle parentesi graffe non sarà eseguita.

**Pseudocodice**

<blockquote>if (<i>condition is true</i>) {<br> <i>statement is executed</i><br>}</blockquote>

**Esempio**

```js
function test(myCondition) {
  if (myCondition) {
    return "It was true";
  }
  return "It was false";
}

test(true);
test(false);
```

`test(true)` restituisce la stringa `It was true` e `test(false)` restituisce la stringa `It was false`.

Quando `test` viene chiamato con un valore di `true`, l'istruzione `if` valuta `myCondition` per vedere se è `true` o no. Dal momento che è `true`, la funzione restituisce `It was true`. Quando chiamiamo `test` con un valore di `false`, `myCondition` *non* è `true`, quindi l'istruzione tra parentesi graffe non viene eseguita e la funzione restituisce `It was false`.

# --instructions--

Crea un comando `if` all'interno della funzione che restituisca `Yes, that was true` se il parametro `wasThatTrue` è `true` e restituisca `No, that was false` altrimenti.

# --hints--

`trueOrFalse` dovrebbe essere una funzione

```js
assert(typeof trueOrFalse === 'function');
```

`trueOrFalse(true)` dovrebbe restituire una stringa

```js
assert(typeof trueOrFalse(true) === 'string');
```

`trueOrFalse(false)` dovrebbe restituire una stringa

```js
assert(typeof trueOrFalse(false) === 'string');
```

`trueOrFalse(true)` dovrebbe restituire la stringa `Yes, that was true`

```js
assert(trueOrFalse(true) === 'Yes, that was true');
```

`trueOrFalse(false)` dovrebbe restituire la stringa `No, that was false`

```js
assert(trueOrFalse(false) === 'No, that was false');
```

# --seed--

## --seed-contents--

```js
function trueOrFalse(wasThatTrue) {
  // Only change code below this line



  // Only change code above this line

}
```

# --solutions--

```js
function trueOrFalse(wasThatTrue) {
  if (wasThatTrue) {
    return "Yes, that was true";
  }
  return "No, that was false";
}
```
