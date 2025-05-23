---
id: 587d7fb4367417b2b2512bfe
title: 給 package.json 添加許可證
challengeType: 2
forumTopicId: 301523
dashedName: add-a-license-to-your-package-json
---

# --description--

The `license` field is where you inform users of what they are allowed to do with your project.

開源項目常見的協議有 MIT 和 BSD 等。 許可證信息並不是必須的。 大多數國家的版權法會默認讓你擁有自己創作的作品的所有權。 但是，明確說明用戶可以做什麼和不能做什麼會是一個很好的做法。 這裏有一個 license 字段的例子：

```json
"license": "MIT",
```

# --instructions--

在項目的 package.json 文件中補充合適的 `license` 字段。

# --hints--

package.json 應該包含一個有效的“license”鍵

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert(packJson.license, '"license" is missing');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

