---
id: 5895f70df9fc0f352b528e6a
title: Creare un nuovo middleware
challengeType: 2
forumTopicId: 301551
dashedName: create-new-middleware
---

# --description--

As is, any user can just go to `/profile` whether they have authenticated or not by typing in the URL. You want to prevent this by checking if the user is authenticated first before rendering the profile page. This is the perfect example of when to create a middleware.

La sfida consiste nel creare la funzione middleware `ensureAuthenticated(req, res, next)`, che controlla se un utente è autenticato o meno invocando il metodo di Passport `isAuthenticated` su `request`, che controlla se `req.user` è definito. Se lo è, allora `next()` dovrebbe essere chiamata. Altrimenti, puoi solo rispondere alla richiesta con un reindirizzamento alla tua homepage per effettuare il login.

Una implementazione di questo middleware è:

```javascript
function ensureAuthenticated(req, res, next) {
  if (req.isAuthenticated()) {
    return next();
  }
  res.redirect('/');
};
```

Crea la funzione middleware qui sopra, poi passa `ensureAuthenticated` come middleware per le richieste per la pagina di profilo prima dell'argomento della richiesta GET:

```javascript
app
 .route('/profile')
 .get(ensureAuthenticated, (req,res) => {
    res.render('profile');
 });
```

Invia la tua pagina quando pensi di averlo fatto correttamente. Se incontri degli errori, puoi vedere <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#create-new-middleware-8" target="_blank" rel="noopener noreferrer nofollow">il progetto completato fino a questo punto</a>.

# --hints--

Il middleware `ensureAuthenticated` dovrebbe essere implementato e associato alla rotta `/profile`.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /ensureAuthenticated[^]*req.isAuthenticated/,
    'Your ensureAuthenticated middleware should be defined and utilize the req.isAuthenticated function'
  );
  assert.match(
    data,
    /profile[^]*get[^]*ensureAuthenticated/,
    'Your ensureAuthenticated middleware should be attached to the /profile route'
  );
}
```

Una richiesta GET non autenticata a `/profile` dovrebbe reindirizzare correttamente a `/`.

```js
async () => {
  const url = new URL("/profile", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /Home page/,
    'An attempt to go to the profile at this point should redirect to the homepage since we are not logged in'
  );
}
```

