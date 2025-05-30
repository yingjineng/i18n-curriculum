---
id: 56533eb9ac21ba0edf2244ac
title: Інкремент числа з JavaScript
challengeType: 1
forumTopicId: 18201
dashedName: increment-a-number-with-javascript
---

# --description--

You can easily <dfn>increment</dfn> or add one to a variable with the `++` operator.

```js
i++;
```

те й саме, що

```js
i = i + 1;
```

**Примітка:** весь рядок стає `i++;`, усуваючи потребу в знаку рівності.

# --instructions--

Змініть код, щоб використати оператор `++` на `myVar`.

# --hints--

`myVar` має дорівнювати `88`.

```js
assert(myVar === 88);
```

Ви не повинні використовувати оператор присвоєння.

```js
assert(
  /let\s+myVar\s*=\s*87;\s*\/*.*\s*([+]{2}\s*myVar|myVar\s*[+]{2})/.test(__helpers.removeJSComments(code))
);
```

Ви повинні використати оператор `++`.

```js
assert(/[+]{2}\s*myVar|myVar\s*[+]{2}/.test(__helpers.removeJSComments(code)));
```

Не змінюйте код над зазначеним коментарем.

```js
assert(/let myVar = 87;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return 'myVar = ' + z;})(myVar);
```

## --seed-contents--

```js
let myVar = 87;

// Only change code below this line
myVar = myVar + 1;
```

# --solutions--

```js
let myVar = 87;
myVar++;
```
