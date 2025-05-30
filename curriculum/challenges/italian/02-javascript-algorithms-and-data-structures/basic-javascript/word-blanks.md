---
id: 56533eb9ac21ba0edf2244bb
title: Parole mancanti
challengeType: 1
forumTopicId: 18377
dashedName: word-blanks
---

# --description--

You are provided sentences with some missing words, like nouns, verbs, adjectives and adverbs. You then fill in the missing pieces with words of your choice in a way that the completed sentence makes sense.

Considera questa frase:

```md
It was really ____, and we ____ ourselves ____.
```

Questa frase ha tre parti mancanti - un aggettivo, un verbo e un avverbio, e possiamo aggiungere parole di nostra scelta per completarla. Possiamo quindi assegnare la frase completata a una variabile come segue:

```js
const sentence = "It was really " + "hot" + ", and we " + "laughed" + " ourselves " + "silly" + ".";
```

# --instructions--

In questa sfida, ti forniremo un sostantivo, un verbo, un aggettivo e un avverbio. Dovrai formare una frase completa utilizzando parole di tua scelta, insieme con le parole che ti forniremo.

Dovrai usare l'operatore di concatenazione delle stringhe `+` per creare una nuova stringa, utilizzando le variabili fornite: `myNoun`, `myAdjective`, `myVerb` e `myAdverb`. Assegnerai quindi la stringa costruita alla variabile `wordBlanks`. Non dovrai cambiare le parole assegnate alle variabili.

Nella tua stringa dovrai anche tenere conto degli spazi, in modo che la frase finale abbia degli spazi tra tutte le parole. Il risultato dovrebbe essere una frase completa.

# --hints--

`wordBlanks` dovrebbe essere una stringa.

```js
assert(typeof wordBlanks === 'string');
```

Non dovresti modificare i valori assegnati a `myNoun`, `myVerb`, `myAdjective` o `myAdverb`.

```js
assert(
  myNoun === 'dog' &&
    myVerb === 'ran' &&
    myAdjective === 'big' &&
    myAdverb === 'quickly'
);
```

Non dovresti usare direttamente i valori `dog`, `ran`, `big` o `quickly` per creare `wordBlanks`.

```js
const newCode = removeAssignments(__helpers.removeJSComments(code));
assert(
  !/dog/.test(newCode) &&
    !/ran/.test(newCode) &&
    !/big/.test(newCode) &&
    !/quickly/.test(newCode)
);
```

`wordBlanks` dovrebbe contenere tutte le parole assegnate alle variabili `myNoun`, `myVerb`, `myAdjective` e `myAdverb` separate da caratteri che non siano parole (e da eventuali parole di tua scelta).

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
