---
id: 587d8249367417b2b2512c3e
title: 使用 helment.noCache() 禁用客户端缓存
challengeType: 2
forumTopicId: 301576
dashedName: disable-client-side-caching-with-helmet-nocache
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

如果你正在为你的网站发布更新，而你希望用户总是下载较新的版本，你可以（尝试）在客户的浏览器上禁用缓存。 它在开发中也很有用。 缓存具有性能优势，你将失去这些优势，因此只有在真正需要时才使用此选项。

# --instructions--

在你的服务器上使用 `helmet.noCache()` 方法。

# --hints--

应正确加载 helmet.noCache() 中间件

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'nocache');
      assert.equal(
        data.headers['cache-control'],
        'no-store, no-cache, must-revalidate, proxy-revalidate'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

