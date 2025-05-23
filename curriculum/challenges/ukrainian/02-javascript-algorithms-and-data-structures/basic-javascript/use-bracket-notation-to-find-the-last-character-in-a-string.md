---
id: bd7123c9c451eddfaeb5bdef
title: Дужкова нотація для пошуку останнього символа рядка
challengeType: 1
forumTopicId: 18342
dashedName: use-bracket-notation-to-find-the-last-character-in-a-string
---

# --description--

In order to get the last letter of a string, you can subtract one from the string's length.

Наприклад, якщо `const firstName = "Ada"`, ви можете отримати значення останньої літери, використавши `firstName[firstName.length - 1]`.

Наприклад:

```js
const firstName = "Ada";
const lastLetter = firstName[firstName.length - 1];
```

`lastLetter` матиме значення рядка `a`.

# --instructions--

Використайте <dfn>дужкову нотацію</dfn>, щоб знайти останній символ у змінній `lastName`.

**Підказка:**Спробуйте подивитися на приклад вище, якщо застрягли.

# --hints--

`lastLetterOfLastName` має бути літера `e`.

```js
assert(lastLetterOfLastName === 'e');
```

Ви повинні використати `.length`, щоб отримати останню літеру.

```js
assert(__helpers.removeJSComments(code).match(/\.length/g).length > 0);
```

# --seed--

## --after-user-code--

```js
(function(v){return v;})(lastLetterOfLastName);
```

## --seed-contents--

```js
// Setup
const lastName = "Lovelace";

// Only change code below this line
const lastLetterOfLastName = lastName; // Change this line
```

# --solutions--

```js
const lastName = "Lovelace";
const lastLetterOfLastName = lastName[lastName.length - 1];
```
