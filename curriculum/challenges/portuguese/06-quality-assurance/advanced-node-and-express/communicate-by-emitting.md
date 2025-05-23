---
id: 589fc831f9fc0f352b528e75
title: Comunicar por envio
challengeType: 2
forumTopicId: 301550
dashedName: communicate-by-emitting
---

# --description--

<dfn>Emit</dfn> is the most common way of communicating you will use. When you emit something from the server to 'io', you send an event's name and data to all the connected sockets. A good example of this concept would be emitting the current count of connected users each time a new user connects!

Comece adicionando uma variável para manter o controle dos usuários, logo antes do local onde você está escutando as conexões no momento.

```js
let currentUsers = 0;
```

Agora, quando alguém se conecta, você deve incrementar a contagem antes de enviá-la. Então, você vai querer adicionar o incrementador dentro do listener de conexões.

```js
++currentUsers;
```

Por fim, depois de incrementar a contagem, você deve enviar o evento (ainda dentro do listener de conexão). O evento deve ser nomeado 'user count' e o dado devem ser simplesmente `currentUsers`.

```js
io.emit('user count', currentUsers);
```

Agora, você pode implementar uma maneira de o client escutar este evento! De modo semelhante a escutar uma conexão no servidor, você usará a palavra-chave `on`.

```js
socket.on('user count', function(data) {
  console.log(data);
});
```

Agora, tente carregar o seu aplicativo, autentique-se e você deve ver no console do client '1', representando a contagem de usuários no momento! Tente carregar mais clients, e autenticar para ver o número subir.

Envie sua página quando você achar que ela está certa. Se você estiver encontrando erros, pode <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#communicate-by-emitting-7" target="_blank" rel="noopener noreferrer nofollow">conferir o projeto concluído até este ponto</a>.

# --hints--

`currentUsers` deve ser definido.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /currentUsers/s,
    'You should have variable currentUsers defined'
  );
}
```

O servidor deve enviar o contador atual a cada nova conexão.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /io.emit.*('|")user count('|").*currentUsers/s,
    'You should emit "user count" with data currentUsers'
  );
}
```

O client deve estar escutando o evento `'user count'`.

```js
async () => {
  const url = new URL("/public/client.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(
    data,
    /socket.on.*('|")user count('|")/s,
    'Your client should be connection to server with the connection defined as socket'
  );
}
```

