---
id: a302f7aae1aa3152a5b413bc
title: 숫자 계승화(Factorialize) 하기
challengeType: 1
forumTopicId: 16013
dashedName: factorialize-a-number
---

# --description--

Return the factorial of the provided integer.

정수 `n`이 주어졌을 때, 계승은 `n`보다 작거나 같은 모든 양수의 곱입니다.

계승은 주로 `n!`으로 표기합니다.

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120`

함수에는 오직 0보다 크거나 같은 정수만 제공됩니다.

# --hints--

`factorialize(5)`는 숫자를 반환해야 합니다.

```js
assert.isNumber(factorialize(5));
```

`factorialize(5)`는 `120`을 반환해야 합니다.

```js
assert.strictEqual(factorialize(5), 120);
```

`factorialize(10)`는 `3628800`을 반환해야 합니다.

```js
assert.strictEqual(factorialize(10), 3628800);
```

`factorialize(20)`는 `2432902008176640000`을 반환해야 합니다.

```js
assert.strictEqual(factorialize(20), 2432902008176640000);
```

`factorialize(0)`는 `1`을 반환해야 합니다.

```js
assert.strictEqual(factorialize(0), 1);
```

# --seed--

## --seed-contents--

```js
function factorialize(num) {
  return num;
}

factorialize(5);
```

# --solutions--

```js
function factorialize(num) {
  return num < 1 ? 1 : num * factorialize(num - 1);
}

factorialize(5);
```
