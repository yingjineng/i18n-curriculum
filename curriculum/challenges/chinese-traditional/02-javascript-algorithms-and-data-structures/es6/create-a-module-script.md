---
id: 5cddbfd622f1a59093ec611d
title: 創建一個模塊腳本
challengeType: 6
forumTopicId: 301198
dashedName: create-a-module-script
---

# --description--

JavaScript started with a small role to play on an otherwise mostly HTML web. Today, it’s huge, and some websites are built almost entirely with JavaScript. In order to make JavaScript more modular, clean, and maintainable; ES6 introduced a way to easily share code among JavaScript files. This involves exporting parts of a file for use in one or more other files, and importing the parts you need, where you need them. In order to take advantage of this functionality, you need to create a script in your HTML document with a `type` of `module`. Here’s an example:

```html
<script type="module" src="filename.js"></script>
```

使用了 `module` 類型的腳本可以使用 `import` 和 `export` 特性（接下來的挑戰會介紹）。

# --instructions--

給 HTML 文檔添加 `module` 類型的腳本，指定源文件爲 `index.js`。

# --hints--

應該創建一個 `script` 標籤。

```js
assert(__helpers.removeJSComments(code).match(/<\s*script[^>]*>\s*<\/\s*script\s*>/g));
```

`script` 標籤應該有一個值爲 `module` 的 `type` 屬性。

```js
assert(
  __helpers.removeJSComments(code).match(
    /<\s*script\s+[^t]*type\s*=\s*('|")module\1[^>]*>\s*<\/\s*script\s*>/g
  )
);
```

`script` 標籤的 `src` 屬性應該爲 `index.js`。

```js
assert(
  __helpers.removeJSComments(code).match(
    /<\s*script\s+[^s]*src\s*=\s*('|")index\.js\1[^>]*>\s*<\/\s*script\s*>/g
  )
);
```

# --seed--

## --seed-contents--

```html
<html>
  <body>
    <!-- Only change code below this line -->

    <!-- Only change code above this line -->
  </body>
</html>
```

# --solutions--

```html
<html>
  <body>
    <script type="module" src="index.js"></script>
  </body>
</html>
```
