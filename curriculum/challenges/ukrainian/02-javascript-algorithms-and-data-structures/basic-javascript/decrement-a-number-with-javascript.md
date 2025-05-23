---
id: 56533eb9ac21ba0edf2244ad
title: Декремент числа з JavaScript
challengeType: 1
forumTopicId: 17558
dashedName: decrement-a-number-with-javascript
---

# --description--

You can easily <dfn>decrement</dfn> or decrease a variable by one with the `--` operator.

```js
i--;
```

те й саме, що

```js
i = i - 1;
```

**Примітка:** весь рядок стає `i--;`, усуваючи потребу в знаку рівності.

# --instructions--

Змініть код, щоб використати оператор `--` на `myVar`.

# --hints--

`myVar` має дорівнювати `10`.

```js
assert(myVar === 10);
```

`myVar = myVar - 1;` потрібно змінити.

```js
assert(!__helpers.removeJSComments(code).match(/myVar\s*=\s*myVar\s*[-]\s*1.*?;?/));
```

Ви не повинні присвоювати `10` до `myVar`.

```js
assert(!__helpers.removeJSComments(code).match(/myVar\s*=\s*10.*?;?/));
```

Ви повинні використати оператор `--` на `myVar`.

```js
assert(/[-]{2}\s*myVar|myVar\s*[-]{2}/.test(__helpers.removeJSComments(code)));
```

Не змінюйте код над зазначеним коментарем.

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
