---
id: bd7123c9c452eddfaeb5bdef
title: Verwendung der Klammer-Notation um das n-te bis letzte Zeichen in einem String zu finden
challengeType: 1
forumTopicId: 18344
dashedName: use-bracket-notation-to-find-the-nth-to-last-character-in-a-string
---

# --description--

You can use the same principle we just used to retrieve the last character in a string to retrieve the Nth-to-last character.

Zum Beispiel kannst du den Wert des drittletzten Buchstabens des Strings `const firstName = "Augusta"` erhalten, indem du `firstName[firstName.length - 3]` verwendest.

Beispiel:

```js
const firstName = "Augusta";
const thirdToLastLetter = firstName[firstName.length - 3];
```

`thirdToLastLetter` hätte den Wert des Strings `s`.

# --instructions--

Verwende die <dfn>Klammer-Notation</dfn>, um das vorletzte Zeichen in dem String `lastName` zu finden.

**Hinweis:** Wenn du nicht weiterkommst, schau dir das Beispiel oben an.

# --hints--

`secondToLastLetterOfLastName` sollte den Buchstaben `c` enthalten.

```js
assert(secondToLastLetterOfLastName === 'c');
```

Du solltest `.length` verwenden, um den vorletzten Buchstaben zu erhalten.

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
