---
id: 5895f70df9fc0f352b528e6a
title: 创建新的中间件
challengeType: 2
forumTopicId: 301551
dashedName: create-new-middleware
---

# --description--

As is, any user can just go to `/profile` whether they have authenticated or not by typing in the URL. You want to prevent this by checking if the user is authenticated first before rendering the profile page. This is the perfect example of when to create a middleware.

这里的挑战是创建中间件函数 `ensureAuthenticated(req, res, next)`，它将通过在检查 `req.user` 是否被定义的 `request` 上调用 Passport 的 `isAuthenticated` 方法检查用户是否已认证。 如果是的话，那么 `next()` 应该被调用。 否则，你可以直接用一个重定向到你的主页来回应请求，以便登录。

此中间件的实现是：

```javascript
function ensureAuthenticated(req, res, next) {
  if (req.isAuthenticated()) {
    return next();
  }
  res.redirect('/');
};
```

创建上述中间件函数，然后在 GET 请求参数之前，将 `ensureAuthenticated` 作为中间件传递，以请求个人资料页面。

```javascript
app
 .route('/profile')
 .get(ensureAuthenticated, (req,res) => {
    res.render('profile');
 });
```

完成之后提交你的页面。 如果你在运行时遇到错误，你可以<a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#create-new-middleware-8" target="_blank" rel="noopener noreferrer nofollow">查看到此为止的项目完成情况</a>。

# --hints--

中间件 `ensureAuthenticated` 应该被实现，并附加到 `/profile` 路由。

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

未认证的 GET 请求 `/profile` 应该正确重定向到 `/`。

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

