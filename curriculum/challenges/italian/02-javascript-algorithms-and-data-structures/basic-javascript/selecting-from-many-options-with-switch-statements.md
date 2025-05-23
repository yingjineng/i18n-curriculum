---
id: 56533eb9ac21ba0edf2244dd
title: Selezionare tra molte opzioni con le istruzioni Switch
challengeType: 1
forumTopicId: 18277
dashedName: selecting-from-many-options-with-switch-statements
---

# --description--

If you need to match one value against many options, you can use a <dfn>switch</dfn> statement. A `switch` statement compares the value to the <dfn>case</dfn> statements which define various possible values. Any valid JavaScript statements can be executed inside a <dfn>case</dfn> block and will run from the first matched `case` value until a `break` is encountered.

Ecco un esempio di un'istruzione `switch`:

```js
switch (fruit) {
  case "apple":
    console.log("The fruit is an apple");
    break;
  case "orange":
    console.log("The fruit is an orange");
    break;
}
```

I valori `case` vengono testati con uguaglianza stretta (`===`). Il `break` dice a JavaScript di interrompere l'esecuzione delle istruzioni. Se il `break` viene omesso, sarà eseguita la successiva istruzione.

# --instructions--

Scrivi una dichiarazione switch che testa `val` e imposta il valore di `answer` per le seguenti condizioni:  
`1` - `alpha`  
`2` - `beta`  
`3` - `gamma`  
`4` - `delta`

# --hints--

`caseInSwitch(1)` dovrebbe avere il valore stringa `alpha`

```js
assert(caseInSwitch(1) === 'alpha');
```

`caseInSwitch(2)` dovrebbe avere il valore stringa `beta`

```js
assert(caseInSwitch(2) === 'beta');
```

`caseInSwitch(3)` dovrebbe avere il valore stringa `gamma`

```js
assert(caseInSwitch(3) === 'gamma');
```

`caseInSwitch(4)` dovrebbe avere il valore stringa `delta`

```js
assert(caseInSwitch(4) === 'delta');
```

Non dovresti usare alcuna dichiarazione `if` o `else`

```js
assert(!/else/g.test(__helpers.removeJSComments(code)) || !/if/g.test(__helpers.removeJSComments(code)));
```

Dovresti avere almeno 3 istruzioni `break`

```js
assert(__helpers.removeJSComments(code).match(/break/g).length > 2);
```

# --seed--

## --seed-contents--

```js
function caseInSwitch(val) {
  let answer = "";
  // Only change code below this line



  // Only change code above this line
  return answer;
}

caseInSwitch(1);
```

# --solutions--

```js
function caseInSwitch(val) {
  let answer = "";

  switch (val) {
    case 1:
      answer = "alpha";
      break;
    case 2:
      answer = "beta";
      break;
    case 3:
      answer = "gamma";
      break;
    case 4:
      answer = "delta";
  }
  return answer;
}
```
