---
id: 587d824f367417b2b2512c59
title: Chai-HTTPを使用して API エンドポイントで機能テストを実行するⅡ
challengeType: 2
forumTopicId: 301592
dashedName: run-functional-tests-on-api-endpoints-using-chai-http-ii
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-mochachai/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

# --instructions--

`tests/2_functional-tests.js` 内の `'Test GET /hello with your name'` というテスト (`// #2`) を変更し、テストが成功するように、レスポンスの `status` と `text` をアサートしてください。

ルートに `?name=<your_name>` を追加して名前を URL クエリとして送信してください。 エンドポイントは `'hello <your_name>'` で応答します。

# --hints--

すべてのテストが成功する必要があります。

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.state, 'passed');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`res.status` == 200 をテストする必要があります。

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[0].method, 'equal');
      assert.equal(data.assertions[0].args[0], 'res.status');
      assert.equal(data.assertions[0].args[1], '200');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`res.text` == `'hello <your_name>'` をテストする必要があります。

```js
  $.get(code + '/_api/get-tests?type=functional&n=1').then(
    (data) => {
      assert.equal(data.assertions[1].method, 'equal');
      assert.equal(data.assertions[1].args[0], 'res.text');
      assert.match(data.assertions[1].args[1], /hello [\w\d_-]/);
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

