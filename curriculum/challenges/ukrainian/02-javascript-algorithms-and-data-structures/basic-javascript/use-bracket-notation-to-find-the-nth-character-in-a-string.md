---
id: bd7123c9c450eddfaeb5bdef
title: Дужкова нотація для пошуку n-го символа рядка
challengeType: 1
forumTopicId: 18343
dashedName: use-bracket-notation-to-find-the-nth-character-in-a-string
---

# --description--

You can also use <dfn>bracket notation</dfn> to get the character at other positions within a string.

Пам’ятайте, що комп’ютер починає рахувати з `0`, тому насправді першим символом є нульовий.

Наприклад:

```js
const firstName = "Ada";
const secondLetterOfFirstName = firstName[1];
```

`secondLetterOfFirstName` матиме значення рядка `d`.

# --instructions--

Спробуйте встановити `thirdLetterOfLastName`, щоб вона дорівнювала третій літері змінної `lastName`, використовуючи дужкову нотацію.

**Підказка:**Спробуйте подивитися на приклад вище, якщо застрягли.

# --hints--

Змінна `thirdLetterOfLastName` повинна мати значення `v`.

```js
assert(thirdLetterOfLastName === 'v');
```

Ви повинні використати дужкову нотацію.

```js
assert(__helpers.removeJSComments(code).match(/thirdLetterOfLastName\s*=\s*lastName\s*\[\s*\d\s*\]/));
```

# --seed--

## --after-user-code--

```js
(function(v){return v;})(thirdLetterOfLastName);
```

## --seed-contents--

```js
// Setup
const lastName = "Lovelace";

// Only change code below this line
const thirdLetterOfLastName = lastName; // Change this line
```

# --solutions--

```js
const lastName = "Lovelace";
const thirdLetterOfLastName = lastName[2];
```
