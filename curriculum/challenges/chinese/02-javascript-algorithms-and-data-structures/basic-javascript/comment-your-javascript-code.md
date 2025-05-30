---
id: bd7123c9c441eddfaeb4bdef
title: 给代码添加注释
challengeType: 1
forumTopicId: 16783
dashedName: comment-your-javascript-code
---

# --description--

Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to other people who will later need to figure out what that code does.

JavaScript有两种写注释的方法。

使用 `//` 注释掉当前行的代码。 这是一个行内注释：

```js
// This is an in-line comment.
```

你也可以使用多行注释来注释你的代码，使用 `/*` 开始， `*/` 结束。 这是一个多行注释：

```js
/* This is a
multi-line comment */
```

**最佳实践**当你写代码的时候，你应该时不时的添加注释来解释你写的代码的作用。 适当的注释能让别人*和*你未来的自己更容易看懂代码。

# --instructions--

尝试创建这两种类型的注释。

# --hints--

创建一个 `//` 样式的注释，被注释的文本至少要包含 5 个字符。

```js
assert(code.match(/(\/\/)...../g));
```

创建一个 `/* */` 样式的注释，被注释的文本至少要包含 5 个字符。

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
