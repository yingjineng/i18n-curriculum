---
id: 5e601c0d5ac9d0ecd8b94afe
title: Traductor británico americano
challengeType: 4
forumTopicId: 462358
dashedName: american-british-translator
---

# --description--

Construye una aplicación full stack de JavaScript que sea funcionalmente similar a esta: <a href="https://american-british-translator.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://american-british-translator.freecodecamp.rocks/</a>. Trabajar en este proyecto implicará escribir tu código utilizando uno de los siguientes métodos:

-   Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-american-british-english-translator/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
-   Usa un constructor de sitios de tu elección para completar el proyecto. Asegúrate de incorporar todos los archivos de nuestro repositorio de GitHub.

# --instructions--

-   Toda la lógica puede ir dentro de `/components/translator.js`
-   Completa la ruta `/api/translate` en `/routes/api.js`
-   Crea todas las pruebas unitarias/funcionales en `tests/1_unit-tests.js` y `tests/2_functional-tests.js`
-   Consulta los archivos de JavaScript en `/components` para ver las diferentes ortografías y términos que debe traducir tu aplicación
-   Para ejecutar las pruebas automáticamente, establece `NODE_ENV` a `test` sin comillas en el `.env`archivo
-   Para ejecutar las pruebas en la consola, usa el comando: `npm run test`.

Escribe las siguientes pruebas en `tests/1_unit-tests.js`:

-   Traduce `Mangoes are my favorite fruit.` a Inglés Británico
-   Traduce `I ate yogurt for breakfast.` al inglés británico
-   Traduce `We had a party at my friend's condo.` al inglés británico
-   Traduce `Can you toss this in the trashcan for me?` al inglés británico
-   Traduce `The parking lot was full.` a Inglés británico
-   Traduce `Like a high tech Rube Goldberg machine.` al inglés británico
-   Traduce `To play hooky means to skip class or work.` al inglés británico
-   Traduce `No Mr. Bond, I expect you to die.` a Inglés británico
-   Traduce `Dr. Grosh will see you now.` a Inglés británico
-   Traduce `Lunch is at 12:15 today.` al inglés británico
-   Traduce `We watched the footie match for a while.` al inglés americano
-   Traduce `Paracetamol takes up to an hour to work.` al inglés americano
-   Traduce `First, caramelise the onions.` al inglés americano
-   Traduce `I spent the bank holiday at the funfair.` al inglés americano
-   Traduce `I had a bicky then went to the chippy.` a Inglés Americano
-   Traduce `I've just got bits and bobs in my bum bag.` al inglés americano
-   Traduce `The car boot sale at Boxted Airfield was called off.` al inglés americano
-   Traduce `Have you met Mrs Kalyani?` al inglés americano
-   Traduce `Prof Joyner of King's College, London.` al inglés americano
-   Traduce `Tea time is usually around 4 or 4.30.` al inglés americano
-   Resalta la traducción en `Mangoes are my favorite fruit.`
-   Resalta la traducción en `I ate yogurt for breakfast.`
-   Resalta la traducción en `We watched the footie match for a while.`
-   Resalta la traducción en `Paracetamol takes up to an hour to work.`

Escribe las siguientes pruebas en `tests/2_functional-tests.js`:

-   Traduce con texto y campos locales: petición POST a `/api/translate`
-   Traducción con texto y campo de configuración regional no válido: solicitud POST a `/api/translate`
-   Traducción con campo de texto faltante: solicitud POST a `/api/translate`
-   Traducción sin campo de configuración regional: solicitud POST a `/api/translate`
-   Traducción con texto vacío: solicitud POST a `/api/translate`
-   Traducción con texto que no necesita traducción: solicitud POST a `/api/translate`

# --hints--

Debes proporcionar tu propio proyecto, no la URL del ejemplo.

```js
  assert(
    !/.*\/american-british-translator\.freecodecamp\.rocks/.test(
      code
    )
  );
```

Puedes `POST` a `/api/translate` con un cuerpo conteniendo `text` con el texto para traducir y `locale` con cualquiera `american-to-british` o `british-to-american`. El objeto devuelto debería contener el `text` y `translation` con el texto traducido.

```js
async () => {
  try {
    const text = 'Mangoes are my favorite fruit.';
    const locale = 'american-to-british';
    const output = {
      text: 'Mangoes are my favorite fruit.',
      translation:
        'Mangoes are my <span class="highlight">favourite</span> fruit.'
    };
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text, locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'text');
    assert.property(parsed, 'translation');
    assert.deepEqual(parsed, output);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

La ruta `/api/translate` debería manejar la forma de escritura de hora en inglés Americano y Británico. Por ejemplo, diez y treinta es escrito como "10.30" en Inglés Británico y "10:30" en Inglés Americano. The `span` element should wrap the entire time string, i.e. `<span class="highlight">10:30</span>`.

```js
async () => {
  try {
    const text = 'Lunch is at 12:15 today.';
    const locale = 'american-to-british';
    const output = {
      text: text,
      translation: 'Lunch is at <span class="highlight">12.15</span> today.'
    };
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text, locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'text');
    assert.property(parsed, 'translation');
    assert.deepEqual(parsed, output);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

La ruta `/api/translate` debería manejar la manera en que los titulares/honoríficos son abreviados en Inglés Americano y Británico. Por ejemplo, Doctor Wright es abreviado como "Dr Wright" en Inglés Británico y "Dr. Wright" en Inglés Americano. Consulta `/components/american-to-british-titles.js` para los diferentes titulares que tu aplicación debería manejar.

```js
async () => {
  try {
    const text = 'Dr. Grosh will see you now.';
    const locale = 'american-to-british';
    const output = {
      text: text,
      translation: '<span class="highlight">Dr</span> Grosh will see you now.'
    };
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text, locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'text');
    assert.property(parsed, 'translation');
    assert.deepEqual(parsed, output);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Wrap any translated spelling or terms with `<span class="highlight">...</span>` tags so they appear in green.

```js
async () => {
  try {
    const text = 'Mangoes are my favorite fruit.';
    const locale = 'american-to-british';
    const output = {
      text: 'Mangoes are my favorite fruit.',
      translation:
        'Mangoes are my <span class="highlight">favourite</span> fruit.'
    };
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text, locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'text');
    assert.property(parsed, 'translation');
    assert.deepEqual(parsed, output);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Si falta uno o más campos requeridos, devuelve `{ error: 'Required field(s) missing' }`.

```js
async () => {
  try {
    const locale = 'american-to-british';
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'error');
    assert.equal(parsed.error, 'Required field(s) missing');
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Si `text` esta vació, devuelve `{ error: 'No text to translate' }`

```js
async () => {
  try {
    const locale = 'american-to-british';
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text: '', locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'error');
    assert.equal(parsed.error, 'No text to translate');
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Si `locale` no coincide con uno de los dos locales especificados, devuelve `{ error: 'Invalid value for locale field' }`.

```js
async () => {
  try {
    const text = "Ceci n'est pas une pipe";
    const locale = 'french-to-american';
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text, locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.property(parsed, 'error');
    assert.equal(parsed.error, 'Invalid value for locale field');
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Si `text` no requiere traduciión, devuelve `"Everything looks good to me!"` para el valor `translation`.

```js
async () => {
  try {
    const locale = 'british-to-american';
    const output = {
      text: 'SaintPeter and nhcarrigan give their regards!',
      translation: 'Everything looks good to me!'
    };
    let data = await fetch(code + '/api/translate', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ text: output.text, locale })
    });
    let parsed = await data.json();
    assert.isObject(parsed);
    assert.isObject(parsed);
    assert.property(parsed, 'text');
    assert.property(parsed, 'translation');
    assert.deepEqual(parsed, output);
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Todas las 24 pruebas unitarias están completas y pasan.

```js
async () => {
  try {
    const getTests = await $.get(code + '/_api/get-tests');
    assert.isArray(getTests);
    const unitTests = getTests.filter((test) => {
      return !!test.context.match(/Unit Tests/gi);
    });
    assert.isAtLeast(unitTests.length, 24, 'At least 24 tests passed');
    unitTests.forEach((test) => {
      assert.equal(test.state, 'passed', 'Tests in Passed State');
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

Todas las 6 pruebas funcionales están completas y pasan.

```js
async () => {
  try {
    const getTests = await $.get(code + '/_api/get-tests');
    assert.isArray(getTests);
    const functTests = getTests.filter((test) => {
      return !!test.context.match(/Functional Tests/gi);
    });
    assert.isAtLeast(functTests.length, 6, 'At least 6 tests passed');
    functTests.forEach((test) => {
      assert.equal(test.state, 'passed', 'Tests in Passed State');
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
