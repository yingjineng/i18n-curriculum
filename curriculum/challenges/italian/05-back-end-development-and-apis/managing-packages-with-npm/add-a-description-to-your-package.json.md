---
id: 587d7fb3367417b2b2512bfc
title: Aggiungere una descrizione al tuo package.json
challengeType: 2
forumTopicId: 301522
dashedName: add-a-description-to-your-package-json
---

# --description--

The next part of a good package.json file is the `description` field; where a short, but informative description about your project belongs.

Se un giorno avessi intenzione di pubblicare un pacchetto su npm, questa è la stringa che dovrebbe vendere la tua idea all'utente quando decide se installare o meno il pacchetto. Tuttavia, questo non è l'unico caso di utilizzo per la descrizione: essa è un ottimo modo per riassumere ciò che un progetto fa. È altrettanto importante in qualsiasi progetto Node.js per aiutare altri sviluppatori, futuri manutentori o anche il futuro te stesso a comprendere il progetto velocemente.

Indipendentemente da ciò che prevedi per il vostro progetto, una descrizione è sicuramente consigliata. Ecco un esempio:

```json
"description": "A project that does something awesome",
```

# --instructions--

Aggiungi una `description` al file package.json del tuo progetto.

**Nota:** Ricordati di usare le virgolette doppie (") per i nomi di campo e le virgole (,) per separare i campi.

# --hints--

package.json dovrebbe avere una chiave "description" valida

```js
  $.get(code + '/_api/package.json').then(
    (data) => {
      var packJson = JSON.parse(data);
      assert(packJson.description, '"description" is missing');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

