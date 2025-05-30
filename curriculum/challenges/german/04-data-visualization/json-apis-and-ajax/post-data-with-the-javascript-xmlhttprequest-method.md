---
id: 587d7faf367417b2b2512be9
title: Daten mit der JavaScript-Methode XMLHttpRequest übermitteln
challengeType: 6
forumTopicId: 301504
dashedName: post-data-with-the-javascript-xmlhttprequest-method
---

# --description--

In the previous examples, you received data from an external resource. You can also send data to an external resource, as long as that resource supports AJAX requests and you know the URL.

Die JavaScript Methode `XMLHttpRequest` wird auch verwendet, um Daten an einen Server zu übermitteln. Hier ein Beispiel:

```js
const xhr = new XMLHttpRequest();
xhr.open('POST', url, true);
xhr.setRequestHeader('Content-Type', 'application/json; charset=UTF-8');
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 201) {
    const serverResponse = JSON.parse(xhr.response);
    document.getElementsByClassName('message')[0].textContent =
      serverResponse.userName + serverResponse.suffix;
  }
};
const body = JSON.stringify({ userName: userName, suffix: ' loves cats!' });
xhr.send(body);
```

Du hast bereits mehrere dieser Methoden gesehen. Hier initialisiert die `open`-Methode die Anfrage als `POST` an die gegebene URL der externen Ressource und übergibt `true` als dritten Parameter - was angibt, dass die Operation asynchron durchgeführt werden soll.

Die Methode `setRequestHeader` legt den Wert eines HTTP-Request-Headers fest, der Informationen über den Absender und die Anfrage enthält. Es muss nach der `open`-Methode, aber noch vor der `send`-Methode aufgerufen werden. Die beiden Parameter sind der Name des Headers und der Wert, der als der Körper des Headers festgelegt werden soll.

Als Nächstes bearbeitet der `onreadystatechange`-Event-Listener eine Änderung des Status der Anfrage. Ein `readyState` von `4` bedeutet, dass die Operation abgeschlossen ist und ein `status` von `201` bedeutet, dass es eine erfolgreiche Anfrage war. Daher kann der HTML-Code des Dokuments aktualisiert werden.

Schließlich sendet die `send`-Methode die Anfrage mit dem `body`-Wert ab. Der `body` besteht aus einem `userName` und einem `suffix`-Schlüssel.

# --instructions--

Aktualisiere den Code so, dass er eine `POST`-Anfrage an den API-Endpunkt stellt. Gib dann deinen Namen in das Eingabefeld ein und klicke auf `Send Message`. Deine AJAX Funktion sollte `Reply from Server will be here.` durch Daten vom Server ersetzen. Formatiere die Antwort so, dass dein Name zusammen mit dem Text `loves cats` angezeigt wird.

# --hints--

Dein Code sollte eine neue `XMLHttpRequest` erstellen.

```js
assert.match(code, /new\s*XMLHttpRequest\(\s*\)/g);
```

Dein Code sollte die `open`-Methode verwenden, um eine `POST`-Anfrage an den Server zu senden.

```js
assert.match(code, /\.open\(\s*('|")POST\1\s*,\s*url\s*,\s*true\s*\)/g);
```

Dein Code sollte die `setRequestHeader`-Methode verwenden.

```js
assert.match(
  code,
  /\.setRequestHeader\(\s*('|")Content-Type\1\s*,\s*('|")application\/json;\s*charset=UTF-8\2\s*\)/g
);
```

Dein Code sollte einen `onreadystatechange` Event-Handler auf eine Funktion gesetzt haben.

```js
assert.match(code, /\.onreadystatechange\s*=/g);
```

Dein Code sollte das Element mit der Klasse `message` erhalten und dessen `textContent` zu `userName loves cats` ändern

```js
assert.match(
  code,
  /document\.getElementsByClassName\(\s*('|")message\1\s*\)\[0\]\.textContent\s*=\s*.+?\.userName\s*\+\s*.+?\.suffix/g
);
```

Dein Code sollte die `send`-Methode verwenden.

```js
assert.match(code, /\.send\(\s*body\s*\)/g);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('sendMessage').onclick = function () {
      const userName = document.getElementById('name').value;
      const url = 'https://jsonplaceholder.typicode.com/posts';
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

<h1>Cat Friends</h1>
<p class="message box">Reply from Server will be here</p>
<p>
  <label for="name"
    >Your name:
    <input type="text" id="name" />
  </label>
  <button id="sendMessage">Send Message</button>
</p>
```

# --solutions--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('sendMessage').onclick = function () {
      const userName = document.getElementById('name').value;
      const url = 'https://jsonplaceholder.typicode.com/posts';
      // Add your code below this line
      const xhr = new XMLHttpRequest();
      xhr.open('POST', url, true);
      xhr.setRequestHeader('Content-Type', 'application/json; charset=UTF-8');
      xhr.onreadystatechange = function () {
        if (xhr.readyState === 4 && xhr.status === 201) {
          const serverResponse = JSON.parse(xhr.response);
          document.getElementsByClassName('message')[0].textContent =
            serverResponse.userName + serverResponse.suffix;
        }
      };
      const body = JSON.stringify({
        userName: userName,
        suffix: ' loves cats!'
      });
      xhr.send(body);
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

<h1>Cat Friends</h1>
<p class="message">Reply from Server will be here</p>
<p>
  <label for="name"
    >Your name:
    <input type="text" id="name" />
  </label>
  <button id="sendMessage">Send Message</button>
</p>
```
