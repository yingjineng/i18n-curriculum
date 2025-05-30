---
id: 598f48a36c8c40764b4e52b3
title: Objektmodifikationen (Mutationen) verhindern
challengeType: 1
forumTopicId: 301207
dashedName: prevent-object-mutation
---

# --description--

As seen in the previous challenge, `const` declaration alone doesn't really protect your data from mutation. To ensure your data doesn't change, JavaScript provides a function `Object.freeze` to prevent data mutation.

Jeder Versuch, das Objekt zu ändern, wird zurückgewiesen und ein Fehler wird ausgegeben, wenn das Skript im strikten Modus läuft.

```js
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad";
obj.newProp = "Test";
console.log(obj); 
```

Die Zuweisungen `obj.review` und `obj.newProp` führen zu Fehlern, weil unser Editor standardmäßig im strikten Modus läuft und die Konsole den Wert `{ name: "FreeCodeCamp", review: "Awesome" }` ausgibt.

# --instructions--

In dieser Aufgabe wirst du `Object.freeze` verwenden, um zu verhindern, dass sich mathematische Konstanten ändern. Du musst das `MATH_CONSTANTS` Objekt fixieren, damit niemand den Wert von `PI` ändern, Eigenschaften hinzufügen oder löschen kann.

# --hints--

Du solltest das Schlüsselwort `const` nicht ersetzen.

```js
assert(__helpers.removeJSComments(code).match(/const/g));
```

`MATH_CONSTANTS` sollte eine konstante Variable sein (indem du `const` verwendest).

```js
assert(__helpers.removeJSComments(code).match(/const\s+MATH_CONSTANTS/g));
```

Du solltest die ursprüngliche Deklaration von `MATH_CONSTANTS` nicht ändern.

```js
assert(__helpers.removeJSComments(code).match(
   /const\s+MATH_CONSTANTS\s+=\s+{\s+PI:\s+3.14\s+};/g
));
```

`PI` sollte gleich `3.14` sein.

```js
assert(PI === 3.14);
```

# --seed--

## --seed-contents--

```js
function freezeObj() {
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  // Only change code below this line


  // Only change code above this line
  try {
    MATH_CONSTANTS.PI = 99;
  } catch(ex) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```

# --solutions--

```js
function freezeObj() {
  const MATH_CONSTANTS = {
    PI: 3.14
  };
  Object.freeze(MATH_CONSTANTS);

  try {
    MATH_CONSTANTS.PI = 99;
  } catch(ex) {
    console.log(ex);
  }
  return MATH_CONSTANTS.PI;
}
const PI = freezeObj();
```
