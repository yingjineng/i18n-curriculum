---
id: 5895f70ef9fc0f352b528e6b
title: Mettere insieme un profilo
challengeType: 2
forumTopicId: 301554
dashedName: how-to-put-a-profile-together
---

# --description--

Now that you can ensure the user accessing the `/profile` is authenticated, you can use the information contained in `req.user` on your page.

Passa un oggetto contenente la proprietà `username` e il valore di `req.user.username` come secondo argomento per il metodo `render` della vista del profilo.

Quindi, vai alla tua vista `profile.pug` e aggiungi la seguente riga sotto l'elemento `h1` esistente, e allo stesso livello di indentazione:

```pug
h2.center#welcome Welcome, #{username}!
```

Questo crea un elemento `h2` di classe `center` e con id `welcome` contenente il testo `Welcome,` seguito dal nome utente.

Inoltre, in `profile.pug`, aggiungi un link relativo alla rotta `/logout`, che ospiterà la logica per disconnettere un utente:

```pug
a(href='/logout') Logout
```

Invia la tua pagina quando pensi che sia tutto corretto. Se incontri degli errori, puoi vedere <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#how-to-put-a-profile-together-9" target="_blank" rel="noopener noreferrer nofollow">il progetto completato fino a questo punto</a>.

# --hints--

Dovresti aggiungere correttamente una variabile di rendering Pug a `/profile`.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /username:( |)req.user.username/,
    'You should be passing the variable username with req.user.username into the render function of the profile page'
  );
}
```

