---
id: 587d7fa6367417b2b2512bc2
title: Dokumentelemente mit D3 hinzufügen
challengeType: 6
forumTopicId: 301474
dashedName: add-document-elements-with-d3
---

# --description--

D3 has several methods that let you add and change elements in your document.

Die `select()`-Methode wählt ein Element aus dem Dokument aus. Sie nimmt ein Argument für den Namen des gewünschten Elements entgegen und gibt einen HTML-Knoten für das erste Element im Dokument zurück, das dem Namen entspricht. Hier ein Beispiel:

```js
const anchor = d3.select('a');
```

Im obigen Beispiel wird das erste Anker-Tag auf der Seite gefunden und ein HTML-Knoten für dieses in der Variable `anchor` gespeichert. Du kannst die Auswahl mit anderen Methoden verwenden. Der `d3`-Teil des Beispiels ist ein Verweis auf das D3-Objekt, mit dem du auf D3-Methoden zugreifst.

Zwei weitere nützliche Methoden sind `append()` und `text()`.

Die `append()`-Methode akzeptiert das Element, welches du dem Dokument hinzufügen möchtest, als Argument. Es fügt einen HTML-Knoten einem bestimmten Element hinzu und gibt ein Handle zu diesem Knoten zurück.

Die `text()`-Methode legt entweder den Text des ausgewählten Knotens fest oder ruft den aktuellen Text ab. Übergib ein String als Argument innerhalb der Klammern der Methode, um den Wert festzulegen.

Hier ist ein Beispiel, das eine ungeordnete Liste auswählt, ein Listenelement anhängt und Text hinzufügt:

```js
d3.select('ul')?.append('li').text('Very important item');
```

Mit D3 kannst du mithilfe von Punkten mehrere Methoden „verketten“, um verschiedene Aktionen hintereinander auszuführen.

# --instructions--

Verwende die `select`-Methode, um das `body`-Tag im Dokument auszuwählen. Füge anschließend mithilfe von `append` einen `h1`-Tag hinzu und gebe diesem `h1`-Element den Text `Learning D3`.

# --hints--

Der `body` sollte über ein `h1`-Element verfügen.

```js
const body = document.querySelector('body');
const headers = body?.querySelectorAll('h1');
assert.lengthOf(headers, 1);
```

Das `h1`-Element sollte den Text `Learning D3` enthalten.

```js
assert.strictEqual(document.querySelector('h1')?.textContent, 'Learning D3');
```

Dein Code sollte auf das `d3`-Objekt zugreifen.

```js
assert.match(code, /d3/g);
```

Dein Code sollte die `select`-Methode verwenden.

```js
assert.match(code, /\.select/g);
```

Dein Code sollte die `append`-Methode verwenden.

```js
assert.match(code, /\.append/g);
```

Dein Code sollte die `text`-Methode verwenden.

```js
assert.match(code, /\.text/g);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    // Add your code below this line



    // Add your code above this line
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    d3.select('body').append('h1').text('Learning D3');
  </script>
</body>
```
