---
id: a26cbbe9ad8655a977e1ceb5
title: 找出字符串中的最長單詞
challengeType: 1
forumTopicId: 16015
dashedName: find-the-longest-word-in-a-string
---

# --description--

Return the length of the longest word in the provided sentence.

函數的返回值應是一個數字。

# --hints--

`findLongestWordLength("The quick brown fox jumped over the lazy dog")` 應返回一個數字。

```js
assert.isNumber(
  findLongestWordLength('The quick brown fox jumped over the lazy dog')
);
```

`findLongestWordLength("The quick brown fox jumped over the lazy dog")` 應返回 `6`。

```js
assert.strictEqual(
  findLongestWordLength('The quick brown fox jumped over the lazy dog'),
  6
);
```

`findLongestWordLength("May the force be with you")` 應返回 `5`。

```js
assert.strictEqual(findLongestWordLength('May the force be with you'), 5);
```

`findLongestWordLength("Google do a barrel roll")` 應返回 `6`。

```js
assert.strictEqual(findLongestWordLength('Google do a barrel roll'), 6);
```

`findLongestWordLength("What is the average airspeed velocity of an unladen swallow")` 應返回 `8`。

```js
assert.strictEqual(
  findLongestWordLength(
    'What is the average airspeed velocity of an unladen swallow'
  ),
  8
);
```

`findLongestWordLength("What if we try a super-long word such as otorhinolaryngology")` 應返回 `19`。

```js
assert.strictEqual(
  findLongestWordLength(
    'What if we try a super-long word such as otorhinolaryngology'
  ),
  19
);
```

# --seed--

## --seed-contents--

```js
function findLongestWordLength(str) {
  return str.length;
}

findLongestWordLength('The quick brown fox jumped over the lazy dog');
```

# --solutions--

```js
function findLongestWordLength(str) {
  return str.split(' ').sort((a, b) => b.length - a.length)[0].length;
}

findLongestWordLength('The quick brown fox jumped over the lazy dog');
```
