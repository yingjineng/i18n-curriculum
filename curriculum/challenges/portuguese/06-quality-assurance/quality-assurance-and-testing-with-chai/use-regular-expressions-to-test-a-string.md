---
id: 587d824d367417b2b2512c54
title: Usar expressões regulares para testar uma string
challengeType: 2
forumTopicId: 301608
dashedName: use-regular-expressions-to-test-a-string
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`match()` afirma que o valor real corresponde à expressão regular do segundo argumento.

# --instructions--

Em `tests/1_unit-tests.js`, no teste de número `#15`, no grupo de testes `Strings`, modifique cada `assert` para `assert.match` ou para `assert.notMatch`, de maneira que cada teste passe (seja `true`). Não altere os argumentos passados às afirmações.

# --hints--

Todos os testes devem passar.

```js
  $.get(code + '/_api/get-tests?type=unit&n=14').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o método correto para a primeira afirmação - `match` ou `notMatch`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=14').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'match',
        "'# name:John Doe, age:35' matches the regex"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o método correto para a segunda afirmação - `match` ou `notMatch`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=14').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'notMatch',
        "'# name:Paul Smith III, age:twenty-four' does not match the regex (the age must be numeric)"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

