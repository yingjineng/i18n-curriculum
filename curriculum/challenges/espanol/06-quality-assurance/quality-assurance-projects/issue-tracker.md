---
id: 587d8249367417b2b2512c42
title: Seguidor de incidentes
challengeType: 4
forumTopicId: 301569
dashedName: issue-tracker
---

# --description--

Construye una aplicación full stack de JavaScript que sea funcionalmente similar a esta: <a href="https://issue-tracker.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://issue-tracker.freecodecamp.rocks/</a>. Trabajar en este proyecto implicará escribir tu código utilizando uno de los siguientes métodos:

-   Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-issuetracker/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
-   Usa un constructor de sitios de tu elección para completar el proyecto. Asegúrate de incorporar todos los archivos de nuestro repositorio de GitHub.

# --instructions--

-   Complete las rutas necesarias en `/routes/api.js`
-   Crea todas las siguientes pruebas funcionales en `tests/2_functional-tests.js`
-   Copie el archivo `sample.env` a `.env` y establezca las variables apropiadamente
-   Para ejecutar las pruebas automáticamente, añade `NODE_ENV=test` en tu archivo `.env`
-   Para ejecutar las pruebas en la consola, use el comando `npm run test`

Escribir las siguientes pruebas en `tests/2_functional-tests.js`:

-   Crea un problema con cada campo: solicitud POST a `/api/issues/{project}`
-   Crear un problema con sólo los campos requeridos: solicitud POST a `/api/issues/{project}`
-   Crear un problema con los campos requeridos faltantes: solicitud POST a `/api/issues/{project}`
-   Ver problemas en un proyecto: Solicitud GET a `/api/issues/{project}`
-   Ver problemas en un proyecto con un filtro: Solicitud GET a `/api/issues/{project}`
-   Ver problemas en un proyecto con múltiples filtros: Solicitud GET a `/api/issues/{project}`
-   Actualizar un campo en un problema: Solicitud PUT a `/api/issues/{project}`
-   Actualizar varios campos en un problema: Solicitud PUT a `/api/issues/{project}`
-   Actualizar un problema con `_id`faltante: solicitud PUT a `/api/issues/{project}`
-   Actualizar un problema sin campos para actualizar: solicitud PUT a `/api/issues/{project}`
-   Actualizar un problema con un `_id` inválido: Solicitud PUT a `/api/issues/{project}`
-   Eliminar un problema: solicitud DELETE a `/api/issues/{project}`
-   Eliminar un problema con un `_id` inválido: solicitud DELETE a `/api/issues/{project}`
-   Eliminar un problema con `_id` faltante: solicitud DELETE a `/api/issues/{project}`

# --hints--

Debes proporcionar tu propio proyecto, no la URL de ejemplo.

```js
  assert(!/.*\/issue-tracker\.freecodecamp\.rocks/.test(code));
```

You can send a `POST` request to `/api/issues/{projectname}` with form data containing the required fields `issue_title`, `issue_text`, `created_by`, and optionally `assigned_to` and `status_text`.

```js
async () => {
  try {
    let test_data = {
      issue_title: 'Faux Issue Title',
      issue_text: 'Functional Test - Required Fields Only',
      created_by: 'fCC'
    };
    const data = await $.post(
      code + '/api/issues/fcc-project',
      test_data
    );
    assert.isObject(data);
    assert.nestedInclude(data, test_data);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

La solicitud `POST` a `/api/issues/{projectname}` devolverá el objeto creado, y debe incluir todos los campos envíados. Los campos excluídos opcionales serán devueltos como cadenas vacías. Adicionalmente, incluye `created_on` (fecha/hora), `updated_on` (fecha/hora), `open` (booleano, `true` par abrir - valor, predeterminado `false` para cerrar), y `_id`.

```js
async () => {
  try {
    let test_data = {
      issue_title: 'Faux Issue Title 2',
      issue_text: 'Functional Test - Every field filled in',
      created_by: 'fCC',
      assigned_to: 'Chai and Mocha'
    };
    const data = await $.post(
      code + '/api/issues/fcc-project',
      test_data
    );
    assert.isObject(data);
    assert.nestedInclude(data, test_data);
    assert.property(data, 'created_on');
    assert.isNumber(Date.parse(data.created_on));
    assert.property(data, 'updated_on');
    assert.isNumber(Date.parse(data.updated_on));
    assert.property(data, 'open');
    assert.isBoolean(data.open);
    assert.isTrue(data.open);
    assert.property(data, '_id');
    assert.isNotEmpty(data._id);
    assert.property(data, 'status_text');
    assert.isEmpty(data.status_text);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Si tu envías una solicitud `POST` a `/api/issues/{projectname}` sin los campos requeridos, será devuelto el error `{ error: 'required field(s) missing' }`

```js
async () => {
  try {
    let test_data = { created_by: 'fCC' };
    const data = await $.post(code + '/api/issues/fcc-project', {
      created_by: 'fCC'
    });
    assert.isObject(data);
    assert.property(data, 'error');
    assert.equal(data.error, 'required field(s) missing');
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Puedes enviar una solicitud `GET` a `/api/issues/{projectname}` para un arreglo de todos los problemas para ese específico `projectname`, con todos los campos presentes para cada problema.

```js
async () => {
  try {
    let test_data = { issue_text: 'Get Issues Test', created_by: 'fCC' };
    const url =
      code +
      '/api/issues/get_issues_test_' +
      Date.now().toString().substring(7);
    const data1 = await $.post(
      url,
      Object.assign(test_data, { issue_title: 'Faux Issue 1' })
    );
    assert.isObject(data1);
    const data2 = await $.post(
      url,
      Object.assign(test_data, { issue_title: 'Faux Issue 2' })
    );
    assert.isObject(data2);
    const data3 = await $.post(
      url,
      Object.assign(test_data, { issue_title: 'Faux Issue 3' })
    );
    assert.isObject(data3);
    const getIssues = await $.get(url);
    assert.isArray(getIssues);
    assert.lengthOf(getIssues, 3);
    let re = new RegExp('Faux Issue \\d');
    getIssues.forEach((issue) => {
      assert.property(issue, 'issue_title');
      assert.match(issue.issue_title, re);
      assert.property(issue, 'issue_text');
      assert.property(issue, 'created_by');
      assert.property(issue, 'assigned_to');
      assert.property(issue, 'status_text');
      assert.property(issue, 'open');
      assert.property(issue, 'created_on');
      assert.property(issue, 'updated_on');
      assert.property(issue, '_id');
    });
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Puedes enviar una solicitud `GET` a `/api/issues/{projectname}` y filtrar la solicitud para también pasar a lo largo de cualquier cambio y valor como una consulta URL (p. ej. `/api/issues/{project}?open=false`). Puedes pasar uno o más pares campos/valor a la vez.

```js
async () => {
  try {
    let test_data = {
      issue_title: 'To be Filtered',
      issue_text: 'Filter Issues Test'
    };
    const url =
      code +
      '/api/issues/get_issues_test_' +
      Date.now().toString().substring(7);
    const data1 = await $.post(
      url,
      Object.assign(test_data, { created_by: 'Alice', assigned_to: 'Bob' })
    );
    const data2 = await $.post(
      url,
      Object.assign(test_data, { created_by: 'Alice', assigned_to: 'Bob' })
    );
    const data3 = await $.post(
      url,
      Object.assign(test_data, { created_by: 'Alice', assigned_to: 'Eric' })
    );
    const data4 = await $.post(
      url,
      Object.assign(test_data, { created_by: 'Carol', assigned_to: 'Eric' })
    );
    const getSingle = await $.get(url + '?created_by=Alice');
    assert.isArray(getSingle);
    assert.lengthOf(getSingle, 3);
    const getMultiple = await $.get(url + '?created_by=Alice&assigned_to=Bob');
    assert.isArray(getMultiple);
    assert.lengthOf(getMultiple, 2);
    const copyId = getMultiple[0]._id;
    const getById = await $.get(url + `?_id=${copyId}`);
    assert.isArray(getById);
    assert.lengthOf(getById, 1);
    assert.equal(getById[0]._id, copyId, 'should be able to query a document by _id')
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Puedes enviar una solicitud `PUT` a `/api/issues/{projectname}` con un `_id` y uno o más campos para actualizar. En caso de éxito, el campo `updated_on` debería ser actualizado, y debería ser devuelto `{  result: 'successfully updated', '_id': _id }`.

```js
async () => {
  try {
    let initialData = {
      issue_title: 'Issue to be Updated',
      issue_text: 'Functional Test - Put target',
      created_by: 'fCC'
    };
    const url = code + '/api/issues/fcc-project';
    const itemToUpdate = await $.post(url, initialData);
    const updateSuccess = await $.ajax({
      url: url,
      type: 'PUT',
      data: { _id: itemToUpdate._id, issue_text: 'New Issue Text' }
    });
    assert.isObject(updateSuccess);
    assert.deepEqual(updateSuccess, {
      result: 'successfully updated',
      _id: itemToUpdate._id
    });
    const getUpdatedId = await $.get(url + '?_id=' + itemToUpdate._id);
    assert.isArray(getUpdatedId);
    assert.isObject(getUpdatedId[0]);
    assert.isAbove(
      Date.parse(getUpdatedId[0].updated_on),
      Date.parse(getUpdatedId[0].created_on)
    );
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Cuando la solicitud `PUT` enviada a `/api/issues/{projectname}` no incluye un `_id`, el valor devuelto es `{ error: 'missing _id' }`.

```js
async () => {
  try {
    const url = code + '/api/issues/fcc-project';
    const badUpdate = await $.ajax({ url: url, type: 'PUT' });
    assert.isObject(badUpdate);
    assert.property(badUpdate, 'error');
    assert.equal(badUpdate.error, 'missing _id');
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Cuando la petición `PUT` enviada a `/api/issues/{projectname}` no incluye campos actualizados, el valor devuelto es `{ error: 'no update field(s) sent', '_id': _id }`. En cualquier otro error, el valor devuelto es `{ error: 'could not update', '_id': _id }`.

```js
async () => {
  try {
    const url = code + '/api/issues/fcc-project';
    const badUpdate = await $.ajax({
      url: url,
      type: 'PUT',
      data: { _id: '5f665eb46e296f6b9b6a504d' }
    });
    assert.deepEqual(badUpdate, {
      error: 'no update field(s) sent',
      _id: '5f665eb46e296f6b9b6a504d'
    });
    const badIdUpdate = await $.ajax({
      url: url,
      type: 'PUT',
      data: { _id: '5f665eb46e296f6b9b6a504d', issue_text: 'New Issue Text' }
    });
    assert.deepEqual(badIdUpdate, {
      error: 'could not update',
      _id: '5f665eb46e296f6b9b6a504d'
    });
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Puedes enviar una solicitud `DELETE` a `/api/issues/{projectname}` con un `_id` para borrar un problema. Si `_id` no fue enviado, el valor devuelto es `{ error: 'missing _id' }`. En caso de éxito, el valor devuelto es `{ result: 'successfully deleted', '_id': _id }`. En caso de fallo, el valor devuelto es `{ error: 'could not delete', '_id': _id }`.

```js
async () => {
  try {
    let initialData = {
      issue_title: 'Issue to be Deleted',
      issue_text: 'Functional Test - Delete target',
      created_by: 'fCC'
    };
    const url = code + '/api/issues/fcc-project';
    const itemToDelete = await $.post(url, initialData);
    assert.isObject(itemToDelete);
    const deleteSuccess = await $.ajax({
      url: url,
      type: 'DELETE',
      data: { _id: itemToDelete._id }
    });
    assert.isObject(deleteSuccess);
    assert.deepEqual(deleteSuccess, {
      result: 'successfully deleted',
      _id: itemToDelete._id
    });
    const noId = await $.ajax({ url: url, type: 'DELETE' });
    assert.isObject(noId);
    assert.deepEqual(noId, { error: 'missing _id' });
    const badIdDelete = await $.ajax({
      url: url,
      type: 'DELETE',
      data: { _id: '5f665eb46e296f6b9b6a504d', issue_text: 'New Issue Text' }
    });
    assert.isObject(badIdDelete);
    assert.deepEqual(badIdDelete, {
      error: 'could not delete',
      _id: '5f665eb46e296f6b9b6a504d'
    });
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Todas las 14 pruebas funcionales están completas y pasaron.

```js
async () => {
  try {
    const getTests = await $.get(code + '/_api/get-tests');
    assert.isArray(getTests);
    assert.isAtLeast(getTests.length, 14, 'At least 14 tests passed');
    getTests.forEach((test) => {
      assert.equal(test.state, 'passed', 'Test in Passed State');
      assert.isAtLeast(
        test.assertions.length,
        1,
        'At least one assertion per test'
      );
    });
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

