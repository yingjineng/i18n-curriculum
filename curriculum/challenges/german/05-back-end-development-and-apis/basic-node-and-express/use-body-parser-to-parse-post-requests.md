---
id: 587d7fb2367417b2b2512bf7
title: Body-Parser verwenden, um POST-Anfragen zu parsen
challengeType: 2
forumTopicId: 301520
dashedName: use-body-parser-to-parse-post-requests
---

# --description--

Besides GET, there is another common HTTP verb, it is POST. POST is the default method used to send client data with HTML forms. In REST convention, POST is used to send data to create new items in the database (a new user, or a new blog post). You don’t have a database in this project, but you are going to learn how to handle POST requests anyway.

Bei dieser Art von Anfragen tauchen die Daten nicht in der URL auf – sie werden im Anfragen-Body versteckt. Der Body ist Teil einer HTTP-Anfrage, auch Payload genannt. Obwohl die Daten in der URL nicht sichtbar sind, bedeutet das nicht, dass diese privat sind. Schaue dir diesen unverarbeiteten Inhalt einer HTTP-Post-Anfrage an, um herauszufinden, wieso:

```http
POST /path/subpath HTTP/1.0
From: john@example.com
User-Agent: someBrowser/1.0
Content-Type: application/x-www-form-urlencoded
Content-Length: 20

name=John+Doe&age=25
```

Wie du siehst, wird der Body genau wie der Abfragen-String kodiert. Das ist das von HTML-Formularen verwendete Standardformat. Mit JSON kannst du über Ajax auch mit Daten komplexerer Struktur arbeiten. Es gibt aber auch eine andere Kodierungsart: multipart/form-data. Diese wird für das Hochladen von Binärdateien verwendet. In dieser Übung wirst du jedoch URL-kodierten Body verwenden. Um die von POST-Anfragen erhaltenen Daten zu parsen, musst du das Paket `body-parser` verwenden. Dieses Paket erlaubt dir, eine Reihe von Middleware-Funktionen zu verwenden, mit welchen du Daten verschiedener Formate dekodieren kannst.

# --instructions--

`body-parser` wurde bereits installiert und befindet sich in deiner `package.json` Projektdatei. `require` es am Anfang der `myApp.js`-Datei und speicher es in einer Variable namens `bodyParser`. Die Middleware zur Verarbeitung von URL-kodierten Daten wird von `bodyParser.urlencoded({extended: false})` zurückgegeben. Übergib die Funktion, die durch den vorherigen Methodenaufruf zurückgegeben wurde, an `app.use()`. Wie üblich muss die Middleware vor allen Pfaden eingebaut werden, die von ihr abhängen.

**Hinweis:** `extended` ist eine Konfigurationsoption, die dem `body-parser` mitteilt, welches Parsing verwendet werden muss. Bei `extended=false` wird die klassische Kodierung der `querystring` Bibliothek verwendet. Ist `extended=true`, wird die Bibliothek `qs` zum Parsen verwendet.

Bei `extended=false` können Werte ausschließlich Strings oder Arrays sein. Das von `querystring` zurückgegebene Objekt erbt nicht prototypisch vom klassischen JavaScript-`Object`, weshalb Funktionen wie `hasOwnProperty` und `toString` nicht verwendbar sind. Zwar erlaubt die erweiterte Version mehr Datenflexibilität, wird aber von JSON übertroffen.

# --hints--

Die Middleware 'body-parser' sollte aufgesetzt werden

```js
  $.get(code + '/_api/add-body-parser').then(
    (data) => {
      assert.isAbove(
        data.mountedAt,
        0,
        '"body-parser" is not mounted correctly'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

