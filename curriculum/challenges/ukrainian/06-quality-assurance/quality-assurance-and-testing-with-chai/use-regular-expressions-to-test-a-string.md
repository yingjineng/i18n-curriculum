---
id: 587d824d367417b2b2512c54
title: Використайте регулярні вирази для перевірки рядка
challengeType: 2
forumTopicId: 301608
dashedName: use-regular-expressions-to-test-a-string
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`match()` підтверджує, що значення відповідає регулярному виразу другого аргументу.

# --instructions--

У межах `tests/1_unit-tests.js` під тестом з міткою `#15` в наборі `Strings` змініть кожний `assert` на `assert.match` або `assert.notMatch`, щоб пройти тест (повинен дорівнювати `true`). Не змінюйте аргументи, передані до тверджень.

# --hints--

Усі тести повинні пройти.

```js
  $.get(code + '/_api/get-tests?type=unit&n=14').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні обрати правильний метод для першого твердження: `match` або `notMatch`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=14').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'match',
        "'# name:John Doe, age:35' matches the regex"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні обрати правильний метод для другого твердження: `match` або `notMatch`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=14').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'notMatch',
        "'# name:Paul Smith III, age:twenty-four' does not match the regex (the age must be numeric)"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

