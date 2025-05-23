---
id: 587d7b8d367417b2b2512b59
title: Einen Standard-Export importieren
challengeType: 1
forumTopicId: 301205
dashedName: import-a-default-export
---

# --description--

In the last challenge, you learned about `export default` and its uses. To import a default export, you need to use a different `import` syntax. In the following example, `add` is the default export of the `math_functions.js` file. Here is how to import it:

```js
import add from "./math_functions.js";
```

Die Syntax unterscheidet sich an einer wichtigen Stelle. Der importierte Wert, `add`, ist nicht von geschweiften Klammern (`{}`) umgeben. `add` ist hier einfach ein Variablenname für den Standard-Export der Datei `math_functions.js`. Du kannst jeden Namen verwenden, wenn du etwas importierst, das als Standard exportiert wurde.

# --instructions--

Im folgenden Code importierst du den Standard-Export aus der Datei `math_functions.js`, die sich im selben Verzeichnis wie diese Datei befindet. Gib dem Import den Namen `subtract`.

# --hints--

Du solltest `subtract` aus `math_functions.js` korrekt importieren.

```js
assert(__helpers.removeJSComments(code).match(/import\s+subtract\s+from\s+('|")\.\/math_functions\.js\1/g));
```

# --seed--

## --seed-contents--

```js

// Only change code above this line

subtract(7,4);
```

# --solutions--

```js
import subtract from "./math_functions.js";

subtract(7,4);
```
