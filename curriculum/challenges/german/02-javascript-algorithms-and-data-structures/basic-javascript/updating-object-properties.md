---
id: 56bbb991ad1ed5201cd392d1
title: Objekteigenschaften aktualisieren
challengeType: 1
forumTopicId: 18336
dashedName: updating-object-properties
---

# --description--

After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

Schauen wir uns zum Beispiel `ourDog` an:

```js
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```

Da er ein besonders glücklicher Hund ist, ändern wir seinen Namen in den String `Happy Camper`. So aktualisieren wir die Namenseigenschaft seines Objekts: `ourDog.name = "Happy Camper";` oder `ourDog["name"] = "Happy Camper";` Wenn wir nun `ourDog.name` auswerten, erhalten wir statt `Camper` seinen neuen Namen, `Happy Camper`.

# --instructions--

Aktualisiere die Eigenschaft name des Objekts `myDog`. Lass uns ihren Namen von `Coder` in `Happy Coder` ändern. Du kannst entweder die Punkt- oder die Klammerschreibweise verwenden.

# --hints--

Du solltest die Eigenschaft `name` von `myDog` so ändern, dass sie den String `Happy Coder` enthält.

```js
assert(/happy coder/gi.test(myDog.name));
```

Du solltest die Definition von `myDog` nicht bearbeiten.

```js
assert(/"name": "Coder"/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(z){return z;})(myDog);
```

## --seed-contents--

```js
// Setup
const myDog = {
  "name": "Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};

// Only change code below this line

```

# --solutions--

```js
const myDog = {
  "name": "Coder",
  "legs": 4,
  "tails": 1,
  "friends": ["freeCodeCamp Campers"]
};
myDog.name = "Happy Coder";
```
