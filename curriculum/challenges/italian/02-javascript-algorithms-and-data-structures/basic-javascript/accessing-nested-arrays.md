---
id: 56533eb9ac21ba0edf2244cd
title: Accedere ad Array annidati
challengeType: 1
forumTopicId: 16160
dashedName: accessing-nested-arrays
---

# --description--

As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, array bracket notation can be chained to access nested arrays.

Ecco un esempio di come accedere a un array nidificato:

```js
const ourPets = [
  {
    animalType: "cat",
    names: [
      "Meowzer",
      "Fluffy",
      "Kit-Cat"
    ]
  },
  {
    animalType: "dog",
    names: [
      "Spot",
      "Bowser",
      "Frankie"
    ]
  }
];

ourPets[0].names[1];
ourPets[1].names[0];
```

`ourPets[0].names[1]` sarebbe la stringa `Fluffy` e `ourPets[1].names[0]` sarebbe la stringa `Spot`.

# --instructions--

Utilizzando la notazione dei punti e delle parentesi, imposta la variabile `secondTree` al secondo elemento dell'array `list` dal secondo oggetto dell'array `myPlants`.

# --hints--

`secondTree` dovrebbe essere uguale alla stringa `pine`.

```js
assert(secondTree === 'pine');
```

Il tuo codice dovrebbe utilizzare la notazione a punti e parentesi per accedere a `myPlants`.

```js
assert(/=\s*myPlants\[1\].list\[1\]/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(x) {
  if(typeof x != 'undefined') {
    return "secondTree = " + x;
  }
  return "secondTree is undefined";
})(secondTree);
```

## --seed-contents--

```js
const myPlants = [
  {
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }
];

const secondTree = "";
```

# --solutions--

```js
const myPlants = [
  {
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }
];

const secondTree = myPlants[1].list[1];
```
