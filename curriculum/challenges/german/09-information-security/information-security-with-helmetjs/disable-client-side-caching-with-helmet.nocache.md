---
id: 587d8249367417b2b2512c3e
title: Client-Side Caching mit helmet.noCache() deaktivieren
challengeType: 2
forumTopicId: 301576
dashedName: disable-client-side-caching-with-helmet-nocache
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Wenn du ein Update für deine Website herausgibst und du möchtest, dass die Nutzer immer die neuere Version herunterladen, kannst du das Caching im Browser des Kunden deaktivieren (oder es versuchen). Es kann auch für die Entwicklung nützlich sein. Die Zwischenspeicherung hat Leistungsvorteile, die du verlieren wirst, daher solltest du diese Option nur nutzen, wenn es wirklich notwendig ist.

# --instructions--

Verwende die `helmet.noCache()`-Methode auf deinem Server.

# --hints--

Die helmet.noCache()-Middleware sollte korrekt eingebaut werden

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'nocache');
      assert.equal(
        data.headers['cache-control'],
        'no-store, no-cache, must-revalidate, proxy-revalidate'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

