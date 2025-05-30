---
id: 56533eb9ac21ba0edf2244ad
title: Decrementare un numero con JavaScript
challengeType: 1
forumTopicId: 17558
dashedName: decrement-a-number-with-javascript
---

# --description--

You can easily <dfn>decrement</dfn> or decrease a variable by one with the `--` operator.

```js
i--;
```

è equivalente a

```js
i = i - 1;
```

**Nota:** L'intera linea diventa `i--;`, eliminando la necessità di un segno uguale.

# --instructions--

Cambia il codice per utilizzare l'operatore `--` su `myVar`.

# --hints--

`myVar` dovrebbe essere uguale a `10`.

```js
assert(myVar === 10);
```

`myVar = myVar - 1;` dovrebbe essere modificato.

```js
assert(!__helpers.removeJSComments(code).match(/myVar\s*=\s*myVar\s*[-]\s*1.*?;?/));
```

Non dovresti assegnare `10` a `myVar`.

```js
assert(!__helpers.removeJSComments(code).match(/myVar\s*=\s*10.*?;?/));
```

Dovresti usare l'operatore `--` su `myVar`.

```js
assert(/[-]{2}\s*myVar|myVar\s*[-]{2}/.test(__helpers.removeJSComments(code)));
```

Non dovresti modificare il codice sopra il commento specificato.

```js
assert(/let myVar = 11;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myVar = ' + z;})(myVar);
```

## --seed-contents--

```js
let myVar = 11;

// Only change code below this line
myVar = myVar - 1;
```

# --solutions--

```js
let myVar = 11;
myVar--;
```
