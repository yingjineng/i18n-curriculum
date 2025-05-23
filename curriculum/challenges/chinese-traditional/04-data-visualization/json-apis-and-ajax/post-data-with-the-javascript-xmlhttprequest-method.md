---
id: 587d7faf367417b2b2512be9
title: 使用 XMLHttpRequest 方法發送數據
challengeType: 6
forumTopicId: 301504
dashedName: post-data-with-the-javascript-xmlhttprequest-method
---

# --description--

In the previous examples, you received data from an external resource. You can also send data to an external resource, as long as that resource supports AJAX requests and you know the URL.

JavaScript 的 `XMLHttpRequest` 方法也用於將數據發佈到服務器。 這是一個示例：

```js
const xhr = new XMLHttpRequest();
xhr.open('POST', url, true);
xhr.setRequestHeader('Content-Type', 'application/json; charset=UTF-8');
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 201) {
    const serverResponse = JSON.parse(xhr.response);
    document.getElementsByClassName('message')[0].textContent =
      serverResponse.userName + serverResponse.suffix;
  }
};
const body = JSON.stringify({ userName: userName, suffix: ' loves cats!' });
xhr.send(body);
```

你之前已經見過這些方法。 在這裏，`open` 方法將請求初始化爲對外部資源的給定 URL 的 `POST`，並傳遞 `true` 作爲第三個參數——表示以異步方式執行該操作。

`setRequestHeader` 方法設置了 HTTP 請求標頭的值，包含有關發送人和請求的信息。 它必須在 `open` 方法之後、`send` 方法之前調用。 這兩個參數是標頭的名稱和要設置爲該標頭正文的值。

接下來，`onreadystatechange` 事件監聽器監聽請求狀態的更改。 `readyState` 爲 `4`，表示操作已完成。`status` 爲 `201`，表示請求成功。 因此，文檔的 HTML 可以更新。

最後， `send` 方法發送帶有 `body` 值的請求。 `body` 包含一個 `userName` 和一個 `suffix` 鍵。

# --instructions--

更新代碼，向 API 端點發送 `POST` 請求。 然後在輸入框中輸入你的姓名，並點擊 `Send Message`。 你的 AJAX 函數會用服務器返回的數據替換 `Reply from Server will be here.`。 修改返回的請求結果，在你的名字後面添加 `loves cats`。

# --hints--

你的代碼應該創建一個新的 `XMLHttpRequest`。

```js
assert.match(code, /new\s*XMLHttpRequest\(\s*\)/g);
```

你的代碼應該使用 `open` 方法初始化一個發送給服務器的 `POST` 請求。

```js
assert.match(code, /\.open\(\s*('|")POST\1\s*,\s*url\s*,\s*true\s*\)/g);
```

你的代碼應該使用 `setRequestHeader` 方法。

```js
assert.match(
  code,
  /\.setRequestHeader\(\s*('|")Content-Type\1\s*,\s*('|")application\/json;\s*charset=UTF-8\2\s*\)/g
);
```

你的代碼應該有一個設置爲函數的 `onreadystatechange` 事件處理程序。

```js
assert.match(code, /\.onreadystatechange\s*=/g);
```

你的代碼應該獲取 class 爲 `message` 的元素，並將它的 `textContent` 更改爲 `userName loves cats`。

```js
assert.match(
  code,
  /document\.getElementsByClassName\(\s*('|")message\1\s*\)\[0\]\.textContent\s*=\s*.+?\.userName\s*\+\s*.+?\.suffix/g
);
```

你的代碼應該使用 `send` 方法。

```js
assert.match(code, /\.send\(\s*body\s*\)/g);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('sendMessage').onclick = function () {
      const userName = document.getElementById('name').value;
      const url = 'https://jsonplaceholder.typicode.com/posts';
      // Add your code below this line

      // Add your code above this line
    };
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

<h1>Cat Friends</h1>
<p class="message box">Reply from Server will be here</p>
<p>
  <label for="name"
    >Your name:
    <input type="text" id="name" />
  </label>
  <button id="sendMessage">Send Message</button>
</p>
```

# --solutions--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('sendMessage').onclick = function () {
      const userName = document.getElementById('name').value;
      const url = 'https://jsonplaceholder.typicode.com/posts';
      // Add your code below this line
      const xhr = new XMLHttpRequest();
      xhr.open('POST', url, true);
      xhr.setRequestHeader('Content-Type', 'application/json; charset=UTF-8');
      xhr.onreadystatechange = function () {
        if (xhr.readyState === 4 && xhr.status === 201) {
          const serverResponse = JSON.parse(xhr.response);
          document.getElementsByClassName('message')[0].textContent =
            serverResponse.userName + serverResponse.suffix;
        }
      };
      const body = JSON.stringify({
        userName: userName,
        suffix: ' loves cats!'
      });
      xhr.send(body);
      // Add your code above this line
    };
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

<h1>Cat Friends</h1>
<p class="message">Reply from Server will be here</p>
<p>
  <label for="name"
    >Your name:
    <input type="text" id="name" />
  </label>
  <button id="sendMessage">Send Message</button>
</p>
```
