---
id: bd7123c9c452eddfaeb5bdef
title: Usare la notazione parentesi per trovare l'n-ultimo carattere dalla fine di una stringa
challengeType: 1
forumTopicId: 18344
dashedName: use-bracket-notation-to-find-the-nth-to-last-character-in-a-string
---

# --description--

You can use the same principle we just used to retrieve the last character in a string to retrieve the Nth-to-last character.

Ad esempio, puoi ottenere il valore della terzultima lettera della stringa `const firstName = "Augusta"` usando `firstName[firstName.length - 3]`

Esempio:

```js
const firstName = "Augusta";
const thirdToLastLetter = firstName[firstName.length - 3];
```

`thirdToLastLetter` dovrebbe avere un valore stringa `s`.

# --instructions--

Usa <dfn>la notazione a parentesi</dfn> per trovare il penultimo carattere nella stringa `lastName`.

**Suggerimento:** Prova a guardare l'esempio qui sopra se ti blocchi.

# --hints--

`secondToLastLetterOfLastName` dovrebbe essere la lettera `c`.

```js
assert(secondToLastLetterOfLastName === 'c');
```

Dovresti usare `.length` per ottenere la penultima lettera.

```js
assert(__helpers.removeJSComments(code).match(/\.length/g).length > 0);
```

# --seed--

## --after-user-code--

```js
(function(v){return v;})(secondToLastLetterOfLastName);
```

## --seed-contents--

```js
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName; // Change this line
```

# --solutions--

```js
const lastName = "Lovelace";
const secondToLastLetterOfLastName = lastName[lastName.length - 2];
```
