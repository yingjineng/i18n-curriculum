---
id: 587d824b367417b2b2512c4a
title: Usare il doppio uguale per affermare l'uguaglianza
challengeType: 2
forumTopicId: 301609
dashedName: use-the-double-equals-to-assert-equality
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

`equal()` confronta oggetti usando `==`.

# --instructions--

All'interno di `tests/1_unit-test.js` sotto il test etichettato `#5` nella suite `Equality` ,cambiare ogni `assert` in `assert.equal` o `assert.notEqual` per far passare il test (dovrebbe risultare `true`). Non alterare gli argomenti passati alle asserzioni.

# --hints--

Tutti i test dovrebbero essere superati.

```js
  $.get(code + '/_api/get-tests?type=unit&n=4').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti scegliere il metodo corretto per la prima asserzione - `equal` oppure `notEqual`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=4').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'equal',
        'Numbers are coerced into strings with == '
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti scegliere il metodo corretto per la seconda asserzione - `equal` oppure `notEqual`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=4').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'notEqual',
        ' == compares object references'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti scegliere il metodo corretto per la terza asserzione - `equal` oppure `notEqual`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=4').then(
    (data) => {
      assert.equal(
        data.assertions[2].method,
        'equal',
        "6 * '2' is 12 ! It should be equal to '12'"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti scegliere il metodo corretto per la quarta asserzione - `equal` oppure `notEqual`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=4').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'notEqual', "6 + '2' is '62'...");
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

