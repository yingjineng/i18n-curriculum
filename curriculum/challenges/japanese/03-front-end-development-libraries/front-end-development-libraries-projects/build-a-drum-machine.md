---
id: 587d7dbc367417b2b2512bae
title: ドラムマシンを作成する
challengeType: 3
forumTopicId: 301370
dashedName: build-a-drum-machine
---

# --description--
**注:** **React 18 はこのプロジェクトのテストとの互換性がありません。(詳細は[こちらの Issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922) を参照してください。)**

**目標:** こちらと似た機能を持つアプリを構築してください: <a href="https://drum-machine.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://drum-machine.freecodecamp.rocks</a>

以下のユーザーストーリーを満たし、すべてのテストが成功するようにしてください。 必要に応じて、どのようなライブラリあるいは API を使用してもかまいません。 あなた独自のアレンジを加えましょう。

このプロジェクトを完了するために、HTML、JavaScript、CSS、Bootstrap、SASS、React、Redux、および jQuery を自在に組み合わせて利用することができます。 このセクションはフロントエンドフレームワークの学習を目的としていますので、React などのフロントエンドフレームワークを使用してください。 上記以外の他のテクノロジーは推奨されません。使用する場合は自己責任で行ってください。 Angular や Vue などの他のフロントエンドフレームワークのサポートを検討していますが、現時点ではサポートされていません。 このプロジェクトで推奨している一連のテクノロジーを使用して生じる不具合については、freeCodeCamp にて報告を受け入れ、修正するよう努めます。 コーディングを楽しみましょう！Happy coding!

**ユーザーストーリー 1:** 対応する `id="drum-machine"` を持ち、他のすべての要素を収める、外側のコンテナーを表示できます。

**ユーザーストーリー 2:** `#drum-machine` の中に、対応する `id="display"` を持つ要素を表示できます。

**ユーザーストーリー 3:** `#drum-machine` の中に、9 つのクリック可能なドラムパッド要素を表示できます。要素はそれぞれ、クラス名 `drum-pad` と、ドラムパットのトリガー用に準備されるオーディオクリップを示す一意の ID、および、キーボードの `Q`、`W`、`E`、`A`、`S`、`D`、`Z`、`X`、`C` のいずれかのキーに対応する内側のテキストを持ちます。 ドラムパッドはこの順序にする必要があります。

**ユーザーストーリー 4:** それぞれの `.drum-pad` の中に、HTML5 の `audio` 要素を配置します。この要素は、オーディオクリップを指し示す `src` 属性、クラス名 `clip`、および、自身の親である `.drum-pad` の内側のテキストに対応する ID を持ちます (`id="Q"`、`id="W"`、`id="E"` など)。

**ユーザーストーリー 5:** `.drum-pad` 要素をクリックすると、その子の `audio` 要素に含まれているオーディオクリップがトリガーされます。

**ユーザーストーリー 6:** それぞれの `.drum-pad` に関連付けられているトリガーキーを押すと、その子の `audio` 要素に含まれているオーディオクリップがトリガーされます。たとえば、`Q` キーを押すと文字列 `Q` を含むドラムパッドがトリガーされ、`W` キーを押すと文字列 `W` を含むドラムパッドがトリガーされる、などとなります。

**ユーザーストーリー 7:** `.drum-pad` がトリガーされると、関連するオーディオクリップを説明する文字列が、`#display` 要素の内側のテキストとして表示されます (文字列はそれぞれ一意にする必要があります)。

ドラムマシンに使用できるオーディオサンプルの例は次のとおりです。

- [Heater 1](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-1.mp3)
- [Heater 2](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-2.mp3)
- [Heater 3](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-3.mp3)
- [Heater 4](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-4_1.mp3)
- [Clap](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Heater-6.mp3)
- [Open-HH](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Dsc_Oh.mp3)
- [Kick-n'-Hat](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Kick_n_Hat.mp3)
- [Kick](https://cdn.freecodecamp.org/testable-projects-fcc/audio/RP4_KICK_1.mp3)
- [Closed-HH](https://cdn.freecodecamp.org/testable-projects-fcc/audio/Cev_H2.mp3)

<a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">この CodePen テンプレートを使用して</a> あなたのプロジェクトを構築することができます。`Save` をクリックすると、あなた用の pen (CodePen 上の作品) を作成することができます。 他の環境を使用する場合は、`index.html` ファイルのボディに次の `<script>` タグを含めてください: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

完了したら、すべてのテストがパスする状態の作業プロジェクトの URL を送信します。

# --solutions--

```js
// solution required
```
