---
id: 587d7fab367417b2b2512bda
title: Erstelle eine lineare Skala mit D3
challengeType: 6
forumTopicId: 301483
dashedName: create-a-linear-scale-with-d3
---

# --description--

The bar and scatter plot charts both plotted data directly onto the SVG. However, if the height of a bar or one of the data points were larger than the SVG height or width values, it would go outside the SVG area.

In D3 gibt es Skalen, die bei der Darstellung von Daten helfen. `scales` sind Funktionen, die dem Programm mitteilen, wie eine Menge von unbearbeiteten Datenpunkten den SVG-Pixeln zugeordnet werden soll.

Nehmen wir beispielsweise an, du hast ein SVG der Größe 100x500 und möchtest das Bruttoinlandsprodukt (BIP) für eine Reihe von Ländern darstellen. Die Zahlen wären im Milliarden- oder Billionen-Dollar-Bereich. Du übergibst D3 einen Skalierungstyp, mit welchem du ihm mitteilst, wie die hohen BIP-Werte in dem 100x500 großen Bereich zu platzieren sind.

Es ist unwahrscheinlich, dass du die Rohdaten so darstellen würdest, wie sie sind. Bevor du mit der Einzeichnung beginnst, legst du die Skala für deinen Datensatz fest, so dass die `x`- und `y`-Werte zu deiner SVG-Breite sowie -Höhe passen.

D3 verfügt über verschiedene Skalierungstypen. Möchtest du eine lineare Skalierung (wie sie für quantitative Daten meist verwendet wird), verwendest du die D3-Methode `scaleLinear()`:

```js
const scale = d3.scaleLinear();
```

Standardmäßig verwendet eine Skala die Identitätsbeziehung. Ein- und Ausgabewerte sind gleich. Wie man das ändern kann, ist Gegenstand einer separaten Aufgabenstellung.

# --instructions--

Ändere die `scale`-Variable so, dass eine lineare Skala entsteht. Setze dann die `output`-Variable auf die Skala, die mit einem Eingabeargument von `50` aufgerufen wird.

# --hints--

Der Text im `h2` sollte `50` sein.

```js
assert.strictEqual(document.querySelector('h2')?.textContent, '50');
```

Dein Code sollte die `scaleLinear()`-Methode verwenden.

```js
assert.match(code, /\.scaleLinear/g);
```

Die `output`-Variable sollte `scale` mit dem Argument `50` aufrufen.

```js
assert.strictEqual(output, 50);
assert.match(code, /scale\(\s*50\s*\)/g);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    // Add your code below this line

    const scale = undefined; // Create the scale here
    const output = scale(); // Call scale with an argument here

    // Add your code above this line

    d3.select('body').append('h2').text(output);
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const scale = d3.scaleLinear();
    const output = scale(50);

    d3.select('body').append('h2').text(output);
  </script>
</body>
```
