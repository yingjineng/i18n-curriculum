---
id: 587d824d367417b2b2512c50
title: Teste, ob ein Wert ein Array ist
challengeType: 2
forumTopicId: 301600
dashedName: test-if-a-value-is-an-array
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Ändere innerhalb `tests/1_unit-tests.js` unter dem Test mit der Beschriftung `#11` in der `Arrays`-Suite, jeden `assert` in `assert.isArray` oder `assert.isNotArray` um, damit der Test bestanden wird (sollte `true` ausgeben). Ändere nicht die Argumente, die an die Assertions übergeben werden.

# --hints--

Alle Tests sollten durchlaufen.

```js
  $.get(code + '/_api/get-tests?type=unit&n=10').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest die richtige Methode für die erste Behauptung wählen, `isArray` vs. `isNotArray`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=10').then(
    (data) => {
      assert.equal(
        data.assertions[0].method,
        'isArray',
        'String.prototype.split() returns an Array'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest die richtige Methode für die zweite Behauptung wählen, `isArray` vs. `isNotArray`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=10').then(
    (data) => {
      assert.equal(
        data.assertions[1].method,
        'isNotArray',
        'Array.prototype.indexOf() returns a number'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

