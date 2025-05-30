---
id: 5900f3ea1000cf542c50fefd
title: 'Problem 126: Cuboid layers'
challengeType: 1
forumTopicId: 301753
dashedName: problem-126-cuboid-layers
---

# --description--

El número minimo de cubos para cubrir cada cara visible de un cuboide que mide 3 x 2 x 1 es veintidós.

<img alt="3x2x1 cuboid covered by twenty-two 1x1x1 cubes" src="https://cdn.freecodecamp.org/curriculum/project-euler/cuboid-layers.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Si añadimos una segunda capa a este solido necesitaría 46 cubos para cubrir cada cara visible, la terera capa necesitaría 78 cubos, y la cuarta necesitaría 108 cubos para cubrir cada cara visible.

However, the first layer on a cuboid measuring 5 x 1 x 1 also requires twenty-two cubes; similarly, the first layer on cuboids measuring 5 x 3 x 1, 7 x 2 x 1, and 11 x 1 x 1 all contain forty-six cubes.

We shall define $C(n)$ to represent the number of cuboids that contain $n$ cubes in one of its layers. So $C(22) = 2$, $C(46) = 4$, $C(78) = 5$, and $C(118) = 8$.

It turns out that 154 is the least value of $n$ for which $C(n) = 10$.

Find the least value of $n$ for which $C(n) = 1000$.

# --hints--

`cuboidLayers()` debería devolver `18522`.

```js
assert.strictEqual(cuboidLayers(), 18522);
```

# --seed--

## --seed-contents--

```js
function cuboidLayers() {

  return true;
}

cuboidLayers();
```

# --solutions--

```js
// solution required
```
