---
id: 587d824a367417b2b2512c46
title: Imparare come funzionano le asserzioni Javascript
challengeType: 2
forumTopicId: 301589
dashedName: learn-how-javascript-assertions-work
---

# --description--

Working on these challenges will involve you writing your code using one of the following methods:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete these challenges locally.
- Usare un costruttore di siti di tua scelta per completare il progetto. Assicurati di incorporare tutti i file del nostro repository GitHub.

# --instructions--

Within `tests/1_unit-tests.js` under the test labeled `#1` in the `Basic Assertions` suite, change each `assert` to either `assert.isNull` or `assert.isNotNull` to make the test pass (should evaluate to `true`). Non alterare gli argomenti passati alle asserzioni.

# --hints--

Tutti i test dovrebbero essere superati.

```js
  $.get(code + '/_api/get-tests?type=unit&n=0').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

You should choose the correct method for the first assertion - `isNull` vs. `isNotNull`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=0').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'isNull', 'Null is null');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

You should choose the correct method for the second assertion - `isNull` vs. `isNotNull`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=0').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'isNotNull', '1 is not null');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

