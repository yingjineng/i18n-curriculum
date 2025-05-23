---
id: bd7157d8c242eddfaeb5bd13
title: マークダウンプレビューアを作成する
challengeType: 3
forumTopicId: 301372
dashedName: build-a-markdown-previewer
---

# --description--
**注:** **React 18 はこのプロジェクトのテストとの互換性がありません。(詳細は[こちらの Issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922) を参照してください。)**

**目標:** こちらと似た機能を持つアプリを構築してください: <a href="https://markdown-previewer.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://markdown-previewer.freecodecamp.rocks</a>

以下のユーザーストーリーを満たし、すべてのテストが成功するようにしてください。 必要に応じて、どのようなライブラリあるいは API を使用してもかまいません。 あなた独自のアレンジを加えましょう。

このプロジェクトを完了するために、HTML、JavaScript、CSS、Bootstrap、SASS、React、Redux、および jQuery を自在に組み合わせて利用することができます。 このセクションはフロントエンドフレームワークの学習を目的としていますので、React などのフロントエンドフレームワークを使用してください。 上記以外の他のテクノロジーは推奨されません。使用する場合は自己責任で行ってください。 Angular や Vue などの他のフロントエンドフレームワークのサポートを検討していますが、現時点ではサポートされていません。 このプロジェクトで推奨している一連のテクノロジーを使用して生じる不具合については、freeCodeCamp にて報告を受け入れ、修正するよう努めます。 コーディングを楽しみましょう！Happy coding!

**ユーザーストーリー 1:** 対応する `id="editor"` を持つ `textarea` 要素を表示できます。

**ユーザーストーリー 2:** 対応する `id="preview"` を持つ要素を表示できます。

**ユーザーストーリー 3:** `#editor` 要素にテキストを入力すると、入力に応じて `#preview` 要素が更新され、テキストエリアの内容が表示されます。

**ユーザーストーリー 4:** GitHub 対応のマークダウンを `#editor` 要素に入力すると、入力に応じて `#preview` 要素にテキストが HTML としてレンダーされます (ヒント: マークダウンを自分で解析する必要はありません。この処理のための Marked ライブラリをインポートできます: <https://cdnjs.com/libraries/marked>)。

**ユーザーストーリー 5:** マークダウンプレビューアプリが初めて読み込まれるとき、`#editor` フィールドのデフォルトのテキストには、見出し要素 (H1 サイズ)、小見出し要素 (H2 サイズ)、リンク、インラインコード、コードブロック、リストアイテム、ブロッククォート、画像、太字テキストの各要素のうち少なくとも 1 つを表す有効なマークダウンが含まれている必要があります。

**ユーザーストーリー 6:** マークダウンプレビューアプリが初めて読み込まれるとき、`#editor` フィールドのデフォルトのマークダウンが `#preview` 要素に HTML としてレンダーされます。

**オプションボーナス (このテストを成功させる必要はありません):** マークダウンプレビューアプリは、キャリッジリターンを解釈し、それらを `br` (改行) 要素としてレンダーします。

プロジェクトの構築には<a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">この CodePen テンプレート</a>を使用できます。`Save` をクリックすると、あなた用の pen が作成できます。 他の環境を使用する場合は、`index.html` ファイルのボディに次の `<script>` タグを含めてください: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

完了したら、すべてのテストが成功する状態の作業プロジェクトの URL を送信してください。

# --solutions--

```js
// solution required
```
