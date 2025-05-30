---
id: 5895f70df9fc0f352b528e6a
title: Criar um novo middleware
challengeType: 2
forumTopicId: 301551
dashedName: create-new-middleware
---

# --description--

As is, any user can just go to `/profile` whether they have authenticated or not by typing in the URL. You want to prevent this by checking if the user is authenticated first before rendering the profile page. This is the perfect example of when to create a middleware.

O desafio aqui é cria a função do middleware `ensureAuthenticated(req, res, next)`, que vai verificar se um usuário está autenticado chamando o método `isAuthenticated` do Passport na `request` (solicitação), que verificará se `req.user` está definido. Se estiver, então `next()` deve ser chamado. Caso contrário, você pode apenas responder ao pedido com um redirecionamento à página inicial para fazer o login.

Uma implementação deste middleware é:

```javascript
function ensureAuthenticated(req, res, next) {
  if (req.isAuthenticated()) {
    return next();
  }
  res.redirect('/');
};
```

Crie a função de middleware acima e, em seguida, passe `ensureAuthenticated` como middleware para requisições de perfil antes do argumento para a requisição GET:

```javascript
app
 .route('/profile')
 .get(ensureAuthenticated, (req,res) => {
    res.render('profile');
 });
```

Envie sua página quando você achar que ela está certa. Se você estiver encontrando erros, pode <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#create-new-middleware-8" target="_blank" rel="noopener noreferrer nofollow">conferir o projeto concluído até este ponto</a>.

# --hints--

O middleware `ensureAuthenticated` deve ser implementado e anexado à rota `/profile`.

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

Uma solicitação GET não autenticado para `/profile` deve redirecionar corretamente para `/`.

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

