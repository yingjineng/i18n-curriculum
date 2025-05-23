---
id: 587d824a367417b2b2512c44
title: 股票價格查看器
challengeType: 4
forumTopicId: 301572
dashedName: stock-price-checker
---

# --description--

Build a full stack JavaScript app that is functionally similar to this: <a href="https://stock-price-checker.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://stock-price-checker.freecodecamp.rocks/</a>.

由於所有可靠的股票價格 API 都需要一個 API 密鑰，我們已經建立了一個解決方案。 使用 <a href="https://stock-price-checker-proxy.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://stock-price-checker-proxy.freecodecamp.rocks/</a> 獲取最新的股票價格信息，而無需註冊你自己的密鑰。

可以採用下面的任意一種方式完成這個挑戰：

-   Clone <a href="https://github.com/freeCodeCamp/boilerplate-project-stockchecker/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete your project locally.
-   Use a site builder of your choice to complete the project. Be sure to incorporate all the files from our GitHub repo.

# --instructions--

1.  Set the `NODE_ENV` environment variable to `test`, without quotes
2.  在 `routes/api.js` 中完成項目，或者通過創建一個處理程序/控制器來完成項目
3.  添加安全功能到 `server.js`。
4.  在 `tests/2_functional-tests.js` 中創建所有的功能測試

**Note** Privacy Considerations: Due to the requirement that only 1 like per IP should be accepted, you will have to save IP addresses. It is important to remain compliant with data privacy laws such as the General Data Protection Regulation. One option is to get permission to save the user's data, but it is much simpler to anonymize it. For this challenge, remember to anonymize IP addresses before saving them to the database. If you need ideas on how to do this, you may choose to hash the data, truncate it, or set part of the IP address to 0.

在 `tests/2_functional-tests.js` 中編寫下以下測試：

-   Viewing one stock: GET request to `/api/stock-prices/`
-   查看一個股票並關注它：發送 GET 請求到 `/api/stock-prices/`
-   查看同一只股票並再次發送關注：發送 GET 請求到 `/api/stock-prices/`
-   查看兩隻股票：發送 GET 請求到 `/api/stock-prices/`
-   查看兩隻股票並關注它：發送 GET 請求到 `/api/stock-prices/`

# --hints--

你可以提交你自己的項目，而不是示例的 URL。

```js
  assert(
    !/.*\/stock-price-checker\.freecodecamp\.rocks/.test(code)
  );
```

將內容安全策略設置爲僅允許從服務器加載腳本和 CSS。

```js
async () => {
  const data = await fetch(code + '/_api/app-info');
  const parsed = await data.json();
  assert.isTrue(
    parsed.headers['content-security-policy'].includes("script-src 'self'")
  );
  assert.isTrue(
    parsed.headers['content-security-policy'].includes("style-src 'self'")
  );
};
```

你可以向 `/api/stock-prices` 發送一個 `GET` 請求，將納斯達克股票代碼賦值給 `stock` 查詢參數。 返回的對象將包含一個名爲 `stockData` 的屬性。

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG'
  );
  const parsed = await data.json();
  assert.property(parsed, 'stockData');
};
```

`stockData` 屬性包括字符串 `stock` 代碼、數字 `price`，以及數字 `likes`。

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG'
  );
  const parsed = await data.json();
  const ticker = parsed.stockData;
  assert.typeOf(ticker.price, 'number');
  assert.typeOf(ticker.likes, 'number');
  assert.typeOf(ticker.stock, 'string');
};
```

你也可以用作爲 `true`（布爾值）來傳遞 `like` 字段，讓你的偏好添加到股票中。 每個 IP 應該只接受 1 個贊。

```js

```

如果你傳遞了兩隻股票，返回值將是一個包含這兩隻股票信息的數組。 它將會顯示對於兩個 `stockData` 對象的 `rel_likes`（兩隻股票所獲得的贊同數的區別），而不是 `likes`。

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG&stock=MSFT'
  );
  const parsed = await data.json();
  const ticker = parsed.stockData;
  assert.typeOf(ticker, 'array');
  assert.property(ticker[0], 'rel_likes');
  assert.property(ticker[1], 'rel_likes');
};
```

所有 5 項功能測試都已完成並通過。

```js
async () => {
  const tests = await fetch(code + '/_api/get-tests');
  const parsed = await tests.json();
  assert.isTrue(parsed.length >= 5);
  parsed.forEach((test) => {
    assert.equal(test.state, 'passed');
  });
};
```

