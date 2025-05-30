---
id: 5900f3c51000cf542c50fed8
title: 'Problema 87: Potencias y triples primos'
challengeType: 1
forumTopicId: 302201
dashedName: problem-87-prime-power-triples
---

# --description--

El número más pequeño expresable como la suma de un cuadrado primo, un cubo primo y una cuarta potencia prima es `28`. De hecho, hay exactamente cuatro números por debajo de cincuenta que se pueden expresar de tal manera:

<div style='margin-left: 4em;'>
  28 = 2<sup>2</sup> + 2<sup>3</sup> + 2<sup>4</sup><br>
  33 = 3<sup>2</sup> + 2<sup>3</sup> + 2<sup>4</sup><br>
  49 = 5<sup>2</sup> + 2<sup>3</sup> + 2<sup>4</sup><br>
  47 = 2<sup>2</sup> + 3<sup>3</sup> + 2<sup>4</sup>
</div><br>

¿Cuántos números por debajo de `n` se pueden expresar como la suma de un cuadrado primo, un cubo primo y una cuarta potencia prima?

# --hints--

`primePowerTriples(50)` debe devolver un número.

```js
assert(typeof primePowerTriples(50) === 'number');
```

`primePowerTriples(50)` debe devolver `4`.

```js
assert.strictEqual(primePowerTriples(50), 4);
```

`primePowerTriples(10035)` debe devolver `684`.

```js
assert.strictEqual(primePowerTriples(10035), 684);
```

`primePowerTriples(500000)` debe devolver `18899`.

```js
assert.strictEqual(primePowerTriples(500000), 18899);
```

`primePowerTriples(5000000)` debe devolver `138932`.

```js
assert.strictEqual(primePowerTriples(5000000), 138932);
```

`primePowerTriples(50000000)` debe devolver `1097343`.

```js
assert.strictEqual(primePowerTriples(50000000), 1097343);
```

# --seed--

## --seed-contents--

```js
function primePowerTriples(n) {

  return true;
}

primePowerTriples(50);
```

# --solutions--

```js
function primePowerTriples(n) {
  function getSievePrimes(max) {
    const primes = [];
    const primesMap = new Array(max).fill(true);
    primesMap[0] = false;
    primesMap[1] = false;

    for (let i = 2; i <= max; i += 2) {
      if (primesMap[i]) {
        primes.push(i);
        for (let j = i * i; j <= max; j = j + i) {
          primesMap[j] = false;
        }
      }
      if (i === 2) {
        i = 1;
      }
    }
    return primes;
  }

  function getPowersSummed(numbers, powers, limit, curSum) {
    if (curSum >= limit) {
      return [];
    } else if (powers.length === 0) {
      return [curSum];
    }

    const powersSummed = [];

    const curPower = powers[0];
    const powersLeft = powers.slice(1);
    for (let i = 0; i < numbers.length; i++) {
      const curNumber = numbers[i];
      const nextSum = curSum + curNumber ** curPower;
      if (nextSum >= limit) {
        return powersSummed;
      }
      const result = getPowersSummed(
        numbers,
        powersLeft,
        limit,
        curSum + curNumber ** curPower
      );
      powersSummed.push(...result);
    }
    return powersSummed;
  }

  const maximumBaseNumber = Math.floor(Math.sqrt(n - 2 ** 3 - 2 ** 4)) + 1;
  const primes = getSievePrimes(maximumBaseNumber);
  const uniqueSums = new Set(getPowersSummed(primes, [2, 3, 4], n, 0));

  return uniqueSums.size;
}
```
