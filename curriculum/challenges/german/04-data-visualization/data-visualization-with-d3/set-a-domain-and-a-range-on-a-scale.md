---
id: 587d7fac367417b2b2512bdb
title: Domain und Bereich auf Skala festlegen
challengeType: 6
forumTopicId: 301491
dashedName: set-a-domain-and-a-range-on-a-scale
---

# --description--

By default, scales use the identity relationship. This means the input value maps to the output value. However, scales can be much more flexible and interesting.

Angenommen ein Datensatz hat Werte zwischen 50 und 480. Dies ist die Eingangsinformation für eine Skala, die auch als <dfn>Domäne</dfn> bezeichnet wird.

Diese Punkte sollten entlang der `x`-Achse auf der SVG zwischen 10 Einheiten und 500 Einheiten zugeordnet werden. Dies sind die Ausgabeinformationen, die auch als <dfn>range</dfn> bezeichnet werden.

Die `domain()`- und `range()`-Methoden legen diese Werte für die Skala fest. Beide Methoden nehmen ein Array von mindestens zwei Elementen als Argument. Hier ist ein Beispiel:

```js
scale.domain([50, 480]);
scale.range([10, 500]);
scale(50);
scale(480);
scale(325);
scale(750);
d3.scaleLinear();
```

Die folgenden Werte werden, in dieser Reihenfolge, in der Konsole angezeigt: `10`, `500`, `323.37`, and `807.67`.

Beachte, dass die Skala die lineare Beziehung zwischen Domäne und Bereichswerten verwendet, um herauszufinden, was die Ausgabe für eine gegebene Zahl sein soll. Der minimale Wert in der Domain (50) wird dem minimalen Wert (10) im Bereich zugeordnet.

# --instructions--

Erstelle eine Skala und setze die Domain auf `[250, 500]` und erweitere auf `[10, 150]`.

**Hinweis:** Du kannst die `domain()`- und `range()`-Methoden mit der `scale`-Variablen verbinden.

# --hints--

Dein Code sollte die `domain()`-Methode verwenden.

```js
assert.match(code, /\.domain/g);
```

Die `domain()` der `scale` sollte auf `[250, 500]` gesetzt werden.

```js
assert.deepEqual(scale.domain(), [250, 500]);
```

Dein Code sollte die `range()`-Methode verwenden.

```js
assert.match(code, /\.range/g);
```

Der `range()` von `scale` sollte auf `[10, 150]` gesetzt werden.

```js
assert.deepEqual(scale.range(), [10, 150]);
```

Der Text im `h2` sollte `-102` sein.

```js
assert.strictEqual(document.querySelector('h2')?.textContent, '-102');
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    // Add your code below this line
    const scale = d3.scaleLinear();



    // Add your code above this line
    const output = scale(50);
    d3.select('body').append('h2').text(output);
  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const scale = d3.scaleLinear();
    scale.domain([250, 500]);
    scale.range([10, 150]);
    const output = scale(50);
    d3.select('body').append('h2').text(output);
  </script>
</body>
```
