---
id: 5900f3e61000cf542c50fef9
title: 'Problem 122: Effiziente Exponentiation'
challengeType: 1
forumTopicId: 301749
dashedName: problem-122-efficient-exponentiation
---

# --description--

Die wohl einfachste Art, $n^{15}$ zu berechnen, erfordert vierzehn Multiplikationen:

$$n × n × \ldots × n = n^{15}$$

Mit einer "binären" Methode kann man sie jedoch in sechs Multiplikationen berechnen:

$$\begin{align}   & n × n = n^2\\\\
  & n^2 × n^2 = n^4\\\\   & n^4 × n^4 = n^8\\\\
  & n^8 × n^4 = n^{12}\\\\   & n^{12} × n^2 = n^{14}\\\\
  & n^{14} × n = n^{15} \end{align}$$

Es ist jedoch möglich, ihn in nur fünf Multiplikationen zu berechnen:

$$\begin{align}   & n × n = n^2\\\\
  & n^2 × n = n^3\\\\   & n^3 × n^3 = n^6\\\\
  & n^6 × n^6 = n^{12}\\\\ & n^{12} × n^3 = n^{15} \end{align}$$

Wir definieren $m(k)$ als die minimale Anzahl von Multiplikationen zur Berechnung von $n^k$; zum Beispiel $m(15) = 5$.

Für $1 ≤ k ≤ 200$, finde $\sum{m(k)}$.

# --hints--

`efficientExponentiation()` sollte `1582` zurückgeben.

```js
assert.strictEqual(efficientExponentiation(), 1582);
```

# --seed--

## --seed-contents--

```js
function efficientExponentiation() {

  return true;
}

efficientExponentiation();
```

# --solutions--

```js
// solution required
```
