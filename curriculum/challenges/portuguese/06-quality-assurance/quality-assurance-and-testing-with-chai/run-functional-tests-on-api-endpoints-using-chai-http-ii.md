---
id: 587d824f367417b2b2512c59
title: Executar testes funcionais no endpoint da API usando Chai-HTTP II
challengeType: 2
forumTopicId: 301592
dashedName: run-functional-tests-on-api-endpoints-using-chai-http-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Dentro de `tests/2_functional-tests.js`, altere o teste `'Test GET /hello with your name'` (`// #2`) para afirmar o `status` e o `text` da resposta para fazer o teste passar.

Envie seu nome como consulta do URL, acrescentando `?name=<your_name>` à rota. O endpoint responde com `'hello <your_name>'`.

# --hints--

Todos os testes devem passar

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve testar que `res.status` == 200

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'equal');
      assert.equal(data.assertions[0].args[0], 'res.status');
      assert.equal(data.assertions[0].args[1], '200');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve testar se `res.text` == `'hello <your_name>'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /hello [\w\d_-]/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

