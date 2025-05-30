---
id: bd7158d8c443edefaeb5bdff
title: Microsserviço conversor de requisição de cabeçalho
challengeType: 4
forumTopicId: 301507
dashedName: request-header-parser-microservice
---

# --description--

Build a full stack JavaScript app that is functionally similar to this: <a href="https://request-header-parser-microservice.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://request-header-parser-microservice.freecodecamp.rocks/</a>. Trabalhar nesse projeto vai fazer com que você escreva o código usando um dos seguintes métodos:

-   Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-headerparser/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
-   Use um criador de sites de sua escolha para completar o projeto. Certifique-se de incorporar todos os arquivos do nosso repositório no GitHub.

# --hints--

You should provide your own project, not the example URL.

```js
  assert(
    !/.*\/request-header-parser-microservice\.freecodecamp\.rocks/.test(
      code
    )
  );
```

A request to `/api/whoami` should return a JSON object with your IP address in the `ipaddress` key.

```js
  $.get(code + '/api/whoami').then(
    (data) => assert(data.ipaddress && data.ipaddress.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

A request to `/api/whoami` should return a JSON object with your preferred language in the `language` key.

```js
  $.get(code + '/api/whoami').then(
    (data) => assert(data.language && data.language.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

A request to `/api/whoami` should return a JSON object with your software in the `software` key.

```js
  $.get(code + '/api/whoami').then(
    (data) => assert(data.software && data.software.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

