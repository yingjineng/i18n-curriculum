---
id: 587d824b367417b2b2512c49
title: Pruebas de veracidad
challengeType: 2
forumTopicId: 301596
dashedName: test-for-truthiness
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`isTrue()` probará el valor booleano `true` y `isNotTrue()` pasará cuando se le dé cualquier cosa que no sea el valor booleano de `true`.

```js
assert.isTrue(true, 'This will pass with the boolean value true');
assert.isTrue('true', 'This will NOT pass with the string value "true"');
assert.isTrue(1, 'This will NOT pass with the number value 1');
```

`isFalse()` y `isNotFalse()` también existen, y se comportan de manera similar a sus contrapartes verdaderas excepto que buscan el valor booleano de `false`.

# --instructions--

Dentro de `tests/1_unit-tests.js` bajo la prueba etiquetada como `#4` en el conjunto de prueba `Basic Assertions`, cambia cada `assert` a `assert.isTrue` o `assert.isNotTrue` para hacer que la prueba pase (debe evaluarse como `true`). No cambies los argumentos pasados a las aserciones.

# --hints--

Se deben pasar todos los tests.

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes elegir el método correcto para la primera afirmación - `isTrue` vs. `isNotTrue`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'isTrue', 'True is true');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes elegir el método correcto para la segunda afirmación: `isTrue` vs. `isNotTrue`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'isTrue',
        'Double negation of a truthy value is true'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes elegir el método correcto para la tercera afirmación: `isTrue` vs. `isNotTrue`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=3').then(
    (data) => {
      assert.equal(
        data.assertions[2].method,
        'isNotTrue',
        'A truthy object is not true - neither is a false one'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

