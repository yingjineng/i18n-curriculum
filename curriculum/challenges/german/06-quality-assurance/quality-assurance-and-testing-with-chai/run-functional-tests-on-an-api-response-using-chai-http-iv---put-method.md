---
id: 587d824f367417b2b2512c5b
title: Funktionstests für eine API-Antwort mit Chai-HTTP IV - PUT-Methode durchführen
challengeType: 2
forumTopicId: 301591
dashedName: run-functional-tests-on-an-api-response-using-chai-http-iv---put-method
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Diese Übung ist ähnlich zu der vorherigen.

Jetzt, da du weißt, wie man eine `PUT`-Anfrage testet, bist du an der Reihe, es von Grund auf selbst zu machen.

# --instructions--

Innerhalb `tests/2_functional-tests.js`, ändere den `'Send {surname: "da Verrazzano"}'` Test (`// #4`) und verwende die `put` und `send` Methoden, um den `'/travellers'` Endpunkt zu testen.

Sende das folgende JSON-Objekt mit deiner PUT-Anfrage:

```json
{
  "surname": "da Verrazzano"
}
```

Überprüfe, ob der `request.end` Callback Folgendes enthält:

1.  The `status` should be `200`
2.  Der `type` sollte `application/json` sein
3.  Der `body.name` sollte `Giovanni` sein
4.  Der `body.surname` sollte `da Verrazzano` sein

Folge der obigen Reihenfolge der Behauptung- wir benötigen sie. Stelle außerdem sicher, dass du `assert.fail()` nach der Fertigstellung entfernst.

# --hints--

Alle Tests sollten bestanden werden

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest testen ob der `res.status` 200 beträgt

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
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

Du solltest testen ob `res.type` Folgendes ist: `'application/json'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.type');
      assert.match(data.assertions[1].args[1], /('|")application\/json\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest testen ob `res.body.name` Folgendes ist: `'Giovanni'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.assertions[2].method, 'equal');
      assert.equal(data.assertions[2].args[0], 'res.body.name');
      assert.match(data.assertions[2].args[1], /('|")Giovanni\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Du solltest testen ob `res.body.surname` Folgendes ist: `'da Verrazzano'`

```js
  $.get(code + '/_api/get-tests?type=functional&n=3').then(
    (data) => {
      assert.equal(data.assertions[3].method, 'equal');
      assert.equal(data.assertions[3].args[0], 'res.body.surname');
      assert.match(data.assertions[3].args[1], /('|")da Verrazzano\1/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

