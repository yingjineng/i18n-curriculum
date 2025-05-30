---
id: 587d824a367417b2b2512c44
title: 株価チェッカー
challengeType: 4
forumTopicId: 301572
dashedName: stock-price-checker
---

# --description--

<a href="https://stock-price-checker.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://stock-price-checker.freecodecamp.rocks/</a> と同じような機能を持つ、フルスタック JavaScript アプリを構築してください。

信頼できる株価 API の利用にはすべて API キーが必要になるため、ここでは回避策を用意しました。 <a href="https://stock-price-checker-proxy.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://stock-price-checker-proxy.freecodecamp.rocks/</a> を使用すれば、登録して自分のキーを取得しなくても最新の株価情報を得ることができます。

プロジェクトに取り組むにあたり、以下の方法のうち 1 つを用いてコードを記述します。

-   <a href="https://github.com/freeCodeCamp/boilerplate-project-stockchecker/" target="_blank" rel="noopener noreferrer nofollow">GitHub リポジトリ</a>をクローンし、ローカル環境でプロジェクトを完了させる。
-   任意のサイトビルダーを使用してプロジェクトを完了させる。 ※必ず上記 GitHub リポジトリのすべてのファイルを取り込むようにしてください。

# --instructions--

1.  環境変数 `NODE_ENV` を `test` に設定する (引用符なし)
2.  `routes/api.js` でプロジェクトを完成させるか、ハンドラー/コントローラーを作成します。
3.  `server.js` にセキュリティ機能を追加します。
4.  `tests/2_functional-tests.js` にすべての機能テストを作成します。

**プライバシーに対する注意事項**: 1 つの IP に対して 1 つの「いいね！」しか受け付けないという条件があるため、IP アドレスを保存する必要があります。 GDPR (一般データ保護規則) などのデータプライバシー関連の法令を遵守することが重要です。 ユーザーのデータを保存するための権限を取得するという方法もありますが、データを匿名化する方がはるかに簡単です。 このチャレンジでは、データベースに保存する前に必ず IP アドレスを匿名化してください。 その方法として、データをハッシュ化する、切り詰める、IP アドレスの一部を 0 にする、などが考えられます。

次のテストを `tests/2_functional-tests.js` に記述してください。

-   1 つの株式を表示: `/api/stock-prices/` への GET リクエスト
-   1 つの株式を表示して「いいね！」をクリック: `/api/stock-prices/` への GET リクエスト
-   もう一度同じ株式を表示して「いいね！」をクリック: `/api/stock-prices/` への GET リクエスト
-   2 つの株式を表示: `/api/stock-prices/` への GET リクエスト
-   2 つの株式を表示して「いいね！」をクリック: `/api/stock-prices/` への GET リクエスト

# --hints--

サンプルの URL ではなく、自分で作成したプロジェクトを提出してください。

```js
  assert(
    !/.*\/stock-price-checker\.freecodecamp\.rocks/.test(code)
  );
```

コンテンツセキュリティポリシーを設定して、自分のサーバーからのみスクリプトや CSS の読み込みを許可するようにしてください。

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

`GET` リクエストを `/api/stock-prices` に送信し、NASDAQ 株式表示記号を `stock` クエリパラメーターに渡すことができます。 返されるオブジェクトには、`stockData` というプロパティが含まれます。

```js
async () => {
  const data = await fetch(
    code + '/api/stock-prices?stock=GOOG'
  );
  const parsed = await data.json();
  assert.property(parsed, 'stockData');
};
```

`stockData` プロパティには、文字列としての `stock` 記号、数値としての `price`、数値としての `likes` が含まれています。

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

また、`like` フィールドに `true` (ブール値) を渡すと、その株式の「いいね！」が増えます。 「いいね！」は、1 つの IP につき 1 回のみ受け付ける必要があります。

```js

```

2 つの株式を渡した場合、返される値は 2 つの株式に関する情報を持つ配列となります。 その場合 `likes` の代わりに、両方の `stockData` オブジェクトの `rel_likes` (両株式の「いいね！」の差) を表示します。

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

5 件の機能テストがすべて記述され、成功する状態になっています。

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

