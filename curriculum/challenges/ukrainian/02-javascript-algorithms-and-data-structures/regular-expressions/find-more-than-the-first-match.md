---
id: 587d7db4367417b2b2512b93
title: Як знайти не лише перший збіг
challengeType: 1
forumTopicId: 301342
dashedName: find-more-than-the-first-match
---

# --description--

So far, you have only been able to extract or search a pattern once.

```js
let testStr = "Repeat, Repeat, Repeat";
let ourRegex = /Repeat/;
testStr.match(ourRegex);
```

`match` поверне `["Repeat"]`.

Щоб знайти або вилучити шаблон більше одного разу, ви можете використати прапорець глобального пошуку: `g`.

```js
let repeatRegex = /Repeat/g;
testStr.match(repeatRegex);
```

А тут `match` поверне значення `["Repeat", "Repeat", "Repeat"]`

# --instructions--

Знайдіть і вилучіть обидва слова `Twinkle` з рядка `twinkleStar` за допомогою регулярного виразу `starRegex`.

**Примітка**  
Ви можете застосувати декілька прапорців до регулярного виразу: `/search/gi`

# --hints--

Ваш регулярний вираз `starRegex` має використати глобальний прапорець `g`

```js
assert(starRegex.flags.match(/g/).length == 1);
```

Ваш регулярний вираз `starRegex` має використати прапорець без урахування регістру `i`

```js
assert(starRegex.flags.match(/i/).length == 1);
```

Ваш збіг має збігатися з двома словами `Twinkle`

```js
assert(
  result.sort().join() ==
    twinkleStar
      .match(/twinkle/gi)
      .sort()
      .join()
);
```

Ваш збіг `result` має містити два елементи.

```js
assert(result.length == 2);
```

# --seed--

## --seed-contents--

```js
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /change/; // Change this line
let result = twinkleStar; // Change this line
```

# --solutions--

```js
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /twinkle/gi;
let result = twinkleStar.match(starRegex);
```
