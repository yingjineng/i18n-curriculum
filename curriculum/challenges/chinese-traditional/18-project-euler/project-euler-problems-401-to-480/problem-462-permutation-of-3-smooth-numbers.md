---
id: 5900f53b1000cf542c51004d
title: '問題462：3個平滑數的排列'
challengeType: 1
forumTopicId: 302137
dashedName: problem-462-permutation-of-3-smooth-numbers
---

# --description--

A 3-smooth number is an integer which has no prime factor larger than 3. For an integer $N$, we define $S(N)$ as the set of 3-smooth numbers less than or equal to $N$. For example, $S(20) = \\{1, 2, 3, 4, 6, 8, 9, 12, 16, 18\\}$.

We define $F(N)$ as the number of permutations of $S(N)$ in which each element comes after all of its proper divisors.

This is one of the possible permutations for $N = 20$.

-   1, 2, 4, 3, 9, 8, 16, 6, 18, 12.

這不是有效的排列，因爲12在它的除數6之前出現。

-   1,2,4,3,9,8,16,6,18,12。

We can verify that $F(6) = 5$, $F(8) = 9$, $F(20) = 450$ and $F(1000) ≈ 8.8521816557e\\,21$.

Find $F({10}^{18})$. Give your answer as a string in scientific notation rounded to ten digits after the decimal point. When giving your answer, use a lowercase `e` to separate mantissa and exponent. 例如： if the answer is $112\\,233\\,445\\,566\\,778\\,899$ then the answer format would be `1.1223344557e17`.

# --hints--

`permutationOf3SmoothNumbers()` should return a string.

```js
assert.strictEqual(typeof permutationOf3SmoothNumbers(), 'string');
```

`permutationOf3SmoothNumbers()` should return the string `5.5350769703e1512`.

```js
assert.strictEqual(permutationOf3SmoothNumbers(), '5.5350769703e1512');
```

# --seed--

## --seed-contents--

```js
function permutationOf3SmoothNumbers() {

  return true;
}

permutationOf3SmoothNumbers();
```

# --solutions--

```js
// solution required
```
