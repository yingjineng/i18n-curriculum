---
id: 587d8247367417b2b2512c37
title: Esconder informações potencialmente perigosas usando o helmet.hidePoweredBy()
challengeType: 2
forumTopicId: 301580
dashedName: hide-potentially-dangerous-information-using-helmet-hidepoweredby
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Os hackers podem explorar vulnerabilidades conhecidas no Express/Node se verem que seu site usa o Express. `X-Powered-By: Express` é enviado em todas as solicitações vindas do Express por padrão. Use o middleware `helmet.hidePoweredBy()` para remover o cabeçalho X-Powered-By.

# --hints--

O middleware helmet.hidePoweredBy() deve ser montado corretamente

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'hidePoweredBy');
      assert.notEqual(data.headers['x-powered-by'], 'Express');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

