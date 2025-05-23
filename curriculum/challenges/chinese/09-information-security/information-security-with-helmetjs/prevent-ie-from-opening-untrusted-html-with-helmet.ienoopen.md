---
id: 587d8248367417b2b2512c3b
title: 使用 helment.ieNoOpen() 防止 IE 打开不受信任的 HTML
challengeType: 2
forumTopicId: 301584
dashedName: prevent-ie-from-opening-untrusted-html-with-helmet-ienoopen
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

有些网站会下载不安全的 HTML 文件。 某些版本的 IE 默认情况下还会在你网站的作用域下打开这些 HTML 文件。 换句话说，这些不安全的 HTML 页面可以在你的网站做恶意行为。 我们可以通过中间件来设置 header 中的 X-Download-Options 字段，让它的值为 noopen。 This will prevent IE users from executing downloads in the trusted site's context.

# --instructions--

应正确加载 `helmet.ieNoOpen()` 中间件

# --hints--

helmet.ieNoOpen() 中间件应正确安装。

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'ienoopen');
      assert.equal(data.headers['x-download-options'], 'noopen');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

