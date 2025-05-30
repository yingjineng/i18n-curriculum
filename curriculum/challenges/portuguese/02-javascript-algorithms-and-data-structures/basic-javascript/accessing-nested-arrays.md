---
id: 56533eb9ac21ba0edf2244cd
title: Acessar arrays aninhados
challengeType: 1
forumTopicId: 16160
dashedName: accessing-nested-arrays
---

# --description--

Como vimos em exemplos anteriores, objetos podem conter tanto objetos aninhados quanto arrays aninhados. Similar to accessing nested objects, array bracket notation can be chained to access nested arrays.

Aqui está um exemplo de como se acessar um array aninhado:

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

`ourPets[0].names[1]` seria a string `Fluffy` e `ourPets[1].names[0]` seria a string `Spot`.

# --instructions--

Usando a notação de ponto e a de colchetes, defina a variável `secondTree` como o segundo item no array `list` do segundo objeto no array `myPlants`.

# --hints--

`secondTree` deve ser igual à string `pine`.

```js
assert(secondTree === 'pine');
```

O código deve usar notação de ponto e colchetes para acessar `myPlants`.

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
