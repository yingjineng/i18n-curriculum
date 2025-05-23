---
id: 587d8250367417b2b2512c5d
title: Ejecuta pruebas funcionales usando un navegador sin interfaz gráfica
challengeType: 2
forumTopicId: 301595
dashedName: run-functional-tests-using-a-headless-browser
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

En la página hay un formulario de entrada. Envía datos al endpoint `PUT /travellers` como una solicitud AJAX.

Cuando la solicitud se completa con éxito, el código del cliente añade un `<div>` que contiene la información en la respuesta al DOM.

Aquí hay un ejemplo de cómo usar Zombie.js para interactuar con el formulario:

```js
test('Submit the surname "Polo" in the HTML form', function (done) {
  browser.fill('surname', 'Polo').then(() => {
    browser.pressButton('submit', () => {
      browser.assert.success();
      browser.assert.text('span#name', 'Marco');
      browser.assert.text('span#surname', 'Polo');
      browser.assert.elements('span#dates', 1);
      done();
    });
  });
});
```

Primero, el método `fill` del objeto `browser` rellena el campo `surname` del formulario con el valor `'Polo'`. `fill` devuelve una promesa, así que `then` está encadenado a ella.

Dentro del callback `then` el método `pressButton` del objeto `browser` se utiliza para invocar el `submit` del event listener. El método `pressButton` es asíncrono.

Luego, una vez que se recibe una respuesta de la solicitud AJAX, se hacen algunas afirmaciones comprobando que:

1.  El estado de la respuesta es `200`
2.  The text within the `<span id='name'></span>` element matches `'Marco'`
3.  The text within the `<span id='surname'></span>` element matches `'Polo'`
4.  There is `1` `<span id='dates'></span>` element.

Finalmente, se invoca el callback `done`, que es necesario debido a la prueba asincrónica.

# --instructions--

Dentro de `tests/2_functional-tests.js`, en `'Submit the surname "Colombo" in the HTML form'` (`// #5`), automatiza lo siguiente:

1.  Rellena el formulario con el apellido `Colombo`
2.  Presione el botón Enviar

Y dentro del callback de `pressButton`:

1.  Comprueba que el status es OK `200`
2.  Compruebe que el texto dentro del elemento `span#name` es `'Cristoforo'`
3.  Compruebe que el texto dentro del elemento `span#surname` es `'Colombo'`
4.  Compruebe que existen elemento(s) `span#dates` y su contador es `1`

No olvide eliminar la llamada `assert.fail()`.

# --hints--

Todas las pruebas deben pasar.

```js
  $.get(code + '/_api/get-tests?type=functional&n=5').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debe asegurarse que la petición del navegador sin interfaz gráfica ha sido exitosa.

```js
  $.get(code + '/_api/get-tests?type=functional&n=5').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'browser.success');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debe comprobar que el texto dentro del elemento `span#name` es `'Cristoforo'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=5').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'browser.text');
      assert.match(data.assertions[1].args[0], /('|")span#name\1/);
      assert.match(data.assertions[1].args[1], /('|")Cristoforo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes comprobar que el texto dentro del elemento `span#surname` es `'Colombo'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=5').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'browser.text');
      assert.match(data.assertions[2].args[0], /('|")span#surname\1/);
      assert.match(data.assertions[2].args[1], /('|")Colombo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debe comprobar que el elemento `span#dates` existe y su contador es 1.

```js
  $.get(code + '/_api/get-tests?type=functional&n=5').then(
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

