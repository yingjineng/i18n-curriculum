---
id: 587d824c367417b2b2512c4c
title: Assegurar a igualdade profunda com .deepEqual e .notDeepEqual
challengeType: 2
forumTopicId: 301587
dashedName: assert-deep-equality-with--deepequal-and--notdeepequal
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`deepEqual()` assegura que dois objetos são profundamente iguais.

# --instructions--

Em `tests/1_unit-tests.js`, no teste de número `#7`, no grupo de testes `Equality`, modifique cada `assert` para `assert.deepEqual` ou para `assert.notDeepEqual`, de maneira que cada teste passe (seja avaliado como `true`). Não altere os argumentos passados às afirmações.

# --hints--

Todos os testes devem passar.

```js
  $.get(code + '/_api/get-tests?type=unit&n=6').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o método correto para a primeira declaração - `deepEqual` ou `notDeepEqual`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=6').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'deepEqual',
        'The order of the keys does not matter'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o método correto para a segunda declaração - `deepEqual` ou `notDeepEqual`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=6').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'notDeepEqual',
        'The position of elements within an array does matter'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

