---
id: 5f8884f4c46685731aabfc41
title: Executar testes funcionais usando um navegador headless II
challengeType: 2
forumTopicId: 301594
dashedName: run-functional-tests-using-a-headless-browser-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Em `tests/2_functional-tests.js`, no teste `'Submit the surname "Vespucci" in the HTML form'` (`// #6`), automatize o seguinte:

1.  Fill in the form with the surname `Vespucci`
2.  Press the submit button

Na callback `pressButton`:

1.  Assert that status is OK `200`
2.  Avalie se o texto dentro do elemento `span#name` é `'Amerigo'`
3.  Avalie se o texto dentro do elemento `span#surname` é `'Vespucci'`
4.  Avalie se o(s) elemento(s) `span#dates` existe(m) e sua contagem é `1`

Não se esqueça de remover a chamada `assert.fail()`.

# --hints--

Todos os testes devem passar.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve avaliar se a solicitação do navegador headless foi bem-sucedida.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'browser.success');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve avaliar se o texto dentro do elemento `span#name` é `'Amerigo'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'browser.text');
      assert.match(data.assertions[1].args[0], /('|")span#name\1/);
      assert.match(data.assertions[1].args[1], /('|")Amerigo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve avaliar se o texto dentro do elemento `span#surname` é `'Vespucci'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'browser.text');
      assert.match(data.assertions[2].args[0], /('|")span#surname\1/);
      assert.match(data.assertions[2].args[1], /('|")Vespucci\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Você deve avaliar se o elemento `span#dates` existe e que sua contagem é 1.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'browser.elements');
      assert.match(data.assertions[3].args[0], /('|")span#dates\1/);
      assert.equal(data.assertions[3].args[1], 1);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

