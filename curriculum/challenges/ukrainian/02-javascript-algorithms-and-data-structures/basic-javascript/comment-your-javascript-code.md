---
id: bd7123c9c441eddfaeb4bdef
title: Коментування коду JavaScript
challengeType: 1
forumTopicId: 16783
dashedName: comment-your-javascript-code
---

# --description--

Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to other people who will later need to figure out what that code does.

Існує два способи написання коментарів у JavaScript:

Використавши `//`, ви повідомите JavaScript про те, що потрібно ігнорувати решту тексту поточного рядка. Це коментар всередині рядка:

```js
// This is an in-line comment.
```

Ви можете зробити багаторядковий коментар, починаючи з `/*` і закінчуючи `*/`. Це багаторядковий коментар:

```js
/* This is a
multi-line comment */
```

**ПРИМІТКА:** при написанні коду ви повинні часто додавати коментарі, щоб роз’яснити функції частин вашого коду. Хороші коментарі можуть передати мету вашого коду як для інших людей, *так і* для себе в майбутньому.

# --instructions--

Спробуйте створити один коментар кожного типу.

# --hints--

Ви повинні створити коментар стилю `//`, який містить принаймні п’ять літер.

```js
assert(code.match(/(\/\/)...../g));
```

Ви повинні створити коментар стилю `/* */`, який містить принаймні п’ять літер.

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
