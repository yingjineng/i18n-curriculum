---
id: bd7158d8c443edefaeb5bdff
title: リクエストヘッダーパーサー マイクロサービス
challengeType: 4
forumTopicId: 301507
dashedName: request-header-parser-microservice
---

# --description--

<a href="https://request-header-parser-microservice.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://request-header-parser-microservice.freecodecamp.rocks/</a> と同じような機能を持つ、フルスタック JavaScript アプリを構築してください。 プロジェクトに取り組むにあたり、以下の方法のうち 1 つを用いてコードを記述します。

-   <a href="https://github.com/freeCodeCamp/boilerplate-project-headerparser/" target="_blank" rel="noopener noreferrer nofollow">GitHub リポジトリ</a>をクローンし、ローカル環境でチャレンジを完了させる。
-   任意のサイトビルダーを使用してプロジェクトを完了させる。 ※必ず上記 GitHub リポジトリのすべてのファイルを取り込むようにしてください。

# --hints--

サンプルの URL ではなく、自分で作成したプロジェクトを提出する必要があります。

```js
  assert(
    !/.*\/request-header-parser-microservice\.freecodecamp\.rocks/.test(
      code
    )
  );
```

`/api/whoami` へのリクエストに対して、`ipaddress` キーにあなた (リクエストの送信者) の IP アドレスを持つ JSON オブジェクトを返す必要があります。

```js
  $.get(code + '/api/whoami').then(
    (data) => assert(data.ipaddress && data.ipaddress.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`/api/whoami` へのリクエストに対して、`language` キーにあなたの優先言語を持つ JSON オブジェクトを返す必要があります。

```js
  $.get(code + '/api/whoami').then(
    (data) => assert(data.language && data.language.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

`/api/whoami` へのリクエストに対して、`software` キーにあなたの使用しているソフトウェア情報を持つ JSON オブジェクトを返す必要があります。

```js
  $.get(code + '/api/whoami').then(
    (data) => assert(data.software && data.software.length > 0),
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

