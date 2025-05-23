---
id: 587d7fb6367417b2b2512c07
title: Erstelle ein Modell
challengeType: 2
forumTopicId: 301535
dashedName: create-a-model
---

# --description--

**C**RUD Part I - CREATE

Zunächst benötigen wir ein Schema. Jedes Schema wird einer MongoDB-Sammlung zugeordnet. Sie definiert die Form der Dokumente innerhalb dieser Sammlung. Schemata sind Grundbausteine für Modelle. Sie können miteinander verschachtelt werden, um komplexe Modelle zu erzeugen – in diesem Fall aber halten wir es einfach. Mit einem Modell kannst du Instanzen deiner Objekte, sogenannte Dokumente, erstellen.

In servers, the interactions with the database happen in handler functions. Diese Funktionen werden ausgeführt, wenn ein Ereignis eintritt (z.B. wenn jemand auf einen API-Endpunkt zugreift). We'll follow the same approach in these exercises. Die `done()`-Funktion ist ein Callback über welchen uns mittgeteilt wird, dass wir nach Abschluss einer asynchronen Operation (Einfügen, Suchen, Aktualisieren, Löschen) fortfahren können. Sie folgt hierbei der Node-Konvention und sollte mit `done(null, data)` bei Erfolg oder `done(err)` bei einem Fehler aufgerufen werden.

Achtung – bei Interaktionen mit entfernten Diensten können Fehler auftreten!

```js
/* Example */

const someFunc = function(done) {
  //... do something (risky) ...
  if (error) return done(error);
  done(null, result);
};
```

# --instructions--

Erstelle ein Personen-Schema namens `personSchema` mit der folgenden Form:

* A required `name` field of type `String`
* Ein `age`-Feld mit `Number`-Datentyp
* Ein `favoriteFoods`-Feld des Typs `[String]`

Verwende die Mongoose-Basis-Schema-Typen. Wenn du möchtest, kannst du auch weitere Felder hinzufügen. Verwende hierzu einfache Validatoren – bspw. „required“ oder „unique“ – und lege Standardwerte fest. Schau dir hierzu unseren <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">Mongoose-Artikel</a> an.

Erstelle nun ein Modell aus dem `personSchema` und weise es der vorhandenen Variable `Person` zu.

# --hints--

Du solltest erfolgreich eine Instanz nach einem Mongoose-Schema erstellt haben

```js
  $.post(code + '/_api/mongoose-model', {
    name: 'Mike',
    age: 28,
    favoriteFoods: ['pizza', 'cheese']
  }).then(
    (data) => {
      assert.equal(data.name, 'Mike', '"model.name" is not what expected');
      assert.equal(data.age, '28', '"model.age" is not what expected');
      assert.isArray(
        data.favoriteFoods,
        '"model.favoriteFoods" is not an Array'
      );
      assert.include(
        data.favoriteFoods,
        'pizza',
        '"model.favoriteFoods" does not include the expected items'
      );
      assert.include(
        data.favoriteFoods,
        'cheese',
        '"model.favoriteFoods" does not include the expected items'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

