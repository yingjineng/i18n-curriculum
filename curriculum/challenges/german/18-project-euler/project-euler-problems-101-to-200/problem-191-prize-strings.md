---
id: 5900f42b1000cf542c50ff3e
title: 'Problem 191: Prämien-Strings'
challengeType: 1
forumTopicId: 301829
dashedName: problem-191-prize-strings
---

# --description--

Eine bestimmte Schule bietet Kindern mit guter Anwesenheit und Pünktlichkeit Geldprämien an. Sie verlieren ihre Prämie jedoch, wenn sie für drei aufeinanderfolgende Tage abwesend sind, oder sich mehr als einmal verspäten.

Während eines n-tägigen Zeitraums wird ein – aus den Buchstaben L (late), O (on time) und A (abwesend) bestehender – dreigliedriger String gebildet.

Obwohl es einundachtzig Dreierketten für einen Zeitraum von 4 Tagen gibt, die gebildet werden können, würden genau dreiundvierzig Ketten zu einem Preis führen:

```markup
OOOO OOOA OOOL OOAO OOAA OOAL OOLO OOLA OAOO OAOA
OAOL OAAO OAAL OALO OALA OLOO OLOA OLAO OLAA AOOO
AOOA AOOL AOAO AOAA AOAL AOLO AOLA AAOO AAOA AAOL
AALO AALA ALOO ALOA ALAO ALAA LOOO LOOA LOAO LOAA
LAOO LAOA LAAO
```

Wie viele „Prämien“-Strings würden über einen dreißigtägigen Zeitraum entstehen?

# --hints--

`prizeStrings()` sollte `1918080160` zurückgeben.

```js
assert.strictEqual(prizeStrings(), 1918080160);
```

# --seed--

## --seed-contents--

```js
function prizeStrings() {

  return true;
}

prizeStrings();
```

# --solutions--

```js
// solution required
```
