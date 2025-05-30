---
id: 5f8884f4c46685731aabfc41
title: Eseguire test funzionali usando un headless browser II
challengeType: 2
forumTopicId: 301594
dashedName: run-functional-tests-using-a-headless-browser-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

All'interno di `tests/2_functional-tests.js`, nel test `'Submit the surname "Vespucci" in the HTML form'` (`// #6`), automatizza quanto segue:

1.  Fill in the form with the surname `Vespucci`
2.  Press the submit button

E all'interno della callback `pressButton`:

1.  Assert that status is OK `200`
2.  Asserisci che il testo all'interno dell'elemento `span#name` è `'Amerigo'`
3.  Asserisci che il testo all'interno dell'elemento `span#surname` è `'Vespucci'`
4.  Asserisci che gli elementi `span#dates` esistono e il loro conteggio è `1`

Non dimenticare di rimuovere la chiamata `assert.fail()`.

# --hints--

Tutti i test dovrebbero essere superati.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti asserire che la richiesta dell'headless browser sia riuscita.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'browser.success');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti controllare che il testo all'interno dell'elemento `span#name` è `'Amerigo'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'browser.text');
      assert.match(data.assertions[1].args[0], /('|")span#name\1/);
      assert.match(data.assertions[1].args[1], /('|")Amerigo\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti verificare che il testo all'interno dell'elemento `span#surname` è `'Vespucci'`.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'browser.text');
      assert.match(data.assertions[2].args[0], /('|")span#surname\1/);
      assert.match(data.assertions[2].args[1], /('|")Vespucci\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Dovresti affermare che l'elemento `span#dates` esiste e il suo conteggio è 1.

```js
  $.get(code + '/_api/get-tests?type=functional&n=6').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'browser.elements');
      assert.match(data.assertions[3].args[0], /('|")span#dates\1/);
      assert.equal(data.assertions[3].args[1], 1);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

