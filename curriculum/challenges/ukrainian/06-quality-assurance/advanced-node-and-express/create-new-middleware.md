---
id: 5895f70df9fc0f352b528e6a
title: Створення нового проміжного ПЗ
challengeType: 2
forumTopicId: 301551
dashedName: create-new-middleware
---

# --description--

As is, any user can just go to `/profile` whether they have authenticated or not by typing in the URL. You want to prevent this by checking if the user is authenticated first before rendering the profile page. This is the perfect example of when to create a middleware.

Це завдання створює функцію проміжного ПЗ `ensureAuthenticated(req, res, next)`, яка перевірятиме, чи користувач автентифікувався, викликавши метод Passport `isAuthenticated` до `request`, який перевіряє, чи `req.user` визначений. Якщо так, то треба викликати `next()`. В іншому випадку ви можете просто відповісти на запит, перенаправивши на свою домашню сторінку для входу.

Впровадження цього проміжного ПЗ:

```javascript
function ensureAuthenticated(req, res, next) {
  if (req.isAuthenticated()) {
    return next();
  }
  res.redirect('/');
};
```

Створіть наведену вище функцію проміжного ПЗ, а потім передайте `ensureAuthenticated` як проміжне ПЗ до запитів сторінки профілю перед аргументом запиту GET:

```javascript
app
 .route('/profile')
 .get(ensureAuthenticated, (req,res) => {
    res.render('profile');
 });
```

Відправте свою сторінку коли впевнились, що все правильно. Якщо виникають помилки, ви можете <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#create-new-middleware-8" target="_blank" rel="noopener noreferrer nofollow">переглянути проєкт, виконаний до цього етапу</a>.

# --hints--

Проміжне програмне забезпечення `ensureAuthenticated` повинне бути реалізоване та приєднане до маршруту `/profile`.

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

Неавтентифікований запит GET до `/profile` повинен правильно перенаправляти до `/`.

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

