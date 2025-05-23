---
id: 587d824c367417b2b2512c4f
title: Testen ob ein Wert innerhalb eines bestimmten Bereichs fällt
challengeType: 2
forumTopicId: 301598
dashedName: test-if-a-value-falls-within-a-specific-range
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

```javascript
.approximately(actual, expected, delta, [message])
```

Überprüft, dass `actual` gleich `expected` ist, innerhalb einem +/- `delta` Spielraum.

# --instructions--

Ändere innerhalb `tests/1_unit-tests.js` mit dem gekennzeichneten Test`#10` in der `Comparisons` Suite, jeden `assert`, zu `assert.approximately`, um den Test zu bestehen (sollte `true` ausgeben).

Wählen den Minimalbereich (3. Parameter) aus, damit der Test immer bestanden wird. Es sollte weniger als 1 sein.

# --hints--

Alle Tests sollten erfolgreich sein.

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest den richtigen Bereich für die erste Behauptung wählen - `approximately(actual, expected, range)`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'approximately');
      assert.equal(
        data.assertions[0].args[2],
        0.5,
        "weirdNumbers(0.5) is in the range (0.5, 1.5]. It's within 1 +/- 0.5"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest den richtigen Bereich für die zweite Behauptung wählen - `approximately(actual, expected, range)`.

```js
  $.get(code + '/_api/get-tests?type=unit&n=9').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'approximately');
      assert.equal(
        data.assertions[1].args[2],
        0.8,
        "weirdNumbers(0.2) is in the range (0.2, 1.2]. It's within 1 +/- 0.8"
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

