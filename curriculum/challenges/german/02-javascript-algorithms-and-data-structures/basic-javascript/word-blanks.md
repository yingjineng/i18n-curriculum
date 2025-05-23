---
id: 56533eb9ac21ba0edf2244bb
title: Lückentext (Word Blanks)
challengeType: 1
forumTopicId: 18377
dashedName: word-blanks
---

# --description--

You are provided sentences with some missing words, like nouns, verbs, adjectives and adverbs. You then fill in the missing pieces with words of your choice in a way that the completed sentence makes sense.

Betrachte diesen Satz:

```md
It was really ____, and we ____ ourselves ____.
```

In diesem Satz fehlen drei Teile - ein Adjektiv, ein Verb und ein Adverb - und wir können Wörter unserer Wahl hinzufügen, um ihn zu vervollständigen. Anschließend können wir den vervollständigten Satz wie folgt einer Variable zuordnen:

```js
const sentence = "It was really " + "hot" + ", and we " + "laughed" + " ourselves " + "silly" + ".";
```

# --instructions--

Bei dieser Aufgabe stellen wir dir ein Nomen, ein Verb, ein Adjektiv sowie ein Adverb zur Verfügung. Du musst einen vollständigen Satz mit Wörtern deiner Wahl und den von uns vorgegebenen Wörtern bilden.

Du musst den String-Verkettungsoperator `+` verwenden, um einen neuen String zu erstellen, indem du die angegebenen Variablen verwendest: `myNoun`, `myAdjective`, `myVerb` und `myAdverb`. Anschließend musst du den erstellten String der Variable `wordBlanks` zuweisen. Du solltest die Wörter, die den Variablen zugeordnet sind, nicht ändern.

Du musst auch die Leerzeichen in deinem String berücksichtigen, damit der letzte Satz Leerzeichen zwischen allen Wörtern hat. Das Ergebnis sollte einen vollständigen Satz darstellen.

# --hints--

`wordBlanks` sollte ein String sein.

```js
assert(typeof wordBlanks === 'string');
```

Du solltest die Werte von `myNoun`, `myVerb`, `myAdjective` oder `myAdverb` nicht verändern.

```js
assert(
  myNoun === 'dog' &&
    myVerb === 'ran' &&
    myAdjective === 'big' &&
    myAdverb === 'quickly'
);
```

Du solltest die Werte `dog`, `ran`, `big` oder `quickly` nicht direkt verwenden, um `wordBlanks` zu erstellen.

```js
const newCode = removeAssignments(__helpers.removeJSComments(code));
assert(
  !/dog/.test(newCode) &&
    !/ran/.test(newCode) &&
    !/big/.test(newCode) &&
    !/quickly/.test(newCode)
);
```

`wordBlanks` sollte alle Wörter enthalten, die den Variablen `myNoun`, `myVerb`, `myAdjective` und `myAdverb` zugeordnet sind, getrennt durch Nicht-Wort-Zeichen (und zusätzliche Wörter deiner Wahl).

```js
assert(
  /\bdog\b/.test(wordBlanks) &&
    /\bbig\b/.test(wordBlanks) &&
    /\bran\b/.test(wordBlanks) &&
    /\bquickly\b/.test(wordBlanks)
);
```

# --seed--

## --after-user-code--

```js
const removeAssignments = str => str
  .replace(/myNoun\s*=\s*["']dog["']/g, '')
  .replace(/myAdjective\s*=\s*["']big["']/g, '')
  .replace(/myVerb\s*=\s*["']ran["']/g, '')
  .replace(/myAdverb\s*=\s*["']quickly["']/g, '');
```

## --seed-contents--

```js
const myNoun = "dog";
const myAdjective = "big";
const myVerb = "ran";
const myAdverb = "quickly";

// Only change code below this line
const wordBlanks = ""; // Change this line
// Only change code above this line
```

# --solutions--

```js
const myNoun = "dog";
const myAdjective = "big";
const myVerb = "ran";
const myAdverb = "quickly";

let wordBlanks = "Once there was a " + myNoun + " which was very " + myAdjective + ". ";
wordBlanks += "It " + myVerb + " " + myAdverb + " around the yard.";
```
