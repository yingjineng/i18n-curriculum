---
id: 5895f70cf9fc0f352b528e66
title: Serializzazione di un oggetto utente
challengeType: 2
forumTopicId: 301563
dashedName: serialization-of-a-user-object
---

# --description--

Serialization and deserialization are important concepts in regard to authentication. To serialize an object means to convert its contents into a small *key* that can then be deserialized into the original object. This is what allows us to know who has communicated with the server without having to send the authentication data, like the username and password, at each request for a new page.

Per una configurazione corretta, devi avere una funzione di serializzazione e una funzione di deserializzazione. In Passport, possono essere create con:

```javascript
passport.serializeUser(cb);
passport.deserializeUser(cb);
```

La funzione callback passata a `serializeUser` viene chiamata con due argomenti: l'oggetto utente completo e un callback utilizzato da passport.

Il callback accetta due argomenti: Un errore, se presente, e una chiave univoca per identificare l'utente che dovrebbe essere restituito nel callback. Utilizzerai l'`_id` dell'utente nell'oggetto. È garantito che sia unico, dato che è generato da MongoDB.

Analogamente, `deserializeUser` è chiamata con due argomenti: la chiave unica e una funzione callback.

Questo callback accetta due argomenti: Un errore, se presente, e l'oggetto utente completo. Per ottenere un oggetto utente completo, effettua una ricerca query per un `_id` Mongo, come mostrato di seguito:


```javascript
passport.serializeUser((user, done) => {
  done(null, user._id);
});

passport.deserializeUser((id, done) => {
  myDataBase.findOne({ _id: new ObjectID(id) }, (err, doc) => {
    done(null, null);
  });
});
```

Aggiungi le due funzioni sopra al tuo server. La classe `ObjectID` proviene dal pacchetto `mongodb`. `mongodb@~3.6.0` è già stato aggiunto come dipendenza. Dichiara questa classe con:

```javascript
const { ObjectID } = require('mongodb');
```

`deserializeUser` darà errore finché non imposti una connessione al database. Quindi, per ora, trasforma la chiamata `myDatabase.findOne` in un commento e chiama `done(null, null)` nella funzione callback `deserializeUser`.

Invia la tua pagina quando pensi che sia tutto corretto. Se incontri degli errori, puoi vedere <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#serialization-of-a-user-object-4" target="_blank" rel="noopener noreferrer nofollow">il progetto completato fino a questo punto</a>.

# --hints--

Dovresti serializzare correttamente l'oggetto utente.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /passport.serializeUser/gi,
    'You should have created your passport.serializeUser function'
  );
  assert.match(
    data,
    /null,\s*user._id/gi,
    'There should be a callback in your serializeUser with (null, user._id)'
  );
}
```

Dovresti deserializzare correttamente l'oggetto utente.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /passport.deserializeUser/gi,
    'You should have created your passport.deserializeUser function'
  );
  assert.match(
    data,
    /null,\s*null/gi,
    'There should be a callback in your deserializeUser with (null, null) for now'
  );
}
```

MongoDB dovrebbe essere una dipendenza.

```js
async () => {
  const url = new URL("/_api/package.json", code);
  const res = await fetch(url);
  const packJson = await res.json();
  assert.property(
    packJson.dependencies,
    'mongodb',
    'Your project should list "mongodb" as a dependency'
  );
}
```

Mongodb dovrebbe essere richiesto correttamente, includendo l'ObjectId.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /require.*("|')mongodb\1/gi,
    'You should have required mongodb'
  );
  assert.match(
    data,
    /new ObjectID.*id/gi,
    'Even though the block is commented out, you should use new ObjectID(id) for when we add the database'
  );
}
```

