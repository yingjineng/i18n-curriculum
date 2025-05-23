---
id: bd7123c9c441eddfaeb4bdef
title: Kommentiere deinen JavaScript-Code
challengeType: 1
forumTopicId: 16783
dashedName: comment-your-javascript-code
---

# --description--

Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to other people who will later need to figure out what that code does.

Es gibt zwei Varianten, Kommentare in JavaScript zu schreiben:

Mit `//` wird JavaScript angewiesen, den Rest des Textes in der aktuellen Zeile zu ignorieren. Dies ist ein Inline-Kommentar:

```js
// This is an in-line comment.
```

Du kannst einen mehrzeiligen Kommentar schreiben, der mit `/*` beginnt und mit `*/` endet. Dies ist ein mehrzeiliger Kommentar:

```js
/* This is a
multi-line comment */
```

**HINWEIS:** Wenn du Code schreibst, solltest du regelmäßig Kommentare hinzufügen, um die Funktion von Teilen deines Codes zu erläutern. Eine gute Kommentierung kann dazu beitragen, den Zweck deines Codes zu erklären - sowohl für andere *als auch* für dein zukünftiges Ich.

# --instructions--

Versuche einen Kommentar von jeder Variante zu erstellen.

# --hints--

Du solltest einen Kommentar im Stil von `//` erstellen, der mindestens fünf Buchstaben enthält.

```js
assert(code.match(/(\/\/)...../g));
```

Du solltest einen Kommentar im Stil von `/* */` erstellen, der mindestens fünf Buchstaben enthält.

```js
assert(code.match(/(\/\*)([^\/]{5,})(?=\*\/)/gm));
```

# --seed--

## --seed-contents--

```js

```

# --solutions--

```js
// Fake Comment
/* Another Comment */
```
