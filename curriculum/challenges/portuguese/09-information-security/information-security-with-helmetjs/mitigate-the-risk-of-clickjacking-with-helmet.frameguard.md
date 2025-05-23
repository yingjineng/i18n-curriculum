---
id: 587d8247367417b2b2512c38
title: Reduzir o risco de clickjacking com o helmet.frameguard()
challengeType: 2
forumTopicId: 301582
dashedName: mitigate-the-risk-of-clickjacking-with-helmet-frameguard
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Sua página pode ser colocada em um `<frame>` ou `<iframe>` sem o seu consentimento. Isso pode resultar em ataques de clickjacking, entre outras coisas. Clickjacking é uma técnica de enganar um usuário para que ele interaja com uma página diferente da que o usuário pensa que é. Isso pode ser feito ao executar sua página em um contexto malicioso, por meio de iframing. Nesse contexto, um hacker pode colocar uma camada oculta sobre sua página. Botões ocultos podem ser usados para executar scripts maliciosos. Este middleware define o cabeçalho X-Frame-Options. Ele restringe quem pode colocar seu site em um frame. Ele tem três modos: DENY, SAMEORIGIN, e ALLOW-FROM.

Não precisamos que nosso aplicativo seja posto em um frame.

# --instructions--

Use `helmet.frameguard()` passando o objeto de configuração `{action: 'deny'}`.

# --hints--

O middleware helmet.frameguard() deve ser montado corretamente

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(
        data.appStack,
        'frameguard',
        'helmet.frameguard() middleware is not mounted correctly'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

A 'action' do helmet.frameguard() deve ser definida como 'DENY'

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.property(data.headers, 'x-frame-options');
      assert.equal(data.headers['x-frame-options'], 'DENY');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

