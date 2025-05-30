---
id: 587d824e367417b2b2512c58
title: Executar testes funcionais no endpoint da API usando Chai-HTTP
challengeType: 2
forumTopicId: 301593
dashedName: run-functional-tests-on-api-endpoints-using-chai-http
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

O Mocha permite que você teste operações assíncronas, como chamadas para endpoints de API, com um plugin chamado `chai-http`.

A seguir, vemos um exemplo de um teste usando `chai-http` para a suite chamada `'GET /hello?name=[name] => "hello [name]"'`:

```js
suite('GET /hello?name=[name] => "hello [name]"', function () {
  test('?name=John', function (done) {
    chai
      .request(server)
      .keepOpen()
      .get('/hello?name=John')
      .end(function (err, res) {
        assert.equal(res.status, 200, 'Response status should be 200');
        assert.equal(res.text, 'hello John', 'Response should be "hello John"');
        done();
      });
  });
});
```

O teste envia uma solicitação de `GET` para o servidor com um nome (name) como a string de consulta do URL (`?name=John`). Na função de callback do método `end`, o objeto de resposta (`res`) é recebido e contém a propriedade `status`.

O primeiro `assert.equal` verifica se o status é igual a `200`. O segundo `assert.equal` verifica se a string de resposta (`res.text`) é igual a `"hello John"`.

Além disso, observe o parâmetro `done` na função de callback do teste. Chamá-la sem um argumento no final de um teste é necessário para sinalizar que a operação assíncrona está completa.

Finalmente, observe o método `keepOpen` logo após o método `request`. Normalmente, você executaria os testes pela linha de comando ou como parte de um processo de integração automatizada. Além disso, você poderia deixar `chai-http` iniciar e parar seu servidor automaticamente.

No entanto, os testes que são executados quando você envia o link para o seu projeto exigem que seu servidor esteja pronto. Então, você precisa usar o método `keepOpen` para impedir que `chai-http` pare seu servidor.

# --instructions--

Dentro de `tests/2_functional-tests.js`, altere o teste `'Test GET /hello with no name'` (`// #1`) para afirmar o `status` e o `text` da resposta para fazer o teste passar. Não altere os argumentos passados às afirmações.

Não deve haver consulta de URL. Não deve haver consulta de name no URL. O endpoint responde com `hello Guest`.

# --hints--

Todos os testes devem passar

```js
  $.get(code + '/_api/get-tests?type=functional&n=0').then(
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
  $.get(code + '/_api/get-tests?type=functional&n=0').then(
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

Você deve testar se `res.text` == `'hello Guest'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=0').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /('|")hello Guest\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

