---
id: 587d824b367417b2b2512c48
title: Використайте Assert.isOK та Assert.isNotOK
challengeType: 2
forumTopicId: 301607
dashedName: use-assert-isok-and-assert-isnotok
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`isOk()` перевіряє істинне значення, а `isNotOk()` перевіряє хибне значення.

Щоб дізнатися більше про істинні й хибні значення, див. наше завдання <a href="https://www.freecodecamp.org/ukrainian/learn/javascript-algorithms-and-data-structures/basic-algorithm-scripting/falsy-bouncer" target="_blank" rel="noopener noreferrer nofollow">«Викидайло брехні»</a>.

# --instructions--

У межах `tests/1_unit-tests.js` під тестом з міткою `#3` в наборі `Basic Assertions` змініть кожний `assert` на `assert.isOk()` або `assert.isNotOk()`, щоб пройти тест (повинен дорівнювати `true`). Не змінюйте аргументи, передані до тверджень.

# --hints--

Всі тести повинні бути успішно пройдені.

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні обрати правильний метод для першого твердження: `isOk` або `isNotOk`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'isNotOk', 'Null is falsy');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні обрати правильний метод для другого твердження: `isOk` або `isNotOk`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'isOk', 'A string is truthy');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Ви повинні обрати правильний метод для третього твердження: `isOk` або `isNotOk`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=2').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'isOk', 'true is truthy');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

