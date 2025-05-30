---
id: 589fc831f9fc0f352b528e77
title: Authentifizierung mit Socket.IO
challengeType: 2
forumTopicId: 301548
dashedName: authentication-with-socket-io
---

# --description--

Currently, you cannot determine who is connected to your web socket. While `req.user` contains the user object, that's only when your user interacts with the web server, and with web sockets you have no `req` (request) and therefore no user data. One way to solve the problem of knowing who is connected to your web socket is by parsing and decoding the cookie that contains the passport session then deserializing it to obtain the user object. Luckily, there is a package on NPM just for this that turns a once complex task into something simple!

`passport.socketio@~3.7.0`, `connect-mongo@~3.2.0` und `cookie-parser@~1.4.5` wurden bereits als Abhängigkeiten hinzugefügt. Fordere sie jeweils als `passportSocketIo`, `MongoStore` und `cookieParser` an. Zudem müssen wir mithilfe von `express-session`, das wir zuvor angefordert haben, einen neuen Speicher initialisieren. So sollte das aussehen:

```js
const MongoStore = require('connect-mongo')(session);
const URI = process.env.MONGO_URI;
const store = new MongoStore({ url: URI });
```

Jetzt müssen wir Socket.IO nur noch mitteilen, diesen zu verwenden und Optionen festlegen. Stelle sicher, dass dies vor dem bestehenden Socket-Code hinzugefügt wird und nicht in den bestehenden Verbindungs-Listener. Für deinen Server sollte das so aussehen:

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

Die Konfiguration einer Passport-Authentifizierung für Socket.IO ähnelt der Art, wie wir die `session`-Middleware für die API konfiguriert haben, übrigens sehr. Das liegt daran, dass sie dazu bestimmt sind, dieselbe Authentifizierungsmethode zu verwenden – Sitzungs-ID eines Cookie abrufen und validieren.

Zuvor haben wir bei der Konfiguration der `session`-Middleware den Cookie-Namen für die Sitzung (`key`) nicht explizit festgelegt. Schlicht, weil das `session`-Paket den Standardwert nutzte. Nun, da wir ein weiteres Paket hinzugefügt haben, welches Zugriff auf denselben Wert der Cookies benötigt, müssen wir explizit den `key`-Wert in beiden Konfigurationsobjekten setzen.

Achte darauf, den `key` mit dem Cookie-Namen zur `session`-Middleware hinzuzufügen, die zum Socket.IO-Schlüssel passt. Füge zudem die `store`-Referenz – in der Nähe von `saveUninitialized: true` – den Optionen hinzu. Das ist notwendig, um Socket.IO mitzuteilen, auf welche Sitzung es sich zu beziehen hat.

<hr />

Definiere nun die `success`- und `fail`-Callback-Funktionen:

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

Das Nutzerobjekt steht deinem Socket-Objekt nun als `socket.request.user` zur Verfügung. Jetzt kannst du zum Beispiel folgendes hinzufügen:

```js
console.log('user ' + socket.request.user.username + ' connected');
```

Dadurch wird in der Serverkonsole protokolliert, wer eine Verbindung hergestellt hat.

Reiche deine Seite ein, wenn du davon ausgehst, alles richtig gemacht zu haben. Wenn du auf Fehler stößt, kannst du <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#authentication-with-socketio-9" target="_blank" rel="noopener noreferrer nofollow">das Projekt bis zu diesem Punkt überprüfen</a>.

# --hints--

`passport.socketio` sollte eine Abhängigkeit sein.

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

`cookie-parser` sollte eine Abhängigkeit sein.

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

passportSocketIo sollte ordnungsgemäß angefordert werden.

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

passportSocketIo sollte ordnungsgemäß eingestellt werden.

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

