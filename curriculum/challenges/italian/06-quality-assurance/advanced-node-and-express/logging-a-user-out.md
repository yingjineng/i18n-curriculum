---
id: 58965611f9fc0f352b528e6c
title: De-autenticare un utente
challengeType: 2
forumTopicId: 301560
dashedName: logging-a-user-out
---

# --description--

Creating the logout logic is easy. The route should just unauthenticate the user, and redirect to the home page instead of rendering any view.

In passport, per de-autenticare un utente è sufficiente invocare `req.logout()` prima del reindirizzamento. Aggiungi questa rotta `/logout` per farlo:

```js
app.route('/logout')
  .get((req, res) => {
    req.logout();
    res.redirect('/');
});
```

Potresti aver notato che non stai gestendo pagine mancanti (404). Il modo comune per gestirle in Node è con il seguente middleware. Prosegui e aggiungilo dopo tutte le tue rotte:

```js
app.use((req, res, next) => {
  res.status(404)
    .type('text')
    .send('Not Found');
});
```

Invia la tua pagina quando pensi di averlo fatto correttamente. Se incontri degli errori, puoi vedere <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#logging-a-user-out-10" target="_blank" rel="noopener noreferrer nofollow">il progetto completato fino a questo punto</a>.

# --hints--

`req.Logout` dovrebbe essere invocato nella tua rotta `/logout`.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /req.logout/gi,
    'You should be calling req.logout() in your /logout route'
  );
}
```

`/logout` dovrebbe reindirizzare alla home page.

```js
async () => {
  const url = new URL("/logout", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /Home page/gi,
    'When a user logs out they should be redirected to the homepage'
  );
}
```

