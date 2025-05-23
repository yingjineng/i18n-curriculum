---
id: 587d8248367417b2b2512c3b
title: Verhindern, dass IE nicht vertrauenswürdigen HTML-Code mit helmet.ieNoOpen() öffnet
challengeType: 2
forumTopicId: 301584
dashedName: prevent-ie-from-opening-untrusted-html-with-helmet-ienoopen
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Einige Webanwendungen werden nicht vertrauenswürdigen HTML zum Download zur Verfügung stellen. Einige Versionen des Internet Explorer öffnen diese HTML-Dateien standardmäßig im Kontext Ihrer Website. Das bedeutet, dass eine nicht vertrauenswürdige HTML-Seite im Zusammenhang mit deinen Seiten unerwünschte Dinge tun könnte. Diese Middleware setzt den X-Download-Options-Header auf noopen. Dadurch werden IE-Benutzer daran gehindert, Downloads im Kontext der vertrauenswürdigen Website auszuführen.

# --instructions--

Verwende die `helmet.ieNoOpen()`-Methode auf deinem Server.

# --hints--

Die helmet.ieNoOpen()-Middleware sollte korrekt eingebaut werden

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(data.appStack, 'ienoopen');
      assert.equal(data.headers['x-download-options'], 'noopen');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

