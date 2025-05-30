---
id: bd7123c9c451eddfaeb5bdef
title: Usare la notazione a parentesi per trovare l'ultimo carattere in una stringa
challengeType: 1
forumTopicId: 18342
dashedName: use-bracket-notation-to-find-the-last-character-in-a-string
---

# --description--

In order to get the last letter of a string, you can subtract one from the string's length.

Per esempio, se `const firstName = "Ada"`, puoi ottenere il valore dell'ultima lettera della stringa usando `firstName[firstName.length - 1]`.

Esempio:

```js
const firstName = "Ada";
const lastLetter = firstName[firstName.length - 1];
```

`lastLetter` dovrebbe avere un valore stringa `a`.

# --instructions--

Usa <dfn>la notazione a parentesi</dfn> per trovare l'ultimo carattere nella variabile `lastName`.

**Suggerimento:** Prova a guardare l'esempio qui sopra se ti blocchi.

# --hints--

`lastLetterOfLastName` dovrebbe essere la lettera `e`.

```js
assert(lastLetterOfLastName === 'e');
```

Dovresti usare `.length` per ottenere l'ultima lettera.

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
