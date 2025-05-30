---
id: 589fc831f9fc0f352b528e77
title: Autenticar com o Socket.IO
challengeType: 2
forumTopicId: 301548
dashedName: authentication-with-socket-io
---

# --description--

Currently, you cannot determine who is connected to your web socket. While `req.user` contains the user object, that's only when your user interacts with the web server, and with web sockets you have no `req` (request) and therefore no user data. One way to solve the problem of knowing who is connected to your web socket is by parsing and decoding the cookie that contains the passport session then deserializing it to obtain the user object. Luckily, there is a package on NPM just for this that turns a once complex task into something simple!

`passport.socketio@~3.7.0`, `connect-mongo@~3.2.0` e `cookie-parser@~1.4.5` já foram instalados como dependências. Solicite-os como `passportSocketIo`, `MongoStore` e `cookieParser`, respectivamente. Além disso, precisamos inicializar uma nova store de memória, a partir do `express-session` que solicitamos anteriormente. Deve ficar assim:

```js
const MongoStore = require('connect-mongo')(session);
const URI = process.env.MONGO_URI;
const store = new MongoStore({ url: URI });
```

Agora, só precisamos dizer ao Socket.IO para usá-la e definir as opções. Certifique-se de que ela foi adicionada antes do código do socket existente e não no listener das conexões existentes. Para o servidor, ele deve ficar assim:

```js
io.use(
  passportSocketIo.authorize({
    cookieParser: cookieParser,
    key: 'express.sid',
    secret: process.env.SESSION_SECRET,
    store: store,
    success: onAuthorizeSuccess,
    fail: onAuthorizeFail
  })
);
```

Observe que configurar a autenticação do Passport para o Socket.IO é muito parecido com a maneira como configuramos o middleware `session` para a API. Isso ocorre porque eles devem usar o mesmo método de autenticação — obter o id da sessão de um cookie e validá-lo.

Anteriormente, quando configuramos o middleware `session`, não definimos explicitamente o nome do cookie para a sessão (`key`). Isso ocorre porque o pacote de `session` estava usando o valor padrão. Agora que adicionamos outro pacote que precisa acessar o mesmo valor a partir dos cookies, precisamos definir explicitamente o valor de `key` em ambos os objetos de configuração.

Certifique-se de adicionar `key` com o nome do cookie para o middleware `session` que corresponde à chave do Socket.IO. Além disso, adicione a referência de `store` às opções, perto de onde configuramos `saveUninitialized: true`. Isto é necessário para informar ao SocketIO a qual sessão ele deve se relacionar.

<hr />

Agora, defina as funções de `success` e `fail` nas funções de callback:

```js
function onAuthorizeSuccess(data, accept) {
  console.log('successful connection to socket.io');

  accept(null, true);
}

function onAuthorizeFail(data, message, error, accept) {
  if (error) throw new Error(message);
  console.log('failed connection to socket.io:', message);
  accept(null, false);
}
```

Agora, o objeto de usuário está acessível no objeto de socket como `socket.request.user`. Por exemplo, agora, você pode adicionar o seguinte:

```js
console.log('user ' + socket.request.user.username + ' connected');
```

Ele vai logar no console do servidor que está conectado!

Envie sua página quando você achar que ela está certa. Se você estiver encontrando erros, pode <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#authentication-with-socketio-9" target="_blank" rel="noopener noreferrer nofollow">conferir o projeto até este ponto</a>.

# --hints--

`passport.socketio` deve ser uma dependência.

```js
async () => {
  const url = new URL("/_api/package.json", code);
  const res = await fetch(url);
  const packJson = await res.json();
  assert.property(
    packJson.dependencies,
    'passport.socketio',
    'Your project should list "passport.socketio" as a dependency'
  );
}
```

`cookie-parser` deve ser uma dependência.

```js
async () => {
  const url = new URL("/_api/package.json", code);
  const res = await fetch(url);
  const packJson = await res.json();
  assert.property(
    packJson.dependencies,
    'cookie-parser',
    'Your project should list "cookie-parser" as a dependency'
  );
}
```

O passportSocketIo deve ser solicitado adequadamente.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /require\((['"])passport\.socketio\1\)/gi,
    'You should correctly require and instantiate "passport.socketio"'
  );
}
```

O passportSocketIo deve ser configurado adequadamente.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /io\.use\(\s*\w+\.authorize\(/,
    'You should register "passport.socketio" as socket.io middleware and provide it correct options'
  );
}
```

