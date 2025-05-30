---
id: bd7158d8c442eddfaeb5bd13
title: ランダムクォートマシンを作成する
challengeType: 3
forumTopicId: 301374
dashedName: build-a-random-quote-machine
---

# --description--
**注:** **React 18 はこのプロジェクトのテストとの互換性がありません。(詳細は[こちらの Issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922) を参照してください。)**

**目標:** こちらと似た機能を持つアプリを構築してください: <a href="https://random-quote-machine.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://random-quote-machine.freecodecamp.rocks</a>

以下のユーザーストーリーを満たし、すべてのテストが成功するようにしてください。 必要に応じて、どのようなライブラリあるいは API を使用してもかまいません。 あなた独自のアレンジを加えましょう。

このプロジェクトを完了するために、HTML、JavaScript、CSS、Bootstrap、SASS、React、Redux、および jQuery を自在に組み合わせて利用することができます。 このセクションはフロントエンドフレームワークの学習を目的としていますので、React などのフロントエンドフレームワークを使用してください。 上記以外の他のテクノロジーは推奨されません。使用する場合は自己責任で行ってください。 Angular や Vue などの他のフロントエンドフレームワークのサポートを検討していますが、現時点ではサポートされていません。 このプロジェクトで推奨している一連のテクノロジーを使用して生じる不具合については、freeCodeCamp にて報告を受け入れ、修正するよう努めます。 コーディングを楽しみましょう！Happy coding!

**ユーザーストーリー 1:** 対応する `id="quote-box"` を持つラッパー要素を表示できます。

**ユーザーストーリー 2:** `#quote-box` の中に、対応する `id="text"` を持つ要素を表示できます。

**ユーザーストーリー 3:** `#quote-box` の中に、対応する `id="author"` を持つ要素を表示できます。

**ユーザーストーリー 4:** `#quote-box` の中に、対応する `id="new-quote"` を持つ要素を表示できます。

**ユーザーストーリー 5:** `#quote-box` の中に、対応する `id="tweet-quote"` を持つクリック可能な `a` 要素を表示できます。

**ユーザーストーリー 6:** クォートマシンの初回読み込み時に、`id="text"` を持つ要素に、ランダムクォートが表示されます。

**ユーザーストーリー 7:** クォートマシンの初回読み込み時に、`id="author"` を持つ要素に、ランダムクォートの作成者が表示されます。

**ユーザーストーリー 8:** クォートマシンの `#new-quote` ボタンをクリックすると、新しいクォートが取得されて `#text` 要素に表示されます。

**ユーザーストーリー 9:** クォートマシンの `#new-quote` ボタンをクリックすると、新しいクォートの作成者が取得されて `#author` 要素に表示されます。

**ユーザーストーリー 10:** `#tweet-quote` の `a` 要素をクリックして現在のクォートをツイートできます。 この `a` 要素の `href` 属性には、現在のクォートをツイートするための `"twitter.com/intent/tweet"` パスが含まれています。

**ユーザーストーリー 11:** `#quote-box` ラッパー要素は水平方向に中央寄せされます。 ブラウザのズームレベルを 100% にし、ページを最大化してテストしてください。

プロジェクトの構築には<a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">この CodePen テンプレート</a>を使用できます。`Save` をクリックすると、あなた用の pen (CodePen 上の作品) が作成できます。 他の環境を使用する場合は、`index.html` ファイルのボディに次の `<script>` タグを含めてください: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

完了したら、すべてのテストが成功する状態の作業プロジェクトの URL を送信してください。

**注:** Twitterでは、iframe にリンクを読み込むことはできません。 ツイートが読み込まれない場合は、`#tweet-quote` 要素で `target="_blank"` または `target="_top"` 属性を使用してみてください。 `target="_top"` は現在のタブを置き換えるので、作業が保存されていることを確認してください。

# --solutions--

```js
// solution required
```
