---
id: 58a25bcff9fc0f352b528e7d
title: パスワードを非同期的にハッシュ化して比較する
challengeType: 2
forumTopicId: 301578
dashedName: hash-and-compare-passwords-asynchronously
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-bcrypt/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

ハッシュは計算量が多くなるように設計されているので、ハッシュ処理中に接続がブロックされないように、サーバー上で非同期的に処理することをお勧めします。 次の呼び出しを実行するだけで、パスワードを非同期にハッシュ化できます。

```js
bcrypt.hash(myPlaintextPassword, saltRounds, (err, hash) => {
  /*Store hash in your db*/
});
```

# --instructions--

このハッシュ関数をサーバーに追加し (関数内で使用されている変数はすでに定義してあります)、コンソールに出力して確認してください。 通常はこの時点でハッシュをデータベースに保存します。

新しい入力がハッシュと同じデータかどうかを調べる必要がある場合は、compare 関数を使用します。

```js
bcrypt.compare(myPlaintextPassword, hash, (err, res) => {
  /*res == true or false*/
});
```

完了したハッシュを出力し、compare の中でコンソールに "res" と出力した後、これを既存のハッシュ関数に追加してください (compare 関数を呼び出す前にハッシュの完了を待つ必要があるため)。 コンソールにハッシュが出力され、次に 'true' と出力されるはずです。 compare 関数の 'myPlaintextPassword' を 'someOtherPlaintextPassword' に変更すると、false と表示されます。

```js
bcrypt.hash('passw0rd!', 13, (err, hash) => {
  console.log(hash);
  //$2a$12$Y.PHPE15wR25qrrtgGkiYe2sXo98cjuMCG1YwSI5rJW1DSJp0gEYS
  bcrypt.compare('passw0rd!', hash, (err, res) => {
    console.log(res); //true
  });
});

```

正しいと思ったら、ページを送信してください。

# --hints--

非同期ハッシュを生成し、正しく比較する必要があります。

```js
  $.get(code + '/_api/server.js').then(
    (data) => {
      assert.match(
        data,
        /START_ASYNC[^]*bcrypt.hash.*myPlaintextPassword( |),( |)saltRounds( |),( |).*err( |),( |)hash[^]*END_ASYNC/gi,
        'You should call bcrypt.hash on myPlaintextPassword and saltRounds and handle err and hash as a result in the callback'
      );
      assert.match(
        data,
        /START_ASYNC[^]*bcrypt.hash[^]*bcrypt.compare.*myPlaintextPassword( |),( |)hash( |),( |).*err( |),( |)res[^]*}[^]*}[^]*END_ASYNC/gi,
        'Nested within the hash function should be the compare function comparing myPlaintextPassword to hash'
      );
    },
    (xhr) => {
      throw new Error(xhr.statusText);
    }
  );
```

