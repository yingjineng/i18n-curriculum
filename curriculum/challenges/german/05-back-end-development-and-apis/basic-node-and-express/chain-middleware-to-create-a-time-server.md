---
id: 587d7fb1367417b2b2512bf4
title: Verkette Middleware, um einen Zeitserver zu erstellen
challengeType: 2
forumTopicId: 301510
dashedName: chain-middleware-to-create-a-time-server
---

# --description--

Middleware can be mounted at a specific route using `app.METHOD(path, middlewareFunction)`. Middleware can also be chained within a route definition.

Sieh dir das folgende Beispiel an:

```js
app.get('/user', function(req, res, next) {
  req.user = getTheUserSync();  // Hypothetical synchronous operation
  next();
}, function(req, res) {
  res.send(req.user);
});
```

Dieser Ansatz ist nützlich, um den Serverbetrieb in kleinere Einheiten aufzuteilen. Das führt zu einer besseren App-Struktur und der Möglichkeit, Code an verschiedenen Stellen wiederzuverwenden. Dieser Ansatz kann auch zur Validierung der Daten verwendet werden. An jedem Punkt des Middleware-Stacks kannst du die Ausführung der aktuellen Kette blockieren und die Kontrolle an Funktionen übergeben, die speziell für die Fehlerbehandlung entwickelt wurden. Oder du kannst die Kontrolle an die nächste passende Route weitergeben, um besondere Fälle zu bearbeiten. Wie das geht, erfährst du im Abschnitt Express für Fortgeschrittene.

# --instructions--

Verkette in der Route `app.get('/now', ...)` eine Middleware-Funktion und den finalen Handler. In der Middleware-Funktion solltest du dem Request-Objekt im Schlüssel `req.time` die aktuelle Zeit hinzufügen. Du kannst `new Date().toString()` verwenden. Antworte im Handler mit einem JSON-Objekt, das die Struktur `{time: req.time}` hat.

**Hinweis:** Der Test wird nicht bestanden, wenn du die Middleware nicht verkettest. Wenn du die Funktion an einer anderen Stelle einhängst, schlägt der Test fehl, auch wenn das Ausgabeergebnis korrekt ist.

# --hints--

Der /now-Endpunkt sollte über eine eingebundene Middleware verfügen

```js
  $.get(code + '/_api/chain-middleware-time').then(
    (data) => {
      assert.equal(
        data.stackLength,
        2,
        '"/now" route has no mounted middleware'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Der `/now`-Endpunkt sollte die aktuelle Zeit zurückgeben.

```js
  $.get(code + '/_api/chain-middleware-time').then(
    (data) => {
      var now = new Date();
      assert.isAtMost(
        Math.abs(new Date(data.time) - now),
        20000,
        'the returned time is not between +- 20 secs from now'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

