---
id: 587d824a367417b2b2512c44
title: Comprobador de precios de acciones
challengeType: 4
forumTopicId: 301572
dashedName: stock-price-checker
---

# --description--

Construye una aplicación full stack de JavaScript que sea funcionalmente similar a esta: <a href="https://stock-price-checker.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://stock-price-checker.freecodecamp.rocks/</a>.

Como todas las API de precios de acciones fiables requieren una clave de API, hemos creado una solución. Utilice <a href="https://stock-price-checker-proxy.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://stock-price-checker-proxy.freecodecamp.rocks/</a> para obtener información actualizada del precio de las acciones sin necesidad de registrarte para tu propia clave.

Trabajar en este proyecto implicará escribir tu código utilizando uno de los siguientes métodos:

-   Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-stockchecker/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
-   Usa un constructor de sitios de tu elección para completar el proyecto. Asegúrate de incorporar todos los archivos de nuestro repositorio de GitHub.

# --instructions--

1.  Set the `NODE_ENV` environment variable to `test`, without quotes
2.  Completa el proyecto en `routes/api.js` o creando un manejador/controlador
3.  Añadirás cualquier característica de seguridad a `server.js`
4.  Crearás todas las pruebas funcionales en `tests/2_functional-tests.js`

**Note** Privacy Considerations: Due to the requirement that only 1 like per IP should be accepted, you will have to save IP addresses. Es importante seguir cumpliendo con leyes de privacidad como el Reglamento General de Protección de Datos. Una opción es obtener permiso para guardar los datos del usuario, pero es mucho más simple hacerlo anónimo. Para este desafío, recuerde anonimizar las direcciones IP antes de guardarlas en la base de datos. If you need ideas on how to do this, you may choose to hash the data, truncate it, or set part of the IP address to 0.

Escribe las siguientes pruebas en `tests/2_functional-tests.js`:

-   Viewing one stock: GET request to `/api/stock-prices/`
-   Viewing one stock and liking it: GET request to `/api/stock-prices/`
-   Viewing the same stock and liking it again: GET request to `/api/stock-prices/`
-   Viewing two stocks: GET request to `/api/stock-prices/`
-   Viewing two stocks and liking them: GET request to `/api/stock-prices/`

# --hints--

Puedes proporcionar tu propio proyecto, no la URL ejemplo.

```js
  assert(
    !/.*\/stock-price-checker\.freecodecamp\.rocks/.test(code)
  );
```

You should set the content security policies to only allow loading of scripts and CSS from your server.

```js
async () => {
  const data = await fetch(code + '/_api/app-info');
  const parsed = await data.json();
  assert.isTrue(
    parsed.headers['content-security-policy'].includes("script-src 'self'")
  );
  assert.isTrue(
    parsed.headers['content-security-policy'].includes("style-src 'self'")
  );
};
```

You can send a `GET` request to `/api/stock-prices`, passing a NASDAQ stock symbol to a `stock` query parameter. The returned object will contain a property named `stockData`.

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG'
  );
  const parsed = await data.json();
  assert.property(parsed, 'stockData');
};
```

The `stockData` property includes the `stock` symbol as a string, the `price` as a number, and `likes` as a number.

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG'
  );
  const parsed = await data.json();
  const ticker = parsed.stockData;
  assert.typeOf(ticker.price, 'number');
  assert.typeOf(ticker.likes, 'number');
  assert.typeOf(ticker.stock, 'string');
};
```

You can also pass along a `like` field as `true` (boolean) to have your like added to the stock(s). Only 1 like per IP should be accepted.

```js

```

If you pass along 2 stocks, the returned value will be an array with information about both stocks. Instead of `likes`, it will display `rel_likes` (the difference between the likes on both stocks) for both `stockData` objects.

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG&stock=MSFT'
  );
  const parsed = await data.json();
  const ticker = parsed.stockData;
  assert.typeOf(ticker, 'array');
  assert.property(ticker[0], 'rel_likes');
  assert.property(ticker[1], 'rel_likes');
};
```

Las 5 pruebas funcionales están completas y aprobadas.

```js
async () => {
  const tests = await fetch(code + '/_api/get-tests');
  const parsed = await tests.json();
  assert.isTrue(parsed.length >= 5);
  parsed.forEach((test) => {
    assert.equal(test.state, 'passed');
  });
};
```

