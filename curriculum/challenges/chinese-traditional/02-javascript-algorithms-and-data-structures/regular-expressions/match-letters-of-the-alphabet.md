---
id: 587d7db5367417b2b2512b96
title: 匹配字母表中的字母
challengeType: 1
forumTopicId: 301354
dashedName: match-letters-of-the-alphabet
---

# --description--

You saw how you can use <dfn>character sets</dfn> to specify a group of characters to match, but that's a lot of typing when you need to match a large range of characters (for example, every letter in the alphabet). Fortunately, there is a built-in feature that makes this short and simple.

在字符集中，可以使用連字符（`-`）來定義要匹配的字符範圍。

例如，要匹配小寫字母 `a` 到 `e`，你可以使用 `[a-e]`。

```js
let catStr = "cat";
let batStr = "bat";
let matStr = "mat";
let bgRegex = /[a-e]at/;
catStr.match(bgRegex);
batStr.match(bgRegex);
matStr.match(bgRegex);
```

按順序排列，三次 `match` 調用將返回值 `["cat"]`，`["bat"]` 和 `null`。

# --instructions--

匹配字符串 `quoteSample` 中的所有字母。

**注意**：一定要同時匹配大小寫字母。

# --hints--

你的正則表達式 `alphabetRegex` 應該匹配 35 項。

```js
assert(result.length == 35);
```

你的正則表達式 `alphabetRegex` 應該使用全局標識。

```js
assert(alphabetRegex.flags.match(/g/).length == 1);
```

你的正則表達式 `alphabetRegex` 應該使用忽略大小寫標誌。

```js
assert(alphabetRegex.flags.match(/i/).length == 1);
```

# --seed--

## --seed-contents--

```js
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /change/; // Change this line
let result = alphabetRegex; // Change this line
```

# --solutions--

```js
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /[a-z]/gi; // Change this line
let result = quoteSample.match(alphabetRegex); // Change this line
```
