---
id: 587d7fb4367417b2b2512bff
title: Додайте версію до package.json
challengeType: 2
forumTopicId: 301525
dashedName: add-a-version-to-your-package-json
---

# --description--

`version` є одним з необхідних полів вашого файлу package.json. Це поле описує поточну версію вашого проєкту. Ось приклад:

```json
"version": "1.2.0",
```

# --instructions--

Додайте `version` до файлу package.json свого проєкту.

# --hints--

package.json повинен мати дійсний ключ «version»

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

