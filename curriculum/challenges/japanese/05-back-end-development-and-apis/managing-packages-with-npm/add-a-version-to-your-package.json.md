---
id: 587d7fb4367417b2b2512bff
title: package.json にバージョンを追加する
challengeType: 2
forumTopicId: 301525
dashedName: add-a-version-to-your-package-json
---

# --description--

`version` は、package.json ファイルの必須フィールドの 1 つです。 このフィールドには、プロジェクトの現在のバージョンを記述します。 こちらがその例です。

```json
"version": "1.2.0",
```

# --instructions--

プロジェクトの package.json ファイルに `version` を追加してください。

# --hints--

package.json で、有効な「version」キーを記述する必要があります。

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert(packJson.version, '"version" is missing');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

