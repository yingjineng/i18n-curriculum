---
id: 5900f4f41000cf542c510007
title: 'Problem 392: Vernetzer Einheitskreis'
challengeType: 1
forumTopicId: 302057
dashedName: problem-392-enmeshed-unit-circle
---

# --description--

Ein geradliniges Gitter ist ein orthogonales Gitter, bei dem die Abstände zwischen den Gitterlinien nicht äquidistant sein müssen.

Ein Beispiel für ein solches Gitter ist logarithmisches Millimeterpapier.

Betrachte die geradlinigen Gitter im kartesischen Koordinatensystem mit den folgenden Eigenschaften:

- Die Gitterlinien verlaufen parallel zu den Achsen des kartesischen Koordinatensystems.
- Es gibt $N + 2$ vertikale und $N + 2$ horizontale Gitterlinien. Folglich gibt es $(N + 1) \times (N + 1)$ rechteckige Zellen.
- Die Gleichungen der beiden äußeren vertikalen Gitterlinien sind $x = -1$ und $x = 1$.
- Die Gleichungen der beiden äußeren horizontalen Gitterlinien sind $y = -1$ und $y = 1$.
- Die Gitterzellen sind rot gefärbt, wenn sie sich mit dem Einheitskreis überschneiden, ansonsten schwarz.

Für dieses Problem möchten wir, dass du die Positionen der verbleibenden $N$ inneren horizontalen und $N$ inneren vertikalen Gitterlinien so finden, dass die von den roten Zellen belegte Fläche minimiert wird.

z.B. hier ist ein Bild der Lösung für $N = 10$:

<img alt="die Lösung für N = 10" src="https://cdn.freecodecamp.org/curriculum/project-euler/enmeshed-unit-circle.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Die von den roten Zellen eingenommene Fläche beträgt für $N = 10$ gerundet auf 10 Nachkommastellen 3,3469640797.

Finde die Positionen für $N = 400$. Gib als Antwort die Fläche an, die von den roten Zellen eingenommen wird, gerundet auf 10 Stellen hinter dem Komma.

# --hints--

`enmeshedUnitCircle()` sollte `3.1486734435` zurückgeben.

```js
assert.strictEqual(enmeshedUnitCircle(), 3.1486734435);
```

# --seed--

## --seed-contents--

```js
function enmeshedUnitCircle() {

  return true;
}

enmeshedUnitCircle();
```

# --solutions--

```js
// solution required
```
