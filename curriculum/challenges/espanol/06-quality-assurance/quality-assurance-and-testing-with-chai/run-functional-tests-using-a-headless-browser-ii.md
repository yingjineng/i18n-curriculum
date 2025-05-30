---
id: 5f8884f4c46685731aabfc41
title: Ejecuta pruebas funcionales usando un navegador sin interfaz gráfica II
challengeType: 2
forumTopicId: 301594
dashedName: run-functional-tests-using-a-headless-browser-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Dentro `tests/2_functional-tests.js`, en el `'Submit the surname "Vespucci" in the HTML form'` prueba (`// #6`), automatiza lo siguiente:

1.  Rellena el formulario con el apellido `Vespucci`
2.  Presiona el botón enviar

Y dentro del callback de `pressButton`:

1.  Comprueba que el status es OK `200`
2.  Comprueba que el texto dentro del elemento `span#name` es `'Amerigo'`
3.  Comprueba que el texto dentro del elemento `span#surname` es `'Vespucci'`
4.  Comprueba que existen elemento(s) `span#dates` y su contador es `1`

No olvides eliminar la llamada `assert.fail()`.

# --hints--

Se deben pasar todos los tests.

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

Debes asegurarte que la petición del navegador sin interfaz gráfica ha sido exitosa.

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

Debes comprobar que el texto dentro del elemento `span#name` es `'Amerigo'`.

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

Debes comprobar que el texto dentro del elemento `span#surname` es `'Vespucci'`.

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

Debes comprobar que el elemento `span#dates` existe y su contador es 1.

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

