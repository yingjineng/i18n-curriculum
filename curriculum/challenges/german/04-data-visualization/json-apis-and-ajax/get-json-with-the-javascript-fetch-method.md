---
id: 5ccfad82bb2dc6c965a848e5
title: Abrufen von JSON mit der JavaScript-Abrufmethode
challengeType: 6
forumTopicId: 301501
dashedName: get-json-with-the-javascript-fetch-method
---

# --description--

Another way to request external data is to use the JavaScript `fetch()` method. It is equivalent to `XMLHttpRequest`, but the syntax is considered easier to understand.

Hier ist der Code für eine GET-Anfrage an `/json/cats.json`

```js
fetch('/json/cats.json')
  .then(response => response.json())
  .then(data => {
    document.getElementById('message').innerHTML = JSON.stringify(data);
  });
```

Note: The `fetch()` method uses `GET` as the default `HTTP` method. This means you don’t need to specify it explicitly for basic data retrieval.

Schau dir jeden einzelnen Teil dieses Codes an.

Die erste Zeile ist diejenige, die den Antrag stellt. `fetch(URL)` stellt also eine `GET`-Anfrage an die angegebene URL. Die Methode gibt ein Promise zurück.

Nachdem ein Promise zurückgegeben wurde, wird bei erfolgreicher Anfrage die Methode `then` ausgeführt, die die Antwort in das JSON-Format konvertiert.

Die `then`-Methode gibt auch ein Promise zurück, das von der nächsten `then`-Methode bearbeitet wird. Das Argument im zweiten `then` ist das JSON-Objekt, nach dem du suchst!

Es wählt nun das Element aus, das die Daten erhalten soll, indem es `document.getElementById()` verwendet. Es ändert dann den HTML-Code des Elements, indem es ein String einfügt, das aus dem von der Anfrage zurückgegebenen JSON-Objekt erstellt wurde.

# --instructions--

Aktualisiere den Code, um eine `GET`-Anfrage an die freeCodeCamp Katzen-Foto-API zu erstellen und zu senden. Diesmal aber mit der Methode `fetch` anstelle von `XMLHttpRequest`.

# --hints--

Dein Code sollte die abgerufenen Daten verwenden, um das innere HTML zu ersetzen

```js
const catData = 'dummy data';
const ref = fetch;
fetch = () => Promise.resolve({ json: () => catData });
async () => {
  try {
    document.getElementById('getMessage').click();
    await new Promise((resolve, reject) => setTimeout(() => resolve(), 250));
  } catch (error) {
    console.log(error);
  } finally {
    fetch = ref;
    assert.equal(
      document.getElementById('message').textContent,
      JSON.stringify(catData)
    );
  }
};
```

Dein Code sollte eine `GET`-Anfrage mit `fetch` stellen.

```js
assert.match(code, /fetch\s*\(\s*('|")\/json\/cats\.json\1\s*\)/g);
```

Dein Code sollte `then` verwenden, um die Antwort in JSON zu konvertieren.

```js
assert.match(
  code,
  /\.then\s*\(\s*\(?(?<var>\w+)\)?\s*=>\s*\k<var>\s*\.json\s*\(\s*\)\s*\)/g
);
```

Dein Code sollte `then` verwenden, um die Daten zu verarbeiten, die von dem anderen `then` in JSON umgewandelt wurden.

```js
assert.match(__helpers.removeWhiteSpace(code), /\.then\(\(?\w+\)?=>{[^}]*}\)/g);
```

Dein Code sollte das Element mit der ID `message` erhalten und sein inneres HTML in den String der JSON-Daten ändern.

```js
assert.match(
  __helpers.removeWhiteSpace(code),
  /document\.getElementById\(('|")message\1\)\.innerHTML=JSON\.stringify\(?\w+\)/g
);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('getMessage').onclick = () => {
      // Add your code below this line
      // Add your code above this line
    };
  });
</script>
<style>
  body {
    text-align: center;
    font-family: 'Helvetica', sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0f5897;
    border: 1px solid #0f5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p id="message" class="box">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```

# --solutions--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('getMessage').onclick = () => {
      fetch('/json/cats.json')
        .then(response => response.json())
        .then(data => {
          document.getElementById('message').innerHTML = JSON.stringify(data);
        });
    };
  });
</script>
<style>
  body {
    text-align: center;
    font-family: 'Helvetica', sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0f5897;
    border: 1px solid #0f5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p id="message" class="box">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```
