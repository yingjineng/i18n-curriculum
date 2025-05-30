---
id: bd7123c9c450eddfaeb5bdef
title: 使用方括號查找字符串中的第 N 個字符
challengeType: 1
forumTopicId: 18343
dashedName: use-bracket-notation-to-find-the-nth-character-in-a-string
---

# --description--

You can also use <dfn>bracket notation</dfn> to get the character at other positions within a string.

請記住，程序是從 `0` 開始計數，所以獲取第一個字符實際上是第零個字符串。

示例：

```js
const firstName = "Ada";
const secondLetterOfFirstName = firstName[1];
```

`secondLetterOfFirstName` 值應該爲字符串 `d`。

# --instructions--

讓我們使用方括號，把 `lastName` 變量的第三個字符賦值給 `thirdLetterOfLastName`。

**提示：** 如果卡住了，請嘗試查看上面的示例。

# --hints--

`thirdLetterOfLastName` 變量值應該爲 `v` 。

```js
assert(thirdLetterOfLastName === 'v');
```

應該使用方括號表示法。

```js
assert(__helpers.removeJSComments(code).match(/thirdLetterOfLastName\s*=\s*lastName\s*\[\s*\d\s*\]/));
```

# --seed--

## --after-user-code--

```js
(function(v){return v;})(thirdLetterOfLastName);
```

## --seed-contents--

```js
// Setup
const lastName = "Lovelace";

// Only change code below this line
const thirdLetterOfLastName = lastName; // Change this line
```

# --solutions--

```js
const lastName = "Lovelace";
const thirdLetterOfLastName = lastName[2];
```
