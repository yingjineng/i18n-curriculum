---
id: 56533eb9ac21ba0edf2244cd
title: Zugriff auf verschachtelte Arrays
challengeType: 1
forumTopicId: 16160
dashedName: accessing-nested-arrays
---

# --description--

As we have seen in earlier examples, objects can contain both nested objects and nested arrays. Similar to accessing nested objects, array bracket notation can be chained to access nested arrays.

Hier ist ein Beispiel, wie du auf ein verschachteltes Array zugreifen kannst:

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

`ourPets[0].names[1]` wäre der String `Fluffy`, und `ourPets[1].names[0]` wäre der String `Spot`.

# --instructions--

Setze die `secondTree`-Variable mit Hilfe der Verwendung der Punkt- und Klammernotation auf das zweite Element im `list`-Array des zweiten Objekts in `myPlants`-Array.

# --hints--

`secondTree` sollte gleich dem String `pine` sein.

```js
assert(secondTree === 'pine');
```

Dein Code sollte die Punkt- und Klammerschreibweise verwenden, um auf `myPlants` zuzugreifen.

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
