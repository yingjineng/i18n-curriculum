---
id: ac6993d51946422351508a41
title: Troncare una stringa
challengeType: 1
forumTopicId: 16089
dashedName: truncate-a-string
---

# --description--

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a `...` ending.

# --hints--

`truncateString("A-tisket a-tasket A green and yellow basket", 8)` dovrebbe restituire la stringa `A-tisket...`.

```js
assert.strictEqual(
  truncateString('A-tisket a-tasket A green and yellow basket', 8),
  'A-tisket...'
);
```

`truncateString("Peter Piper picked a peck of pickled peppers", 11)` dovrebbe restituire la stringa `Peter Piper...`.

```js
assert.strictEqual(
  truncateString('Peter Piper picked a peck of pickled peppers', 11),
  'Peter Piper...'
);
```

`truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length)` dovrebbe restituire la stringa `A-tisket a-tasket A green and yellow basket`.

```js
assert.strictEqual(
  truncateString(
    'A-tisket a-tasket A green and yellow basket',
    'A-tisket a-tasket A green and yellow basket'.length
  ),
  'A-tisket a-tasket A green and yellow basket'
);
```

`truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2)` dovrebbe restituire la stringa `A-tisket a-tasket A green and yellow basket`.

```js
assert.strictEqual(
  truncateString(
    'A-tisket a-tasket A green and yellow basket',
    'A-tisket a-tasket A green and yellow basket'.length + 2
  ),
  'A-tisket a-tasket A green and yellow basket'
);
```

`truncateString("A-", 1)` dovrebbe restituire la stringa `A...`.

```js
assert.strictEqual(truncateString('A-', 1), 'A...');
```

`truncateString("Absolutely Longer", 2)` dovrebbe restituire la stringa `Ab...`.

```js
assert.strictEqual(truncateString('Absolutely Longer', 2), 'Ab...');
```

# --seed--

## --seed-contents--

```js
function truncateString(str, num) {
  return str;
}

truncateString('A-tisket a-tasket A green and yellow basket', 8);
```

# --solutions--

```js
function truncateString(str, num) {
  if (num >= str.length) {
    return str;
  }

  return str.slice(0, num) + '...';
}

truncateString('A-tisket a-tasket A green and yellow basket', 8);
```
