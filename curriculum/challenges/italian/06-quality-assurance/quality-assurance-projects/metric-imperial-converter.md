---
id: 587d8249367417b2b2512c41
title: Convertitore Metrico-Imperiale
challengeType: 4
forumTopicId: 301570
dashedName: metric-imperial-converter
---

# --description--

Build a full stack JavaScript app that is functionally similar to this: <a href="https://metric-imperial-converter.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://metric-imperial-converter.freecodecamp.rocks/</a>. Working on this project will involve you writing your code using one of the following methods:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-metricimpconverter/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
- Use a site builder of your choice to complete the project. Be sure to incorporate all the files from our GitHub repo.

**Note:** This project's tests do not work when using `glitch.com`.

# --instructions--

- Complete the necessary conversion logic in `/controllers/convertHandler.js`
- Completa le rotte necessarie in `/routes/api.js`
- Copia il file `sample.env` su `.env` e imposta le variabili in modo appropriato
- To run the tests automatically, add `NODE_ENV=test` in your `.env` file
- To run the tests in the console, use the command `npm run test`.

Scrivi i seguenti test in `tests/1_unit-tests.js`:

- `convertHandler` should correctly read a whole number input.
- `convertHandler` dovrebbe leggere correttamente un numero decimale inserito.
- `convertHandler` dovrebbe leggere correttamente una frazione inserita.
- `convertHandler` dovrebbe leggere correttamente un input frazionario con un decimale.
- `convertHandler` dovrebbe restituire correttamente un errore su una doppia frazione (cioè `3/2/3`).
- `convertHandler` dovrebbe essere correttamente predefinito con un input numerico di `1` quando non viene fornito alcun input numerico.
- `convertHandler` dovrebbe leggere correttamente ogni input valido.
- `convertHandler` dovrebbe restituire un errore per ogni input non valido.
- `convertHandler` dovrebbe restituire l'unità di ritorno corretta per ogni unità di input valida.
- `convertHandler` dovrebbe restituire correttamente l'unità di misura scritta per esteso per ogni unità di input valida.
- `convertHandler` dovrebbe convertire correttamente `gal` in `L`.
- `convertHandler` dovrebbe convertire correttamente `L` in `gal`.
- `convertHandler` dovrebbe convertire correttamente `mi` in `km`.
- `convertHandler` dovrebbe convertire correttamente `km` in `mi`.
- `convertHandler` dovrebbe convertire correttamente `lbs` in `kg`.
- `convertHandler` dovrebbe convertire correttamente `kg` in `lbs`.

Scrivi i seguenti test in `tests/2_functional-tests.js`:

- Convert a valid input such as `10L`: `GET` request to `/api/convert`.
- Converti un input non valido come `32g`: richiesta `GET` a `/api/convert`.
- Converti un input non valido come `3/7.2/4kg`: richiesta `GET` a `/api/convert`.
- Converti un input non valido come `3/7.2/4kilomegagram`: richiesta `GET` a `/api/convert`.
- Converti un input senza alcun numero come `kg`: richiesta `GET` a `/api/convert`.

# --hints--

È necessario fornire il proprio progetto, non l'URL di esempio.

```js
  assert(
    !/.*\/metric-imperial-converter\.freecodecamp\.rocks/.test(
      code
    )
  );
```

È possibile ottenere (`GET`) `/api/convert` con un singolo parametro contenente un numero e un'unità validi e convertirlo. (Suggerimento: Dividi l'input cercando l'indice del primo carattere, che segnerà l'inizio dell'unità)

```js

```

Puoi convertire `'gal'` in `'L'` e viceversa. (1 gal in 3.78541 L)

```js
async () => {
  try {
    const data1 = await $.get(code + '/api/convert?input=1gal');
    assert.equal(data1.returnNum, 3.78541);
    assert.equal(data1.returnUnit, 'L');
    const data2 = await $.get(code + '/api/convert?input=10gal');
    assert.equal(data2.returnNum, 37.8541);
    assert.equal(data2.returnUnit, 'L');
    const data3 = await $.get(code + '/api/convert?input=1l');
    assert.equal(data3.returnNum, 0.26417);
    assert.equal(data3.returnUnit, 'gal');
    const data4 = await $.get(code + '/api/convert?input=10l');
    assert.equal(data4.returnNum, 2.64172);
    assert.equal(data4.returnUnit, 'gal');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Puoi convertire `'lbs'` in `'kg'` e viceversa. (1 lbs in 0,453592 kg)

```js
async () => {
  try {
    const data1 = await $.get(code + '/api/convert?input=1lbs');
    assert.equal(data1.returnNum, 0.45359);
    assert.equal(data1.returnUnit, 'kg');
    const data2 = await $.get(code + '/api/convert?input=10lbs');
    assert.equal(data2.returnNum, 4.53592);
    assert.equal(data2.returnUnit, 'kg');
    const data3 = await $.get(code + '/api/convert?input=1kg');
    assert.equal(data3.returnNum, 2.20462);
    assert.equal(data3.returnUnit, 'lbs');
    const data4 = await $.get(code + '/api/convert?input=10kg');
    assert.equal(data4.returnNum, 22.04624);
    assert.equal(data4.returnUnit, 'lbs');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Puoi convertire `'mi'` in `'km'` e viceversa. (1 mi in 1.60934 km)

```js
async () => {
  try {
    const data1 = await $.get(code + '/api/convert?input=1mi');
    assert.equal(data1.returnNum, 1.60934);
    assert.equal(data1.returnUnit, 'km');
    const data2 = await $.get(code + '/api/convert?input=10mi');
    assert.equal(data2.returnNum, 16.0934);
    assert.equal(data2.returnUnit, 'km');
    const data3 = await $.get(code + '/api/convert?input=1km');
    assert.equal(data3.returnNum, 0.62137);
    assert.equal(data3.returnUnit, 'mi');
    const data4 = await $.get(code + '/api/convert?input=10km');
    assert.equal(data4.returnNum, 6.21373);
    assert.equal(data4.returnUnit, 'mi');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Tutte le unità in entrata dovrebbero essere accettate sia in maiuscolo che in minuscolo, ma dovrebbero essere restituite in minuscolo sia per `initUnit` che `returnUnit`, ad eccezione del litro, che dovrebbe essere rappresentato come una `'L'` maiuscola.

```js
async () => {
  try {
    const data1 = await $.get(code + '/api/convert?input=1gal');
    assert.equal(data1.initUnit, 'gal');
    assert.equal(data1.returnUnit, 'L');
    const data2 = await $.get(code + '/api/convert?input=10L');
    assert.equal(data2.initUnit, 'L');
    assert.equal(data2.returnUnit, 'gal');
    const data3 = await $.get(code + '/api/convert?input=1l');
    assert.equal(data3.initUnit, 'L');
    assert.equal(data3.returnUnit, 'gal');
    const data4 = await $.get(code + '/api/convert?input=10KM');
    assert.equal(data4.initUnit, 'km');
    assert.equal(data4.returnUnit, 'mi');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Se l'unità di misura non è valida, sarà restituito `'invalid unit'`.

```js
async () => {
  try {
    const data = await $.get(code + '/api/convert?input=1min');
    assert(data.error === 'invalid unit' || data === 'invalid unit');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Se il numero non è valido, sarà restituito `'invalid number'`.

```js
async () => {
  try {
    const data = await $.get(
      code + '/api/convert?input=1//2gal'
    );
    assert(data.error === 'invalid number' || data === 'invalid number');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Se sia l'unità che il numero non sono validi, sarà restituito `'invalid number and unit'`.

```js
async () => {
  try {
    const data = await $.get(
      code + '/api/convert?input=1//2min'
    );
    assert(
      data.error === 'invalid number and unit' ||
        data === 'invalid number and unit'
    );
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

È possibile utilizzare frazioni, decimali o entrambi nel parametro (es. 5, 1/2, 2.5/6), ma se non viene fornito nulla il valore predefinito sarà 1.

```js
async () => {
  try {
    const data1 = await $.get(code + '/api/convert?input=mi');
    assert.approximately(data1.initNum, 1, 0.001);
    assert.approximately(data1.returnNum, 1.60934, 0.001);
    assert.equal(data1.returnUnit, 'km');
    const data2 = await $.get(code + '/api/convert?input=1/5mi');
    assert.approximately(data2.initNum, 1 / 5, 0.1);
    assert.approximately(data2.returnNum, 0.32187, 0.001);
    assert.equal(data2.returnUnit, 'km');
    const data3 = await $.get(
      code + '/api/convert?input=1.5/7km'
    );
    assert.approximately(data3.initNum, 1.5 / 7, 0.001);
    assert.approximately(data3.returnNum, 0.13315, 0.001);
    assert.equal(data3.returnUnit, 'mi');
    const data4 = await $.get(
      code + '/api/convert?input=3/2.7km'
    );
    assert.approximately(data4.initNum, 3 / 2.7, 0.001);
    assert.approximately(data4.returnNum, 0.69041, 0.001);
    assert.equal(data4.returnUnit, 'mi');
  } catch (err) {
    throw new Error(err.responseText || err.message);
  }
};
```

Il tuo risultato consisterà in `initNum`, `initUnit`, `returnNum`, `returnUnit`, e `string` che indica le unità nel formato `'{initNum} {initUnitString} converts to {returnNum} {returnUnitString}'` con il risultato arrotondato a 5 decimali.

```js
async () => {
  try {
    const data = await $.get(code + '/api/convert?input=2mi');
    assert.equal(data.initNum, 2);
    assert.equal(data.initUnit, 'mi');
    assert.approximately(data.returnNum, 3.21868, 0.001);
    assert.equal(data.returnUnit, 'km', 'returnUnit did not match');
    assert.equal(data.string, '2 miles converts to 3.21868 kilometers');
  } catch (xhr) {
    throw new Error(xhr.responseText || xhr.message);
  }
};
```

Tutti i 16 test funzionali richiesti sono completi e superati.

```js
async () => {
  try {
    const getTests = await $.get(code + '/_api/get-tests');
    assert.isArray(getTests);
    const unitTests = getTests.filter(test => {
      return !!test.context.match(/Unit Tests/gi);
    });
    assert.isAtLeast(unitTests.length, 16, 'At least 16 tests passed');
    unitTests.forEach(test => {
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

Tutti i 5 test funzionali richiesti sono completi e superati.

```js
async () => {
  try {
    const getTests = await $.get(code + '/_api/get-tests');
    assert.isArray(getTests);
    const functTests = getTests.filter(test => {
      return !!test.context.match(/Functional Tests/gi);
    });
    assert.isAtLeast(functTests.length, 5, 'At least 5 tests passed');
    functTests.forEach(test => {
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

