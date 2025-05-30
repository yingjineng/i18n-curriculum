---
id: 587d7fb4367417b2b2512bfd
title: package.json にキーワードを追加する
challengeType: 2
forumTopicId: 301526
dashedName: add-keywords-to-your-package-json
---

# --description--

`keywords` フィールドでは、関連するキーワードを使用してプロジェクトを記述できます。 こちらがその例です。

```json
"keywords": [ "descriptive", "related", "words" ],
```

ご覧のとおり、このフィールドは二重引用符で囲まれた文字列の配列として構成されています。

# --instructions--

プロジェクトの package.json ファイルの `keywords` フィールドに、適切な文字列の配列を追加してください。

キーワードの 1 つを「freecodecamp」にする必要があります。

# --hints--

package.json で、有効な 「keywords」キーを記述する必要があります。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert(packJson.keywords, '"keywords" is missing');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

「keywords」フィールドは、配列である必要があります。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.isArray(packJson.keywords, '"keywords" is not an array');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

「keywords」に「freecodecamp」を含める必要があります。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.include(
        packJson.keywords,
        'freecodecamp',
        '"keywords" does not include "freecodecamp"'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

