---
id: 587d7fb4367417b2b2512bfe
title: 给 package.json 添加许可证
challengeType: 2
forumTopicId: 301523
dashedName: add-a-license-to-your-package-json
---

# --description--

The `license` field is where you inform users of what they are allowed to do with your project.

开源项目常见的协议有 MIT 和 BSD 等。 许可证信息并不是必须的。 大多数国家的版权法会默认让你拥有自己创作的作品的所有权。 但是，明确说明用户可以做什么和不能做什么会是一个很好的做法。 这里有一个 license 字段的例子：

```json
"license": "MIT",
```

# --instructions--

在项目的 package.json 文件中补充合适的 `license` 字段。

# --hints--

package.json 应该包含一个有效的“license”键

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

