---
id: 587d8247367417b2b2512c38
title: helmet.frameguard() を使用してクリックジャック攻撃のリスクを軽減する
challengeType: 2
forumTopicId: 301582
dashedName: mitigate-the-risk-of-clickjacking-with-helmet-frameguard
---

# --description--

As a reminder, this project is being built upon the following starter project cloned from <a href="https://github.com/freeCodeCamp/boilerplate-infosec/" target="_blank" rel="noopener noreferrer nofollow">GitHub</a>.

あなたのページは、あなたの同意なしに `<frame>` や `<iframe>` に挿入される可能性があります。 こうした可能性は、特にクリックジャック攻撃につながるおそれがあります。 クリックジャック攻撃とは、ユーザーをだまして、ユーザーが意図しているものとは違うページとやり取りさせる手法です。 これは、iframe を通じて悪意のあるコンテキストでページを実行することで実現されます。 こうした状況では、ハッカーによってあなたのページ上に隠れたレイヤーが配置されます。 悪意のあるスクリプトを実行するために、隠しボタンが使用されることがあります。 このミドルウェアは、X-Frame-Options ヘッダーを設定して、 サイトをフレーム内に配置できるユーザーを制限します。 DENY、SAMEORIGIN、ALLOW-FROM の 3 つのモードがあります。

サンプルのアプリをフレームに配置する必要はありません。

# --instructions--

`helmet.frameguard()` を使用し、config オブジェクト `{action: 'deny'}` を渡してください。

# --hints--

helmet.frameguard() ミドルウェアを正しくマウントする必要があります。

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.include(
        data.appStack,
        'frameguard',
        'helmet.frameguard() middleware is not mounted correctly'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

helmet.frameguard() の 'action' を 'DENY' に設定する必要があります。

```js
  $.get(code + '/_api/app-info').then(
    (data) => {
      assert.property(data.headers, 'x-frame-options');
      assert.equal(data.headers['x-frame-options'], 'DENY');
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

