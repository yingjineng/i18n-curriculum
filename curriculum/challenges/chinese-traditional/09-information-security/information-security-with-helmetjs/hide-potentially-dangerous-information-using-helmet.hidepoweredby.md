---
id: 587d8247367417b2b2512c37
title: 使用 helmet.hidePoweredBy() 隱藏潛在的危險信息
challengeType: 2
forumTopicId: 301580
dashedName: hide-potentially-dangerous-information-using-helmet-hidepoweredby
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

如果黑客發現你的網站是用 Express 搭建的，那麼他們就可以利用 Express 或 Node 現存的漏洞來攻擊你的網站。 `X-Powered-By: Express` 默認在來自 Express 的每個請求中被髮送。 使用 `helmet.hidePoweredBy()` 中間件來移除 X-Powered-By 頭。

# --hints--

應正確地安裝 helmet.hidePoweredBy() 中間件

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'hidePoweredBy');
      assert.notEqual(data.headers['x-powered-by'], 'Express');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

