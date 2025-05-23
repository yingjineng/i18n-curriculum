---
id: 587d7b8c367417b2b2512b58
title: Erstelle einen Export-Fallback mit export default
challengeType: 1
forumTopicId: 301199
dashedName: create-an-export-fallback-with-export-default
---

# --description--

In the `export` lesson, you learned about the syntax referred to as a <dfn>named export</dfn>. This allowed you to make multiple functions and variables available for use in other files.

Es gibt noch eine weitere `export`-Syntax, die du kennen musst: <dfn>export default</dfn> (Standard-Export). Normalerweise verwendest du diese Syntax, wenn nur ein Wert aus einer Datei exportiert wird. Es wird auch verwendet, um einen Fallback-Wert für eine Datei oder ein Modul zu erstellen.

Im Folgenden findest du Beispiele mit `export default`:

```js
export default function add(x, y) {
  return x + y;
}

export default function(x, y) {
  return x + y;
}
```

Die erste ist eine benannte Funktion, die zweite eine anonyme Funktion.

Da `export default` verwendet wird, um einen Fallback-Wert für ein Modul oder eine Datei zu deklarieren, kannst du nur einen Wert als Standard-Export in jedem Modul oder jeder Datei haben. Außerdem kannst du `export default` nicht mit `var`, `let` oder `const` verwenden

# --instructions--

Die folgende Funktion sollte der Fallbackwert für das Modul sein. Bitte füge den dafür notwendigen Code hinzu.

# --hints--

Dein Code sollte einen `export` Fallback verwenden.

```js
assert(
  __helpers.removeJSComments(code).match(
    /export\s+default\s+function(\s+subtract\s*|\s*)\(\s*x,\s*y\s*\)\s*{/g
  )
);
```

# --seed--

## --seed-contents--

```js
function subtract(x, y) {
  return x - y;
}
```

# --solutions--

```js
export default function subtract(x, y) {
  return x - y;
}
```
