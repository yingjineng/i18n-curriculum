---
id: 56533eb9ac21ba0edf2244ba
title: Незмінність рядка
challengeType: 1
forumTopicId: 18331
dashedName: understand-string-immutability
---

# --description--

In JavaScript, `String` values are <dfn>immutable</dfn>, which means that they cannot be altered once created.

Наприклад, наступний код спричинить помилку, оскільки літеру `B` у рядку `Bob` не можна змінити на літеру `J`:

```js
let myStr = "Bob";
myStr[0] = "J";
```

Зауважте, що це *не* означає, що `myStr` не можна повторно присвоїти. Єдиний спосіб змінити `myStr` — присвоїти нове значення:

```js
let myStr = "Bob";
myStr = "Job";
```

# --instructions--

Використовуючи приклад вище, виправте присвоєння `myStr` так, щоб значенням рядка було `Hello World`.

# --hints--

`myStr` повинен мати значення рядка `Hello World`.

```js
assert(myStr === 'Hello World');
```

Не змінюйте код над зазначеним коментарем.

```js
assert(/myStr = "Jello World"/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(v){return "myStr = " + v;})(myStr);
```

## --seed-contents--

```js
// Setup
let myStr = "Jello World";

// Only change code below this line
myStr[0] = "H"; // Change this line
// Only change code above this line
```

# --solutions--

```js
let myStr = "Jello World";
myStr = "Hello World";
```
