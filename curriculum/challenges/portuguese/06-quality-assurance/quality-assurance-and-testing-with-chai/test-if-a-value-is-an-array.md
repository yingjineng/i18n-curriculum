---
id: 587d824d367417b2b2512c50
title: Testar se o valor é um array
challengeType: 2
forumTopicId: 301600
dashedName: test-if-a-value-is-an-array
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Em `tests/1_unit-tests.js`, no teste de número `#11`, no grupo de testes `Arrays`, modifique cada `assert` para `assert.isArray` ou para `assert.isNotArray`, de maneira que cada teste passe (seja `true`). Não altere os argumentos passados para as assertivas.

# --hints--

Todos os testes devem passar.

```js
  $.get(code + '/_api/get-tests?type=unit&n=10').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o método correto para a primeira afirmação - `isArray` ou `isNotArray`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=10').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'isArray',
        'String.prototype.split() returns an Array'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o método correto para a segunda afirmação - `isArray` ou `isNotArray`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=10').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'isNotArray',
        'Array.prototype.indexOf() returns a number'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

