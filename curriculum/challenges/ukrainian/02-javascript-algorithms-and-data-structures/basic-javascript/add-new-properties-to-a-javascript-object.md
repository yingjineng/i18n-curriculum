---
id: 56bbb991ad1ed5201cd392d2
title: Додавання нових властивостей до об’єкта JavaScript
challengeType: 1
forumTopicId: 301169
dashedName: add-new-properties-to-a-javascript-object
---

# --description--

You can add new properties to existing JavaScript objects the same way you would modify them.

Таким чином ми б додали властивість `bark` до `ourDog`:

```js
ourDog.bark = "bow-wow";
```

або

```js
ourDog["bark"] = "bow-wow";
```

Якщо ми виконаємо `ourDog.bark`, отримаємо гавкання `bow-wow`.

Приклад:

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```

# --instructions--

Додайте властивість `bark` до `myDog` і встановіть її на гавкіт собаки, наприклад «woof». Ви можете використати точкову або дужкову нотацію.

# --hints--

Ви повинні додати властивість `bark` до `myDog`.

```js
assert(myDog.bark !== undefined);
```

Ви не повинні додавати `bark` до ініціалізації `myDog`.

```js
assert(!/bark[^\n]:/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return z;})(myDog);
```

## --seed-contents--

```js
const myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};


```

# --solutions--

```js
const myDog = {
  "name": "Happy Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};
myDog.bark = "Woof Woof";
```
