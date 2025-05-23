---
id: 587d7faf367417b2b2512be9
title: Inviare dati con il metodo XMLHttpRequest di JavaScript
challengeType: 6
forumTopicId: 301504
dashedName: post-data-with-the-javascript-xmlhttprequest-method
---

# --description--

In the previous examples, you received data from an external resource. You can also send data to an external resource, as long as that resource supports AJAX requests and you know the URL.

Il metodo `XMLHttpRequest` è anche usato per mandare dati ad un server. Ecco un esempio:

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

Hai già visto molti di questi metodi. Qui il metodo `open` inizializza la richiesta come `POST` all'URL specificato della risorsa esterna, e passa `true` come terzo parametro - indicando l'esecuzione di un'operazione asincrona.

Il metodo `setRequestHeader` imposta il valore di un'intestazione di richiesta HTTP, che contiene informazioni sul mittente e sulla richiesta. Deve essere chiamato dopo il metodo `open`, ma prima del metodo `send`. I due parametri sono il nome dell'intestazione e il valore da impostare come corpo di quell'intestazione.

Successivamente, il listener dell'evento `onreadystatechange` gestisce un cambiamento nello stato della richiesta. Un `readyState` di `4` significa che l'operazione è completata, e uno `status` di `201` significa che la richiesta ha avuto successo. Pertanto, l'HTML del documento può essere aggiornato.

Infine, il metodo `send` invia la richiesta con il valore `body`. Il `body` è costituito da uno `userName` e un `suffix` chiave.

# --instructions--

Aggiorna il codice in modo da fare una richiesta `POST` all'endpoint API. Quindi digita il nome nel campo di input e fai click su `Send Message`. La funzione AJAX dovrebbe sostituire `Reply from Server will be here.` con i dati dal server. Formatta la risposta per mostrare il tuo nome con l'aggiunta del testo `loves cats`.

# --hints--

Il tuo codice dovrebbe creare una nuova `XMLHttpRequest`.

```js
assert.match(code, /new\s*XMLHttpRequest\(\s*\)/g);
```

Il tuo codice dovrebbe utilizzare il metodo `open` per inizializzare una richiesta `POST` al server.

```js
assert.match(code, /\.open\(\s*('|")POST\1\s*,\s*url\s*,\s*true\s*\)/g);
```

Il tuo codice dovrebbe utilizzare il metodo `setRequestHeader`.

```js
assert.match(
  code,
  /\.setRequestHeader\(\s*('|")Content-Type\1\s*,\s*('|")application\/json;\s*charset=UTF-8\2\s*\)/g
);
```

Il tuo codice dovrebbe avere un gestore di eventi `onreadystatechange` impostato a una funzione.

```js
assert.match(code, /\.onreadystatechange\s*=/g);
```

Il tuo codice dovrebbe ottenere l'elemento di classe `message` e cambiare il suo `textContent` in `userName loves cats`

```js
assert.match(
  code,
  /document\.getElementsByClassName\(\s*('|")message\1\s*\)\[0\]\.textContent\s*=\s*.+?\.userName\s*\+\s*.+?\.suffix/g
);
```

Il tuo codice dovrebbe usare il metodo `send`.

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
