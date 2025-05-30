---
id: 587d7fb0367417b2b2512bef
title: Bereitstellen einer HTML-Datei
challengeType: 2
forumTopicId: 301516
dashedName: serve-an-html-file
---

# --description--

You can respond to requests with a file using the `res.sendFile(path)` method. You can put it inside the `app.get('/', ...)` route handler. Behind the scenes, this method will set the appropriate headers to instruct your browser on how to handle the file you want to send, according to its type. Then it will read and send the file. This method needs an absolute file path. We recommend you to use the Node global variable `__dirname` to calculate the path like this:

```js
absolutePath = __dirname + '/relativePath/file.ext'
```

# --instructions--

Sende die `/views/index.html`-Datei als Antwort auf GET-Anfragen an den `/`-Pfad. Siehst du dir deine laufende Anwendung an, solltest du eine große HTML-Überschrift ohne angewandten Stil sehen (und ein Formular, welches wir später verwenden werden...).

**Hinweis:** Du kannst die Lösung der vorherigen Aufgabe bearbeiten oder eine neue erstellen. Wenn du eine neue Lösung erstellst, beachte, dass Express die Pfade von oben nach unten auswertet und den Handler für die erste Übereinstimmung ausführt. Du musst die vorangehende Lösung entkommentieren, sonst antwortet der Server weiterhin mit einem String.

# --hints--

Die Anwendung sollte die Datei views/index.html bereitstellen

```js
  $.get(code).then(
    (data) => {
      assert.match(
        data,
        /<h1>.*<\/h1>/,
        'Your app does not serve the expected HTML'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

