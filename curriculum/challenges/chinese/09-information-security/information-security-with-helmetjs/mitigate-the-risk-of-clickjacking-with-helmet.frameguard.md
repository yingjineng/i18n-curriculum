---
id: 587d8247367417b2b2512c38
title: 使用 helmet.frameguard() 降低点击劫持的风险
challengeType: 2
forumTopicId: 301582
dashedName: mitigate-the-risk-of-clickjacking-with-helmet-frameguard
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

你的网页可能在未经你同意的情况下被放在 `<frame>` 或 `<iframe>` 中。 这可能会导致点击劫持攻击等情况。 点击劫持是一种欺骗用户的技术，使其与用户认为不同的页面进行互动。 这可以通过使用 iframe 恶意运行你的页面而获得。 在这种情况下，黑客可以在你的页面上设置一个隐藏层。 隐藏的按钮可以被用来运行坏的脚本。 该中间件设置 X-Frame-Options 头。 它限制了谁可以把你的网站放在一个框架里。 它有三种模式：DENY、SAMEORIGIN 和 ALLOW-FROM。

我们不需要让我们的应用程序可以被嵌入。

# --instructions--

使用 `helmet.frameguard()` 时应传递配置对象 `{action: 'deny'}`。

# --hints--

应正确加载 helmet.frameguard() 中间件

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(
        data.appStack,
        'frameguard',
        'helmet.frameguard() middleware is not mounted correctly'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

helmet.frameguard() 'action' 应该设置为 “DENY”

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.property(data.headers, 'x-frame-options');
      assert.equal(data.headers['x-frame-options'], 'DENY');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

