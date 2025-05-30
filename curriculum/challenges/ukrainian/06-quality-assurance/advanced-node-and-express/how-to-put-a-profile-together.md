---
id: 5895f70ef9fc0f352b528e6b
title: Як налаштувати профіль
challengeType: 2
forumTopicId: 301554
dashedName: how-to-put-a-profile-together
---

# --description--

Now that you can ensure the user accessing the `/profile` is authenticated, you can use the information contained in `req.user` on your page.

Передайте об’єкт, який містить властивість `username` та значення `req.user.username` як другий аргумент для методу `render` показу профілю.

Потім перейдіть до перегляду свого `profile.pug` і додайте наступний рядок під наявним елементом `h1`, дотримуючись тих самих відступів:

```pug
h2.center#welcome Welcome, #{username}!
```

Це створить елемент `h2` з класом `center` та id `welcome`, що міститиме текст `Welcome,` та ім’я користувача.

Крім того, в `profile.pug` додайте посилання на маршрут `/logout`, який міститиме логіку для скасування автентифікації користувача:

```pug
a(href='/logout') Logout
```

Відправте свою сторінку коли впевнились, що все правильно. Якщо виникають помилки, ви можете <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#how-to-put-a-profile-together-9" target="_blank" rel="noopener noreferrer nofollow">переглянути проєкт, виконаний до цього етапу</a>.

# --hints--

Ви повинні правильно додати змінну Pug до `/profile`.

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

