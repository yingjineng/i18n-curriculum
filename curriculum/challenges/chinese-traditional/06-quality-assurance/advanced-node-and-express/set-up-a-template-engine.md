---
id: 5895f700f9fc0f352b528e63
title: 設置模板引擎
challengeType: 2
forumTopicId: 301564
dashedName: set-up-a-template-engine
---

# --description--

Working on these challenges will involve you writing your code using one of the following methods:

- Clone <a href="https://github.com/freeCodeCamp/boilerplate-advancednode/" target="_blank" rel="noopener noreferrer nofollow">this GitHub repo</a> and complete these challenges locally.
- 使用你選擇的網站生成器來完成項目。 需要包含我們 GitHub 倉庫的所有文件。

你可以在應用的模版引擎中使用靜態模板文件（如那些寫在 *Pug* 裏的）。 At runtime, the template engine replaces variables in a template file with actual values which can be supplied by your server. 在運行時，模版引擎會用服務端的真實數據替換掉模版文件中的變量，然後將模版轉譯成發送給客戶端的 HTML 靜態文件。 這樣可以輕鬆地構造 HTML 頁面，允許在頁面直接顯示變量內容而不需要發送 API 請求。

`pug@~3.0.0` has already been installed, and is listed as a dependency in your `package.json` file.

Express needs to know which template engine you are using. Use the `set` method to assign `pug` as the `view engine` property's value:

```javascript
app.set('view engine', 'pug');
```

After that, add another `set` method that sets the `views` property of your `app` to point to the `./views/pug` directory. This tells Express to render all views relative to that directory.

Finally, use `res.render()` in the route for your home page, passing `index` as the first argument. This will render the `pug` template.

If all went as planned, your app home page will no longer be blank. Instead, it will display a message indicating you've successfully rendered the Pug template!

完成上述要求後，你可以在下方提交你的頁面鏈接。 If you're running into errors, you can <a href="https://forum.freecodecamp.org/t/advanced-node-and-express/567135#set-up-a-template-engine-1" target="_blank" rel="noopener noreferrer nofollow">check out the project completed up to this point</a>.

# --hints--

項目中應使用 Pug 作爲依賴。

```js
async () => {
  const url = new URL("/_api/package.json", code);
  const res = await fetch(url);
  const packJson = await res.json();
  assert.property(
    packJson.dependencies,
    'pug',
    'Your project should list "pug" as a dependency'
  );
}
```

項目中應使用 Pug 作爲模版引擎。

```js
async () => {
  const url = new URL("/_api/app", code);
  const res = await fetch(url);
  const app = await res.json();
  assert.equal(app?.settings?.['view engine'], "pug");
}
```

You should set the `views` property of the application to `./views/pug`.

```js
async () => {
  const url = new URL("/_api/app", code);
  const res = await fetch(url);
  const app = await res.json();
  assert.equal(app?.settings?.views, "./views/pug");
}
```

使用正確的 ExpressJS 方法渲染來自響應的索引頁。

```js
async () => {
  const url = new URL("/", code);
  const res = await fetch(url);
  const data = await res.text();
      assert.match(
        data,
        /FCC Advanced Node and Express/gi,
        'You successfully rendered the Pug template!'
      );
    }
```

Pug 應該正常運行。

```js
async () => {
  const url = new URL("/", code);
  const res = await fetch(url);
  const data = await res.text();
      assert.match(
        data,
        /pug-success-message/gi,
        'Your projects home page should now be rendered by pug with the projects .pug file unaltered'
      );
    }
```

