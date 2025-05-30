---
id: 58a25bcef9fc0f352b528e7c
title: Capire la crittografia hash BCrypt
challengeType: 2
forumTopicId: 301586
dashedName: understand-bcrypt-hashes
---

# --description--

For the following challenges, you will be working with a new starter project that is different from the previous one. You can find the new starter project to clone on <a href="https://github.com/freeCodeCamp/boilerplate-bcrypt/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

Gli hash BCrypt sono molto sicuri. Un hash è fondamentalmente un'impronta digitale dei dati originali, sempre unica. Questo si ottiene inserendo i dati originali in un algoritmo e restituendo un risultato di lunghezza fissa. Per complicare ulteriormente questo processo e renderlo più sicuro, puoi anche aggiungere un *salt* al tuo hash. Aggiungere un salt al tuo hash comporta l'aggiunta di dati casuali ai dati originali prima del processo di hashing che rende ancora più difficile crackare l'hash.

Gli hash BCrypt appariranno sempre come `$2a$13$ZyprE5MRw2Q3WpNOGZWGbeG7ADUre1Q8QO.uUUtcbqloU0yvzavOm` che ha una struttura. Il primo pezzettino di dati `$2a` sta definendo che tipo di algoritmo di hash è stato utilizzato. La porzione successiva `$13` definisce il *costo*. Il costo è più o meno quanto potere computazionale è necessario per calcolare l'hash. È su una scala logaritmica di 2^costo e determina quante volte i dati vengono messi attraverso l'algoritmo di hashing. Per esempio, al costo di 10 puoi fare l'hash di 10 password per secondo su un computer medio, però a un costo di 15 servono 3 secondi per un hash... e per esagerare, a un costo di 31 servirebbero più giorni per completare un hash. Un costo di 12 è considerato molto sicuro in questo momento. L'ultima porzione del tuo hash `$ZyprE5MRw2Q3WpNOGZWGbeG7ADUre1Q8QO.uUUtcbqloU0yvzavOm`, sembra una grande stringa di numeri, punti e lettere, ma sono in realtà due pezzi separati di informazioni. I primi 22 caratteri sono il salt in chiaro, e il resto è la password crittografata!

# --instructions--

Aggiungi tutto il tuo codice per queste lezioni nel file `server.js` in mezzo al codice di partenza che ti abbiamo fornito. Non modificare o eliminare il codice che abbiamo aggiunto per te.

BCrypt è già stato aggiunto come dipendenza, quindi richiedilo come `bcrypt` nel tuo server.

Invia la tua pagina quando pensi di averlo fatto correttamente.

# --hints--

BCrypt dovrebbe essere una dipendenza.

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert.property(
        packJson.dependencies,
        'bcrypt',
        'Your project should list "bcrypt" as a dependency'
      );
    },
    (xhr) => {
      throw new Error(xhr.statusText);
    }
  );
```

BCrypt dovrebbe essere richiesto correttamente.

```js
  $.get(code + '/_api/server.js').then(
    (data) => {
      assert.match(
        data,
        /bcrypt.*=.*require.*('|")bcrypt('|")/gi,
        'You should correctly require and instantiate socket.io as io.'
      );
    },
    (xhr) => {
      throw new Error(xhr.statusText);
    }
  );
```

