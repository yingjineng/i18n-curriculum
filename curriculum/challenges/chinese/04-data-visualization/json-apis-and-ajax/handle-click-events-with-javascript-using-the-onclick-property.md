---
id: 587d7fad367417b2b2512be1
title: 使用 onclick 属性处理点击事件
challengeType: 6
forumTopicId: 301503
dashedName: handle-click-events-with-javascript-using-the-onclick-property
---

# --description--

You want your code to execute only once your page has finished loading. For that purpose, you can attach a JavaScript event to the document called `DOMContentLoaded`. Here's the code that does this:

```js
document.addEventListener('DOMContentLoaded', function () {});
```

你可以在`DOMContentLoaded`函数内部添加事件处理方法。 你可以通过添加以下代码来添加 `onclick` 事件处理器，当用户点击 id 为`#getMessage` 的元素时会触发事件：

```js
document.getElementById('getMessage').onclick = function () {};
```

# --instructions--

在`DOMContentLoaded`函数内为 id 为`getMessage`的元素添加一个 click 事件处理器。

# --hints--

你的代码应该用 `document.getElementById` 方法来选择 id 为 `getMessage` 的元素。

```js
assert.match(code, /document\s*\.getElementById\(\s*('|")getMessage\1\s*\)/g);
```

你的代码应该添加`onclick`事件处理器。

```js
assert.isFunction(document.getElementById('getMessage').onclick);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    // Add your code below this line
    // Add your code above this line
  });
</script>

<style>
  body {
    text-align: center;
    font-family: 'Helvetica', sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0f5897;
    border: 1px solid #0f5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p class="message box">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```

# --solutions--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    // Add your code below this line
    document.getElementById('getMessage').onclick = function () {};
    // Add your code above this line
  });
</script>

<style>
  body {
    text-align: center;
    font-family: 'Helvetica', sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0f5897;
    border: 1px solid #0f5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p class="message box">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```
