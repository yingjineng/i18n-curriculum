---
id: 56533eb9ac21ba0edf2244dd
title: Selecionar entre várias opções com instruções switch
challengeType: 1
forumTopicId: 18277
dashedName: selecting-from-many-options-with-switch-statements
---

# --description--

If you need to match one value against many options, you can use a <dfn>switch</dfn> statement. A `switch` statement compares the value to the <dfn>case</dfn> statements which define various possible values. Any valid JavaScript statements can be executed inside a <dfn>case</dfn> block and will run from the first matched `case` value until a `break` is encountered.

Aqui está um exemplo de uma instrução `switch`:

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

Valores `case` são testados com o operador de igualdade estrita (`===`). O `break` diz ao JavaScript parar interromper a execução das instruções. Se o `break` for omitido, a próxima instrução case será executada.

# --instructions--

Escreva uma instrução switch que testa `val` e define `answer` para as seguintes condições:  
`1` - `alpha`  
`2` - `beta`  
`3` - `gamma`  
`4` - `delta`

# --hints--

`caseInSwitch(1)` deve ter o valor da string `alpha`

```js
assert(caseInSwitch(1) === 'alpha');
```

`caseInSwitch(2)` deve ter o valor da string `beta`

```js
assert(caseInSwitch(2) === 'beta');
```

`caseInSwitch(3)` deve ter o valor da string `gamma`

```js
assert(caseInSwitch(3) === 'gamma');
```

`caseInSwitch(4)` deve ter o valor da string `delta`

```js
assert(caseInSwitch(4) === 'delta');
```

Você não deve usar nenhuma instrução do tipo `if` ou `else`

```js
assert(!/else/g.test(__helpers.removeJSComments(code)) || !/if/g.test(__helpers.removeJSComments(code)));
```

Você deve ter pelo menos 3 instruções `break`

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
