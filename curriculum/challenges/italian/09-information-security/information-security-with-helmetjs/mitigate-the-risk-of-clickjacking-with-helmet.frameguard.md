---
id: 587d8247367417b2b2512c38
title: Mitigare il rischio di Clickjacking con helmet.frameguard()
challengeType: 2
forumTopicId: 301582
dashedName: mitigate-the-risk-of-clickjacking-with-helmet-frameguard
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

La tua pagina potrebbe essere inserita in un `<frame>` o `<iframe>` senza il tuo consenso. Questo tra le altre cose può portare ad attacchi di clickjacking ("dirottamento dei click"). Il clickjacking è una tecnica per indurre un utente a interagire con una pagina diversa da quella che l'utente pensa che sia. Questo può essere ottenuto eseguendo la tua pagina in un contesto dannoso, per mezzo di iframing. In questo contesto, un hacker può mettere un livello nascosto sulla tua pagina. I pulsanti nascosti possono essere usati per eseguire script dannosi. Questo middleware imposta l'intestazione X-Frame-Options. Limita chi può mettere il tuo sito in un iframe. Ha tre modalità: DENY, SAMEORIGIN, e ALLOW-FROM.

Non abbiamo bisogno che la nostra app sia in un iframe.

# --instructions--

Usa `helmet.frameguard()` passando `{action: 'deny'}` con l'oggetto di configurazione.

# --hints--

Il middleware helmet.frameguard() deve essere montato correttamente

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(
        data.appStack,
        'frameguard',
        'helmet.frameguard() middleware is not mounted correctly'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

helmet.frameguard() 'action' dovrebbe essere impostato su 'DENY'

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.property(data.headers, 'x-frame-options');
      assert.equal(data.headers['x-frame-options'], 'DENY');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

