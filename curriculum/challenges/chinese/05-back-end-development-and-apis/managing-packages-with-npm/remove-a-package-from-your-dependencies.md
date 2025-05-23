---
id: 587d7fb5367417b2b2512c04
title: 从依赖项中删除依赖包
challengeType: 2
forumTopicId: 301530
dashedName: remove-a-package-from-your-dependencies
---

# --description--

You have now tested a few ways you can manage dependencies of your project by using the package.json's dependencies section. You have also included external packages by adding them to the file and even told npm what types of versions you want, by using special characters such as the tilde or the caret.

但是，如果想要删除不再需要的依赖包，该怎么办呢？ 可能已经猜到了——只需要从依赖项中删除相应的键值对就行了。

同样的方法也适用于删除 package.json 中的其他字段。

# --instructions--

从依赖项中删除 `@freecodecamp/example` 包。

**注意：**删除依赖包后，确保逗号数量正确。

# --hints--

`"dependencies"` 不应包含 `"@freecodecamp/example"`。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.notProperty(
        packJson.dependencies,
        '@freecodecamp/example',
        '"dependencies" still includes "@freecodecamp/example"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

