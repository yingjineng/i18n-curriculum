---
id: 587d7fb4367417b2b2512bfe
title: Adicionar uma licença ao package.json
challengeType: 2
forumTopicId: 301523
dashedName: add-a-license-to-your-package-json
---

# --description--

The `license` field is where you inform users of what they are allowed to do with your project.

Algumas licenças comuns para projetos de código aberto incluem a MIT e a BSD. Informações de licença não são necessárias. As leis de direitos autorais na maioria dos países lhe darão a propriedade do que você criou por padrão. No entanto, é sempre uma boa prática indicar explicitamente o que os usuários podem e não podem fazer. Aqui está um exemplo do campo license:

```json
"license": "MIT",
```

# --instructions--

Preencha o campo `license` no arquivo package.json do seu projeto conforme achar adequado.

# --hints--

O package.json deve ter uma chave "license" válida

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

