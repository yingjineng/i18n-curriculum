---
id: 587d7fb2367417b2b2512bf8
title: Ottenere dati dalle richieste POST
challengeType: 2
forumTopicId: 301511
dashedName: get-data-from-post-requests
---

# --description--

Mount a POST handler at the path `/name`. It’s the same path as before. We have prepared a form in the html frontpage. It will submit the same data of exercise 10 (Query string). If the body-parser is configured correctly, you should find the parameters in the object `req.body`. Have a look at the usual library example:

<blockquote>route: POST '/library'<br>urlencoded_body: userId=546&#x26;bookId=6754 <br>req.body: {userId: '546', bookId: '6754'}</blockquote>

Rispondi con lo stesso oggetto JSON di prima: `{name: 'firstname lastname'}`. Verifica se il tuo endpoint funziona utilizzando il modulo html che abbiamo fornito nella pagina principale dell'app.

Suggerimento: ci sono diversi altri metodi http diversi da GET e POST. E per convenzione c'è una corrispondenza tra il verbo http, e l'operazione che si sta per eseguire sul server. La mappatura convenzionale è:

POST (talvolta PUT) - Crea una nuova risorsa utilizzando le informazioni inviate con la richiesta,

GET - Leggi una risorsa esistente senza modificarla,

PUT o PATCH (a volte POST) - Aggiorna una risorsa utilizzando i dati inviati,

DELETE = Elimina una risorsa.

Ci sono anche un paio di altri metodi che vengono utilizzati per negoziare una connessione con il server. Except for GET, all the other methods listed above can have a payload (i.e. the data into the request body). Il middleware body-parser funziona anche con questi metodi.

# --hints--

Test 1: Il tuo endpoint API dovrebbe rispondere con il nome corretto

```js
  $.post(code + '/name', { first: 'Mick', last: 'Jagger' }).then(
    (data) => {
      assert.equal(
        data.name,
        'Mick Jagger',
        'Test 1: "POST /name" route does not behave as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Test 2: Il tuo endpoint API dovrebbe rispondere con il nome corretto

```js
  $.post(code + '/name', {
    first: 'Keith',
    last: 'Richards'
  }).then(
    (data) => {
      assert.equal(
        data.name,
        'Keith Richards',
        'Test 2: "POST /name" route does not behave as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

