---
id: 587d8249367417b2b2512c41
title: Conversor de medidas dos sistemas métrico e imperial
challengeType: 4
forumTopicId: 301570
dashedName: metric-imperial-converter
---

# --description--

Build a full stack JavaScript app that is functionally similar to this: <a href="https://metric-imperial-converter.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://metric-imperial-converter.freecodecamp.rocks/</a>. Trabalhar nesse projeto vai fazer com que você escreva o código usando um dos seguintes métodos:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-metricimpconverter/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
- Use a site builder of your choice to complete the project. Be sure to incorporate all the files from our GitHub repo.

**Note:** This project's tests do not work when using `glitch.com`.

# --instructions--

- Complete the necessary conversion logic in `/controllers/convertHandler.js`
- Complete a rota /api/translate em `/routes/api.js`
- Copie o arquivo `sample.env` para `.env` e defina as variáveis adequadamente
- Para executar os testes, adicione `NODE_ENV=test` no seu arquivo `.env`
- To run the tests in the console, use the command `npm run test`.

Escreva os testes a seguir em `tests/1_unit-tests.js`:

- `convertHandler` should correctly read a whole number input.
- `convertHandler` deverá ler corretamente a entrada de números decimais.
- `convertHandler` deverá ler corretamente a entrada de frações.
- `convertHandler` deverá ler corretamente a entrada de frações com decimais.
- `convertHandler` deve retornar corretamente um erro em uma dupla fração (por exemplo, `3/2/3`).
- `convertHandler` deverá apresentar corretamente como padrão uma entrada numérica de `1` quando nenhuma entrada numérica for fornecida.
- `convertHandler` deverá ler corretamente unidade de entrada válida.
- `convertHandler` deverá retornar corretamente um erro para uma unidade de entrada inválida.
- `convertHandler` deverá retornar corretamente a unidade para cada unidade de entrada válida.
- `convertHandler` deverá retornar corretamente a unidade em string estendida para cada unidade de entrada válida.
- `convertHandler` deve converter corretamente `gal` para `L`.
- `convertHandler` deve converter corretamente `L` para `gal`.
- `convertHandler` deve converter corretamente `mi` para `km`.
- `convertHandler` deve converter corretamente `km` para `mi`.
- `convertHandler` deve converter corretamente `lbs` para `kg`.
- `convertHandler` deve converter corretamente `kg` para `lbs`.

Escreva os testes a seguir em `tests/2_functional-tests.js`:

- Convert a valid input such as `10L`: `GET` request to `/api/convert`.
- Converta uma entrada inválida, como `32g`: solicitação de `GET` para `/api/convert`.
- Converta um número inválido, como `3/7.2/4kg`: solicitação de `GET` para `/api/convert`.
- Converta um número inválido E uma unidade, como `3/7.2/4kilomegagram`: solicitação de `GET` para `/api/convert`.
- Converta sem número, como `kg`: solicitação de `GET` para `/api/convert`.

# --hints--

Você pode fornecer seu próprio projeto, não o exemplo de URL.

```js
  assert(
    !/.*\/metric-imperial-converter\.freecodecamp\.rocks/.test(
      code
    )
  );
```

Você pode fazer a solicitação de `GET` `/api/convert` com um único parâmetro que contém um número e unidade aceitos e fazer com que sejam convertidos. (Dica: divida a entrada procurando o índice do primeiro caractere que vai marcar o início da unidade)

```js

```

Você pode converter `'gal'` para `'L'` e vice-versa. (1 gal para 3.78541 L)

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

Você pode converter `'lbs'` para `'kg'` e vice-versa. (1 lbs para 0.453592 kg)

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

Você pode converter `'mi'` para `'km'` e vice-versa. (1 mi para 1.60934 km)

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

Todas as unidades de entrada devem ser aceitas em letras maiúsculas e minúsculas, mas devem ser retornadas em `initUnit` e `returnUnit` em minúsculas, exceto para litro, que deve ser representado como uma maiúscula `'L'`.

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

Se a unidade de medida for inválida, será retornado `'invalid unit'`.

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

Se o número for inválida, será retornado `'invalid number'`.

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

Se o número e a unidade forem inválidos, será retornado `'invalid number and unit'`.

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

Você pode usar frações, números decimais ou ambos no parâmetro (por exemplo, 5, 1/2, 2.5/6), mas se nada for fornecido, o padrão será 1.

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

O retorno consistirá em `initNum`, `initUnit`, `returnNum`, `returnUnit` e `string` escrevendo as unidades no formato `'{initNum} {initUnitString} converts to {returnNum} {returnUnitString}'` com o resultado arredondado para 5 casas decimais.

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

Todos os 16 testes de unidade foram concluídos e deram aprovação.

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

Todos os 5 testes funcionais foram concluídos e deram aprovação.

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

