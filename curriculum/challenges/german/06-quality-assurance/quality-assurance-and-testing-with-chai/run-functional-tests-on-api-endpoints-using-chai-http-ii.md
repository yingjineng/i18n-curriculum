---
id: 587d824f367417b2b2512c59
title: Funktionstests an API-Endpunkten mit Chai-HTTP II durchführen
challengeType: 2
forumTopicId: 301592
dashedName: run-functional-tests-on-api-endpoints-using-chai-http-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

Innerhalb von `tests/2_functional-tests.js`, ändere `'Test GET /hello with your name'` Test (`// #2`) um den `status` und den `text` der Antwort geltend zu machen, um den Test zu bestehen.

Sende deinen Namen als URL Query, indem du `?name=<your_name>` an den Pfad anhängst. Der Endpunkt antwortet mit `'hello <your_name>'`.

# --hints--

Alle Tests sollten bestanden werden

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest auf `res.status` == 200 testen

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'equal');
      assert.equal(data.assertions[0].args[0], 'res.status');
      assert.equal(data.assertions[0].args[1], '200');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest auf `res.text` == `'hello <your_name>'` testen

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /hello [\w\d_-]/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

