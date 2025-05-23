---
id: 587d824f367417b2b2512c5b
title: Ejecutar pruebas funcionales en la respuesta de un API usando Chai-HTTP IV - método PUT
challengeType: 2
forumTopicId: 301591
dashedName: run-functional-tests-on-an-api-response-using-chai-http-iv---put-method
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Este ejercicio es similar al anterior.

Ahora que sabes cómo comprobar una petición `PUT`, es tu turno de hacerlo desde cero.

# --instructions--

Dentro de `tests/2_functional-tests.js`, modifica la prueba `'Send {surname: "da Verrazzano"}'` (`// #4`), usa los métodos `put` y `send` para probar el endpoint `'/travellers'`.

Envia el siguiente objeto JSON con tu solicitud PUT:

```json
{
  "surname": "da Verrazzano"
}
```

Compruebe lo siguiente dentro del callback `request.end`:

1.  The `status` should be `200`
2.  El `type` debe ser `application/json`
3.  El `body.name` debe ser `Giovanni`
4.  El `body.surname` debe ser `da Verrazzano`

Sigue el orden de las aserciones de arriba - nos basamos en esto. Además, asegúrese de eliminar `assert.fail()` una vez completado.

# --hints--

Todas las pruebas deben pasar

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes comprobar que `res.status` sea 200

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
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

Debes comprobar que `res.type` sea `'application/json'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.type');
      assert.match(data.assertions[1].args[1], /('|")application\/json\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes comprobar que `res.body.name` sea `'Giovanni'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'equal');
      assert.equal(data.assertions[2].args[0], 'res.body.name');
      assert.match(data.assertions[2].args[1], /('|")Giovanni\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Debes comprobar que `res.body.surname` sea `'da Verrazzano'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'equal');
      assert.equal(data.assertions[3].args[0], 'res.body.surname');
      assert.match(data.assertions[3].args[1], /('|")da Verrazzano\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

