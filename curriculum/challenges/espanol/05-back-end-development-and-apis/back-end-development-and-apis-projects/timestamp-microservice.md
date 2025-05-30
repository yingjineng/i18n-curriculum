---
id: bd7158d8c443edefaeb5bdef
title: Microservicio de marca de tiempo
challengeType: 4
forumTopicId: 301508
dashedName: timestamp-microservice
---

# --description--

Build a full stack JavaScript app that is functionally similar to this: <a href="https://timestamp-microservice.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://timestamp-microservice.freecodecamp.rocks</a>. Trabajar en este proyecto implicará escribir tu código utilizando uno de los siguientes métodos:

-   Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-timestamp/"  target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
-   Usa un constructor de sitios de tu elección para completar el proyecto. Asegúrate de incorporar todos los archivos de nuestro repositorio de GitHub.

**Nota:** La conversión de zonas horarias no es el propósito de este proyecto, por lo que asumimos que todas las fechas válidas enviadas serán analizadas con `new Date()` como fechas GMT.

# --hints--

Debes proporcionar tu propio proyecto, no la URL de ejemplo.

```js
  assert(
    !/.*\/timestamp-microservice\.freecodecamp\.rocks/.test(code)
  );
```

Una petición para `/api/:date?` con una fecha válida debe devolver un objeto JSON con una clave `unix` que es una marca de tiempo Unix de la fecha de entrada en milisegundos (como tipo Número)

```js
  $.get(code + '/api/2016-12-25').then(
    (data) => {
      assert.equal(
        data.unix,
        1482624000000,
        'Should be a valid unix timestamp'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Una petición para `/api/:date?` con una fecha válida debe devolver un objeto JSON con una clave `utc` que es una cadena de la fecha de entrada en el formato: `Thu, 01 Jan 1970 00:00:00 GMT`

```js
  $.get(code + '/api/2016-12-25').then(
    (data) => {
      assert.equal(
        data.utc,
        'Sun, 25 Dec 2016 00:00:00 GMT',
        'Should be a valid UTC date string'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Una petición a `/api/1451001600000` debe devolver `{ unix: 1451001600000, utc: "Fri, 25 Dec 2015 00:00:00 GMT" }`

```js
  $.get(code + '/api/1451001600000').then(
    (data) => {
      assert(
        data.unix === 1451001600000 &&
          data.utc === 'Fri, 25 Dec 2015 00:00:00 GMT'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Tu proyecto puede manejar fechas que pueden ser analizadas con éxito por `new Date(date_string)`

```js
  $.get(code + '/api/05 October 2011, GMT').then(
    (data) => {
      assert(
        data.unix === 1317772800000 &&
          data.utc === 'Wed, 05 Oct 2011 00:00:00 GMT'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Si la cadena representando la fecha es inválida, la API devuelve un objeto con la estructura `{ error : "Invalid Date" }`

```js
  $.get(code + '/api/this-is-not-a-date').then(
    (data) => {
      assert.equal(data.error.toLowerCase(), 'invalid date');
    },
    (xhr) => {
      assert(xhr.responseJSON.error.toLowerCase() === 'invalid date');
    }
  );
```

Un parámetro de fecha vacío debe devolver la hora actual en un objeto JSON con una clave `unix`

```js
  $.get(code + '/api').then(
    (data) => {
      var now = Date.now();
      assert.approximately(data.unix, now, 20000);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Un parámetro de fecha vacío debe devolver la hora actual en un objeto JSON con una clave `utc`

```js
  $.get(code + '/api').then(
    (data) => {
      var now = Date.now();
      var serverTime = new Date(data.utc).getTime();
      assert.approximately(serverTime, now, 20000);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

