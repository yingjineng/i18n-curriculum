---
id: 587d7fb1367417b2b2512bf3
title: Implementare un middleware logger di richiesta a livello radice
challengeType: 2
forumTopicId: 301514
dashedName: implement-a-root-level-request-logger-middleware
---

# --description--

Earlier, you were introduced to the `express.static()` middleware function. Now it’s time to see what middleware is, in more detail. Middleware functions are functions that take 3 arguments: the request object, the response object, and the next function in the application’s request-response cycle. These functions execute some code that can have side effects on the app, and usually add information to the request or response objects. They can also end the cycle by sending a response when some condition is met. If they don’t send the response when they are done, they start the execution of the next function in the stack. This triggers calling the 3rd argument, `next()`.

Considera l'esempio seguente:

```js
function(req, res, next) {
  console.log("I'm a middleware...");
  next();
}
```

Supponiamo che tu abbia montato questa funzione su una rotta. Quando una richiesta corrisponde alla rotta, mostrerà la stringa “I’m a middleware…”, dopodiché eseguirà la funzione successiva nello stack. In questo esercizio, costruirai un middleware a livello di radice. Come hai visto nella sfida 4, per montare una funzione middleware a livello di radice, puoi usare il metodo `app.use(<mware-function>)`. In questo caso, la funzione verrà eseguita per tutte le richieste, ma è anche possibile impostare condizioni più specifiche. Ad esempio, se desideri che una funzione venga eseguita solo per le richieste POST, puoi utilizzare `app.post(<mware-function>)`. Esistono metodi analoghi per tutti i verbi HTTP (GET, DELETE, PUT, …).

# --instructions--

Costruisci un semplice logger. Per ogni richiesta, esso dovrebbe scrivere nella console una stringa con il seguente formato: `method path - ip`. L'output dovrebbe assomigliare a questo: `GET /json - ::ffff:127.0.0.1`. Nota che c'è uno spazio tra `method` e `path` e che il trattino che separa `path` e `ip` è circondato da uno spazio su entrambi i lati. Puoi ottenere il metodo di richiesta (il verbo http), il percorso relativo e l'ip del chiamante dall'oggetto request utilizzando `req.method`, `req.path` e `req.ip`. Ricordati di chiamare `next()` quando hai finito, o il tuo server rimarrà bloccato per sempre. Assicurati di avere il 'Logs' aperto, e guarda cosa succede quando arriva qualche richiesta.

**Nota:** Express valuta le funzioni nell'ordine in cui appaiono nel codice. Questo vale anche per i middleware. Se vuoi che funzioni per tutte le rotte, dovresti montarlo prima di loro.

# --hints--

Il middleware del logger di livello radice dovrebbe essere attivo

```js
  $.get(code + '/_api/root-middleware-logger').then(
    (data) => {
      assert.isTrue(
        data.passed,
        'root-level logger is not working as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

