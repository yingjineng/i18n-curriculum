---
id: 587d7fb5367417b2b2512c01
title: 通過語義化版本來管理 npm 依賴關係
challengeType: 2
forumTopicId: 301529
dashedName: manage-npm-dependencies-by-understanding-semantic-versioning
---

# --description--

`Versions` of the npm packages in the dependencies section of your package.json file follow what’s called Semantic Versioning (SemVer), an industry standard for software versioning aiming to make it easier to manage dependencies. Libraries, frameworks or other tools published on npm should use SemVer in order to clearly communicate what kind of changes projects can expect if they update.

在使用外部依賴項（大多數情況都是這樣）進行軟件開發時，瞭解語義化版本會很有用。 這些數字保存着項目的偶然發生的破壞性改變，不會讓人對項目昨天還正常，今天卻無法運行而百思不解。 根據官網，這是語義化版本的工作方式：

```json
"package": "MAJOR.MINOR.PATCH"
```

當做了不兼容的 API 修改，應該增加主版本號（MAJOR）； 當新增了向下兼容的新功能時，應該增加次版本號（MINOR）； 當修復了向下兼容的 bug 時，應該增加修訂號（PATCH）。 這意味着修訂號是用來修復錯誤的，次版本號則是添加了新功能，但它們都沒有破壞之前的功能。 主版本號（MAJOR）是添加了不兼容早期版本的更改。

# --instructions--

在 `package.json` 文件的依賴項部分，更改 `@freecodecamp/example` 的版本以匹配 MAJOR 版本爲 1、MINOR 版本爲 2 和 PATCH 版本爲 13

# --hints--

`"dependencies"` 應包括 `"@freecodecamp/example"`。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.property(
        packJson.dependencies,
        '@freecodecamp/example',
        '"dependencies" does not include "@freecodecamp/example"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`"@freecodecamp/example"` 版本應爲 `"1.2.13"`。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.equal(
        packJson.dependencies["@freecodecamp/example"],
        '1.2.13',
        'Wrong version of "@freecodecamp/example". It should be 1.2.13'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

