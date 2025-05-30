---
id: 589fc831f9fc0f352b528e77
title: Автентифікація за допомогою Socket.IO
challengeType: 2
forumTopicId: 301548
dashedName: authentication-with-socket-io
---

# --description--

Currently, you cannot determine who is connected to your web socket. While `req.user` contains the user object, that's only when your user interacts with the web server, and with web sockets you have no `req` (request) and therefore no user data. One way to solve the problem of knowing who is connected to your web socket is by parsing and decoding the cookie that contains the passport session then deserializing it to obtain the user object. Luckily, there is a package on NPM just for this that turns a once complex task into something simple!

`passport.socketio@~3.7.0`, `connect-mongo@~3.2.0` та `cookie-parser@~1.4.5` вже додані як залежності. Вимагайте їх як `passportSocketIo`, `MongoStore` та `cookieParser` відповідно. Крім того, нам потрібно ініціалізувати нове сховище пам’яті з `express-session`, яке ми вимагали раніше. Це має виглядати ось так:

```js
const MongoStore = require('connect-mongo')(session);
const URI = process.env.MONGO_URI;
const store = new MongoStore({ url: URI });
```

Тепер треба лише вказати Socket.IO використовувати його та встановити налаштування. Переконайтеся, що його додано перед наявним кодом сокета, а не в наявному слухачі приєднання. На вашому сервері це повинно мати такий вигляд:

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

Зауважте, що налаштування автентифікації Passport для Socket.IO подібне до налаштування проміжного програмного забезпечення `session` для API. Це пояснюється тим, що вони призначені для одного методу автентифікації: отримати id сесії від куків та перевірити його.

Раніше при налаштуванні проміжного програмного забезпечення `session` ми не встановлювали назву куків для сесії (`key`). Це пояснюється тим, що пакет `session` використовував значення за замовчуванням. Тепер, коли додано інший пакет, який потребує доступу до того самого значення куків, треба чітко встановити значення `key` в обох об’єктах конфігурації.

Не забудьте додати `key` з назвою куків до проміжного програмного забезпечення `session`, яке відповідає ключу Socket.IO. Також додайте посилання `store` до налаштувань, поруч з якими ми встановлюємо `saveUninitialized: true`. Необхідно вказати Socket.IO до якої сесії прив’язуватися.

<hr />

Тепер потрібно визначити функції зворотного виклику `success` та `fail`:

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

Тепер до вашого об’єкта-користувача можна отримати доступ в об’єкті-сокеті як `socket.request.user`. Наприклад, тепер ви можете додати наступне:

```js
console.log('user ' + socket.request.user.username + ' connected');
```

Це введе на консоль сервера тих, хто приєднався!

Відправте свою сторінку коли впевнились, що все правильно. Якщо виникають помилки, ви можете <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#authentication-with-socketio-9" target="_blank" rel="noopener noreferrer nofollow">переглянути проєкт, виконаний до цього етапу</a>.

# --hints--

`passport.socketio` повинен бути залежністю.

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

`cookie-parser` повинен бути залежністю.

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

passportSocketIo повинен бути правильно заданий.

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

passportSocketIo потрібно правильно налаштувати.

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

