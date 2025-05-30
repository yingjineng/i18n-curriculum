---
id: 58965611f9fc0f352b528e6c
title: Вихід з облікового запису
challengeType: 2
forumTopicId: 301560
dashedName: logging-a-user-out
---

# --description--

Creating the logout logic is easy. The route should just unauthenticate the user, and redirect to the home page instead of rendering any view.

Скасувати автентифікацію користувача через Passport так само легко, як викликати `req.logout()` перед переадресацією. Додайте такий маршрут `/logout`, щоб зробити це:

```js
app.route('/logout')
  .get((req, res) => {
    req.logout();
    res.redirect('/');
});
```

Мабуть, ви помітили, що не обробляєте відсутні вебсторінки (404). Поширеним способом обробки цієї помилки у Node є наступне проміжне програмне забезпечення. Додайте його після всіх інших маршрутів:

```js
app.use((req, res, next) => {
  res.status(404)
    .type('text')
    .send('Not Found');
});
```

Відправте свою сторінку коли впевнились, що все правильно. Якщо виникають помилки, ви можете <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#logging-a-user-out-10" target="_blank" rel="noopener noreferrer nofollow">переглянути проєкт, виконаний до цього етапу</a>.

# --hints--

`req.logout()` потрібно викликати у маршруті `/logout`.

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

`/logout` повинен переадресовувати на головну сторінку.

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

