---
id: 587d8249367417b2b2512c41
title: Метрично-імперський конвертер
challengeType: 4
forumTopicId: 301570
dashedName: metric-imperial-converter
---

# --description--

Build a full stack JavaScript app that is functionally similar to this: <a href="https://metric-imperial-converter.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://metric-imperial-converter.freecodecamp.rocks/</a>. Робота над цим проєктом передбачає написання коду за допомогою одного з наступних методів:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-metricimpconverter/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
- Use a site builder of your choice to complete the project. Be sure to incorporate all the files from our GitHub repo.

**Note:** This project's tests do not work when using `glitch.com`.

# --instructions--

- Complete the necessary conversion logic in `/controllers/convertHandler.js`
- Завершіть необхідні маршрути у `/routes/api.js`
- Скопіюйте файл `sample.env` до `.env` і встановіть відповідні змінні
- Щоб запустити тести автоматично, додайте `NODE_ENV=test` до файлу `.env`
- To run the tests in the console, use the command `npm run test`.

Пропишіть наступні тести у `tests/1_unit-tests.js`:

- `convertHandler` should correctly read a whole number input.
- `convertHandler` має правильно прочитати введення десяткового числа.
- `convertHandler` має правильно прочитати введення дробових даних.
- `convertHandler` має правильно прочитати введення дробових даних із десятковим числом.
- `convertHandler` має правильно повернути помилку про подвійний дріб (наприклад, `3/2/3`).
- `convertHandler` має правильно приймати за замовчуванням числове введення `1`, якщо числове введення не надано.
- `convertHandler` має правильно прочитати всі допустимі одиниці вимірів, які вводяться.
- `convertHandler` має правильно повернути помилку для недопустимих одиниць виміру, які вводяться.
- `convertHandler` має повернути правильну одиницю виміру для кожної допустимої одиниці виміру, яка вводиться.
- `convertHandler` має правильно повернути прописаний рядок одиниці виміру для кожної допустимої одиниці виміру, яка вводиться.
- `convertHandler` має правильно конвертувати `gal` у `L`.
- `convertHandler` має правильно конвертувати `L` у `gal`.
- `convertHandler` має правильно конвертувати `mi` у `km`.
- `convertHandler` має правильно конвертувати `km` у `mi`.
- `convertHandler` має правильно конвертувати `lbs` у `kg`.
- `convertHandler` має правильно конвертувати `kg` у `lbs`.

Пропишіть наступні тести у `tests/2_functional-tests.js`:

- Convert a valid input such as `10L`: `GET` request to `/api/convert`.
- Конвертуйте недопустимі вхідні дані, як запит `32g`: `GET` до `/api/convert`.
- Конвертуйте недопустиме число, як запит `3/7.2/4kg`: `GET` до `/api/convert`.
- Конвертуйте недопустиме число ТА одиницю виміру, як запит `3/7.2/4kilomegagram`: `GET` до `/api/convert`.
- Конвертуйте без числа, як запит `kg`: `GET` до `/api/convert`.

# --hints--

Ви можете надати власний проєкт, а не URL-адресу прикладу.

```js
  assert(
    !/.*\/metric-imperial-converter\.freecodecamp\.rocks/.test(
      code
    )
  );
```

Ви можете надіслати запит `GET` `/api/convert` із єдиним параметром, який містить прийняте число та одиницю виміру та буде конвертований. (Підказка: розділіть вхідні дані шляхом пошуку індексу першого символу, який позначить початок одиниці виміру)

```js

```

Ви можете конвертувати `'gal'` у `'L'` та навпаки. (1 галон у 3.78541 л)

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

Ви можете конвертувати `'lbs'` у `'kg'` та навпаки. (1 фунт у 0.453592 кг)

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

Ви можете конвертувати `'mi'` у `'km'` та навпаки. (1 миля у 1.60934 км)

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

Написання усіх вхідних одиниць вимірів повинно прийматися, як із великої, так із малої літери, однак повинне повертатися в обох випадках `initUnit` та `returnUnit` у нижньому регістрі. Виключення становить одиниця "liter" - вона має бути повернута у верхньому регістрі `'L'`.

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

Якщо одиниця виміру недопустима - повернути наступне `'invalid unit'`.

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

Якщо число недопустиме - повернути наступне `'invalid number'`.

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

Якщо одиниця виміру і число недопустимі - повернути наступне `'invalid number and unit'`.

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

Ви можете використовувати дроби, десяткові числа або і те, і інше у параметрах(до прикладу: 5, 1/2, 2.5/6), але якщо нічого не вказано, то за замовчуванням встановиться 1.

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

Ваше повернення буде складатися із `initNum`, `initUnit`, `returnNum`, `returnUnit` та `string`, що прописують одиниці виміру у форматі`'{initNum} {initUnitString} converts to {returnNum} {returnUnitString}'` із округленим до 5-ти символів після коми результатом.

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

Усі 16 модульних тестів завершено та успішно пройдено.

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

Усі 5 функціональних тестів завершено та успішно пройдено.

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

