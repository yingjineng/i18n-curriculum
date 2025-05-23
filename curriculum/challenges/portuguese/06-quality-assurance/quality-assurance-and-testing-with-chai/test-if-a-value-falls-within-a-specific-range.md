---
id: 587d824c367417b2b2512c4f
title: Testar se um valor está dentro de um intervalo específico
challengeType: 2
forumTopicId: 301598
dashedName: test-if-a-value-falls-within-a-specific-range
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

```javascript
.approximately(actual, expected, delta, [message])
```

Afirma que o `actual` é igual a `expected`, para dentro de um intervalo de +/- `delta`.

# --instructions--

Em `tests/1_unit-tests.js`, no teste de número `#10`, no grupo de testes `Comparisons`, modifique cada `assert` para `assert.approximately`, de maneira que cada teste passe (seja avaliado como `true`).

Escolha o intervalo mínimo (terceiro parâmetro) para fazer com que o teste sempre passe. Deve ser inferior a 1.

# --hints--

Todos os testes devem passar.

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o intervalo correto para a primeira afirmação - `approximately(actual, expected, range)`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'approximately');
      assert.equal(
        data.assertions[0].args[2],
        0.5,
        "weirdNumbers(0.5) is in the range (0.5, 1.5]. It's within 1 +/- 0.5"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve escolher o intervalo correto para a segunda afirmação - `approximately(actual, expected, range)`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'approximately');
      assert.equal(
        data.assertions[1].args[2],
        0.8,
        "weirdNumbers(0.2) is in the range (0.2, 1.2]. It's within 1 +/- 0.8"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

