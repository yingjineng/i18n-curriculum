---
id: 589fc831f9fc0f352b528e76
title: Verbindungsabbruch verarbeiten
challengeType: 2
forumTopicId: 301552
dashedName: handle-a-disconnect
---

# --description--

You may notice that up to now you have only been increasing the user count. Handling a user disconnecting is just as easy as handling the initial connect, except you have to listen for it on each socket instead of on the whole server.

Füge zu diesem Zweck dem bestehenden `'connect'`-Listener einen weiteren Listener hinzu, der auf `'disconnect'`-Ereignisse des Sockets wartet, ohne dass Daten durchgelassen werden. Du kannst diese Funktionalität testen, indem du einfach an die Konsole loggst, dass ein Nutzer die Verbindung abgebrochen hat.

```js
socket.on('disconnect', () => {
  /*anything you want to do on disconnect*/
});
```

Um sicherzustellen, dass Clients immer über aktuelle Nutzerzahlen verfügen, solltest du `currentUsers` um 1 verringern, wenn die Verbindung unterbrochen wird und dann das Ereignis `'user count'` mit der aktualisierten Anzahl ausgeben.

**Hinweis:** Wie bei `'disconnect'` sollten auch alle anderen Ereignisse, die ein Socket an den Server übertragen kann, innerhalb des Verbindungsaufbau-Listeners verarbeitet werden, in welchem wir 'socket' definiert haben.

Reiche deine Seite ein, wenn du davon ausgehst, alles richtig gemacht zu haben. Wenn du auf Fehler stößt, kannst du <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#handle-a-disconnect-8" target="_blank" rel="noopener noreferrer nofollow">das bis zu diesem Punkt abgeschlossene Projekt überprüfen</a>.

# --hints--

Der Server sollte das disconnect-Ereignis des Sockets verarbeiten.

```js
async () => {
  const url = new URL("/_api/server.js", code);
  const res = await fetch(url);
  const data = await res.text();
  assert.match(data, /socket.on.*('|")disconnect('|")/s, '');
}
```

Dein Client sollte auf das Ereignis `'user count'` warten.

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

