---
id: bd7123c9c441eddfaeb4bdef
title: 給代碼添加註釋
challengeType: 1
forumTopicId: 16783
dashedName: comment-your-javascript-code
---

# --description--

Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to other people who will later need to figure out what that code does.

JavaScript有兩種寫註釋的方法。

使用 `//` 註釋掉當前行的代碼。 這是一個行內註釋：

```js
// This is an in-line comment.
```

你也可以使用多行註釋來註釋你的代碼，使用 `/*` 開始， `*/` 結束。 這是一個多行註釋：

```js
/* This is a
multi-line comment */
```

**最佳實踐**當你寫代碼的時候，你應該時不時的添加註釋來解釋你寫的代碼的作用。 適當的註釋能讓別人*和*你未來的自己更容易看懂代碼。

# --instructions--

嘗試創建這兩種類型的註釋。

# --hints--

創建一個 `//` 樣式的註釋，被註釋的文本至少要包含 5 個字符。

```js
assert(code.match(/(\/\/)...../g));
```

創建一個 `/* */` 樣式的註釋，被註釋的文本至少要包含 5 個字符。

```js
assert(code.match(/(\/\*)([^\/]{5,})(?=\*\/)/gm));
```

# --seed--

## --seed-contents--

```js

```

# --solutions--

```js
// Fake Comment
/* Another Comment */
```
