---
id: 56533eb9ac21ba0edf2244cc
title: Доступ до вкладених об’єктів
challengeType: 1
forumTopicId: 16161
dashedName: accessing-nested-objects
---

# --description--

The sub-properties of objects can be accessed by chaining together the dot or bracket notation.

Ось вкладений об’єкт:

```js
const ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};

ourStorage.cabinet["top drawer"].folder2;
ourStorage.desk.drawer;
```

`ourStorage.cabinet["top drawer"].folder2` буде рядком `secrets`, а `ourStorage.desk.drawer` буде рядком `stapler`.

# --instructions--

Отримайте доступ до `myStorage` та призначте вміст властивості `glove box` до змінної `gloveBoxContents`. Використайте точкову нотацію для всіх властивостей, де можливо. В іншому випадку використайте дужкову нотацію.

# --hints--

`gloveBoxContents` має дорівнювати рядку `maps`.

```js
assert(gloveBoxContents === 'maps');
```

Код має використати точкову нотацію (там де можливо), щоб отримати доступ до `myStorage`.

```js
assert.match(code, /myStorage\.car\.inside/);
```

`gloveBoxContents` досі має бути оголошено з `const`.

```js
assert.match(code, /const\s+gloveBoxContents\s*=/);
```

Не змінюйте об’єкт `myStorage`.

```js
const expectedMyStorage = {
  "car":{
    "inside":{
      "glove box":"maps",
      "passenger seat":"crumbs"
    },
    "outside":{
      "trunk":"jack"
    }
  }
};
assert.deepStrictEqual(myStorage, expectedMyStorage);
```

# --seed--

## --after-user-code--

```js
(function(x) { 
  if(typeof x != 'undefined') { 
    return "gloveBoxContents = " + x;
  }
  return "gloveBoxContents is undefined";
})(gloveBoxContents);
```

## --seed-contents--

```js
const myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

const gloveBoxContents = undefined;
```

# --solutions--

```js
const myStorage = {
  "car":{
    "inside":{
      "glove box":"maps",
      "passenger seat":"crumbs"
    },
    "outside":{
      "trunk":"jack"
    }
  }
};
const gloveBoxContents = myStorage.car.inside["glove box"];
```
