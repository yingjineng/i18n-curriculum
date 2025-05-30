---
id: 6555c1d3e11a1574434cf8b5
title: ポケモン検索アプリを作成する
challengeType: 14
forumTopicId: 16003
dashedName: build-a-pokemon-search-app
---

# --description--

このプロジェクトでは、ポケモンを名前または ID で検索して結果を表示するアプリを作成します。 ポケモンのデータや画像の取得には、freeCodeCamp の <a href="https://pokeapi-proxy.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">PokéAPI プロキシー</a>を使用します。

 **注:** 最初の 13 項目は、`index.html` ファイル内で完了させてください。

**目標:** <a href="https://pokemon-search-app.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://pokemon-search-app.freecodecamp.rocks</a> と似た機能を持つアプリを作成してください。

**ユーザーストーリー:**

1. You should have an `input` element with an `id` of `"search-input"`, and is required.
1. `id` が `"search-button"` に設定された `button` 要素が必要です。
1. `id` が `"pokemon-name"` に設定された要素が必要です。
1. `id` が `"pokemon-id"` に設定された要素が必要です。
1. `id` が `"weight"` に設定された要素が必要です。
1. `id` が `"height"` に設定された要素が必要です。
1. `id` が `"types"` に設定された要素が必要です。
1. `id` が `"hp"` に設定された要素が必要です。
1. `id` が `"attack"` に設定された要素が必要です。
1. `id` が `"defense"` に設定された要素が必要です。
1. `id` が `"special-attack"` に設定された要素が必要です。
1. `id` が `"special-defense"` に設定された要素が必要です。
1. `id` が `"speed"` に設定された要素が必要です。
1. `#search-input` の要素に `Red` という値を入力した状態で `#search-button` の要素をクリックした場合、`"Pokémon not found"` というテキストのアラートが表示されます。
1. When the `#search-input` element contains the value `Pikachu` and the `#search-button` element is clicked, the values in the `#pokemon-name`, `#pokemon-id`, `#weight`, `#height`, `#hp`, `#attack`, `#defense`, `#special-attack`, `#special-defense`, and `#speed` elements should be `PIKACHU`, `#25` or `25`, `Weight: 60` or `60`, `Height: 4` or `4`, `35`, `55`, `40`, `50`, `50`, and `90`, respectively.
1. When the `#search-input` element contains the value `Pikachu` and the `#search-button` element is clicked, you should add an `img` element with the `id` of `"sprite"` and the `src` set to the Pokémon's `front_default` sprite to the page.
1. `#search-input` の要素に `Pikachu` という値を入力した状態で `#search-button` の要素をクリックした場合、`#types` の要素の中には、`ELECTRIC` という値を持つ要素が 1 つ入ります。 `#types` の要素の中身は、検索の度にクリアされるようにしてください。
1. When the `#search-input` element contains the value `94` and the `#search-button` element is clicked, the values in the `#pokemon-name`, `#pokemon-id`, `#weight`, `#height`, `#hp`, `#attack`, `#defense`, `#special-attack`, `#special-defense`, and `#speed`elements should be `GENGAR`, `#94` or `94`, `Weight: 405` or `405`, `Height: 15` or `15`, `60`, `65`, `60`, `130`, `75`, and `110`, respectively.
1. When the `#search-input` element contains the value `94` and the `#search-button` element is clicked, you should add an `img` element with the `id` of `sprite` and the `src` set to the Pokémon's `front_default` sprite to the page.
1. `#search-input` の要素に `94` という値を入力した状態で `#search-button` の要素をクリックした場合、`#types` の要素の中には、`GHOST` と `POISON` という値を持つ 2 つの要素が入ります。 `#types` の要素の中身は、検索の度にクリアされるようにしてください。
1. When the `#search-input` element contains an invalid Pokemon name, and the `#search-button` element is clicked, an alert should appear with the text `"Pokémon not found"`.
1. `#search-input` の要素に有効なポケモンの ID を入力した状態で `#search-button` の要素をクリックした場合、正しいデータが UI に表示されます。

上記のユーザーストーリーを満たし、以下のすべてのテストが通るようにして、このプロジェクトを完成させてください。 あなた独自のアレンジを加えましょう。 ハッピーコーディング！

**注:** テストの実行時、多少の遅延が発生します。 テストが終了するまで数秒お待ちください。 完了する前にページを更新しないでください。

# --hints--

`id` が `"search-input"` に設定された `input` 要素が必要です。 The `input` should be marked as required.

```js
const el = document.getElementById('search-input');
assert.strictEqual(el?.nodeName?.toLowerCase(), 'input');
assert.isTrue(el?.required);
```

`id` が `"search-button"` に設定された `button` 要素が必要です。

```js
const el = document.getElementById('search-button');
assert.strictEqual(el?.nodeName?.toLowerCase(), 'button');
```

`id` が `"pokemon-name"` に設定された要素が必要です。

```js
const el = document.getElementById('pokemon-name');
assert.exists(el);
```

`id` が `"pokemon-id"` に設定された要素が必要です。

```js
const el = document.getElementById('pokemon-id');
assert.exists(el);
```

`id` が `"weight"` に設定された要素が必要です。

```js
const el = document.getElementById('weight');
assert.exists(el);
```

`id` が `"height"` に設定された要素が必要です。

```js
const el = document.getElementById('height');
assert.exists(el);
```

`id` が `"types"` に設定された要素が必要です。

```js
const el = document.getElementById('types');
assert.exists(el);
```

`id` が `"hp"` に設定された要素が必要です。

```js
const el = document.getElementById('hp');
assert.exists(el);
```

`id` が `"attack"` に設定された要素が必要です。

```js
const el = document.getElementById('attack');
assert.exists(el);
```

`id` が `"defense"` に設定された要素が必要です。

```js
const el = document.getElementById('defense');
assert.exists(el);
```

`id` が `"special-attack"` に設定された要素が必要です。

```js
const el = document.getElementById('special-attack');
assert.exists(el);
```

`id` が `"special-defense"` に設定された要素が必要です。

```js
const el = document.getElementById('special-defense');
assert.exists(el);
```

`id` が `"speed"` に設定された要素が必要です。

```js
const el = document.getElementById('speed');
assert.exists(el);
```

`#search-input` の要素に `Red` という値を入力した状態で `#search-button` の要素をクリックした場合、`"Pokémon not found"` というテキストのアラートが表示されます。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    let alertMessage;
    window.alert = (message) => alertMessage = message; // Override alert and store message
    searchInput.value = 'Red';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/red'); // Fetch from proxy to simulate network delay

    if (!res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow the alert to trigger

      assert.include(['pokémon not found', 'pokemon not found'], alertMessage?.trim().replace(/[.,?!]+$/g, '').toLowerCase());
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に `Pikachu` という値を入力した状態で `#search-button` の要素をクリックした場合、`#pokemon-name`、`#pokemon-id`、`#weight`、`#height`、`#hp`、`#attack`、`#defense`、`#special-attack`、`#special-defense`、`#speed` の各要素の値はそれぞれ、`PIKACHU`、`#25` または `25`、`Weight: 60` または `60`、`Height: 4` または `4`、`35`、`55`、`40`、`50`、`50`、`90` となります。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    searchInput.value = 'Pikachu';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/pikachu'); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow UI to update

      const pokemonName = document.getElementById('pokemon-name');
      const pokemonID = document.getElementById('pokemon-id');
      const weight = document.getElementById('weight');
      const height = document.getElementById('height');
      const hp = document.getElementById('hp');
      const attack = document.getElementById('attack');
      const defense = document.getElementById('defense');
      const specialAttack = document.getElementById('special-attack');
      const specialDefense = document.getElementById('special-defense');
      const speed = document.getElementById('speed');

      assert.strictEqual(pokemonName.innerText.trim().toLowerCase(), 'pikachu');
      assert.include(['#25', '25'], pokemonID.innerText.trim());
      assert.include(['weight: 60', '60'], weight.innerText.trim().toLowerCase());
      assert.include(['height: 4', '4'], height.innerText.trim().toLowerCase());
      assert.strictEqual(hp.innerText.trim(), '35');
      assert.strictEqual(attack.innerText.trim(), '55');
      assert.strictEqual(defense.innerText.trim(), '40');
      assert.strictEqual(specialAttack.innerText.trim(), '50');
      assert.strictEqual(specialDefense.innerText.trim(), '50');
      assert.strictEqual(speed.innerText.trim(), '90');
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に `Pikachu` という値を入力した状態で `#search-button` の要素をクリックした場合、`id` が `"sprite"`、`src` がそのポケモンの `front_default` のスプライト画像 (sprites) に設定された `img` 要素を、ページに追加してください。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    searchInput.value = 'Pikachu';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/pikachu'); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow UI to update

      const sprite = document.getElementById('sprite');
      assert.isTrue(sprite.src.endsWith('sprites/pokemon/25.png'));
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に `Pikachu` という値を入力した状態で `#search-button` の要素をクリックした場合、`#types` の要素の中には、`ELECTRIC` という値を持つ要素が 1 つ入ります。 `#types` 要素の中身は、検索の度にクリアされるようにしてください。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    searchInput.value = 'Pikachu';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/pikachu'); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow UI to update

      const typesEl = document.getElementById('types');

      assert.lengthOf(typesEl.children, 1);
      assert.strictEqual(typesEl?.children[0]?.innerText.trim().toLowerCase(), 'electric');
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に `94` という値を入力した状態で `#search-button` の要素をクリックした場合、`#pokemon-name`、`#pokemon-id`、`#weight`、`#height`、`#hp`、`#attack`、`#defense`、`#special-attack`、`#special-defense`、`#speed` の各要素の値はそれぞれ、`GENGAR`、`#94` または `94`、`Weight: 405` または `405`、`Height: 15` または `15`、`60`、`65`、`60`、`130`、`75`、`110` となります。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    searchInput.value = '94';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/94'); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow UI to update

      const pokemonName = document.getElementById('pokemon-name');
      const pokemonID = document.getElementById('pokemon-id');
      const weight = document.getElementById('weight');
      const height = document.getElementById('height');
      const hp = document.getElementById('hp');
      const attack = document.getElementById('attack');
      const defense = document.getElementById('defense');
      const specialAttack = document.getElementById('special-attack');
      const specialDefense = document.getElementById('special-defense');
      const speed = document.getElementById('speed');

      assert.strictEqual(pokemonName.innerText.trim().toLowerCase(), 'gengar');
      assert.include(['#94', '94'], pokemonID.innerText.trim());
      assert.include(['weight: 405', '405'], weight.innerText.trim().toLowerCase());
      assert.include(['height: 15', '15'], height.innerText.trim().toLowerCase());
      assert.strictEqual(hp.innerText.trim(), '60');
      assert.strictEqual(attack.innerText.trim(), '65');
      assert.strictEqual(defense.innerText.trim(), '60');
      assert.strictEqual(specialAttack.innerText.trim(), '130');
      assert.strictEqual(specialDefense.innerText.trim(), '75');
      assert.strictEqual(speed.innerText.trim(), '110');
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に `94` という値を入力した状態で `#search-button` の要素をクリックした場合、`id` が `"sprite"`、`src` がそのポケモンの `front_default` のスプライト画像 (sprites) に設定された `img` 要素を、ページに追加してください。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    searchInput.value = '94';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/94'); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow UI to update

      const sprite = document.getElementById('sprite');
      assert.isTrue(sprite.src.endsWith('sprites/pokemon/94.png'));
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に `94` という値を入力した状態で `#search-button` の要素をクリックした場合、`#types` の要素の中には、`GHOST` と `POISON` という値を持つ 2 つの要素が入ります。 `#types` 要素の中身は、検索の度にクリアされるようにしてください。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    searchInput.value = '94';
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/94'); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 1000)); // Additional delay to allow UI to update
      const targetTypes = ['ghost', 'poison'];

      const typesEl = document.getElementById('types');

      assert.lengthOf(typesEl.children, 2);
      assert.sameMembers(['ghost', 'poison'], [...typesEl.children].map(el => el.innerText.trim().toLowerCase()));
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

`#search-input` の要素に無効なポケモンの名前を入力した状態で `#search-button` の要素をクリックした場合、`"Pokémon not found"` というテキストのアラートが表示されます。

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    let alertMessage;
    window.alert = (message) => alertMessage = message; // Override alert and store message

    const randomInvalidPokeId = crypto.randomUUID().substring(0, 6);

    searchInput.value = randomInvalidPokeId;
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/' + randomInvalidPokeId); // Fetch from proxy to simulate network delay

    if (!res.ok) {
      await new Promise(resolve => setTimeout(resolve, 2000)); // Additional delay to allow the alert to trigger

      assert.include(['pokémon not found', 'pokemon not found'], alertMessage?.trim().replace(/[.,?!]+$/g, '').toLowerCase());
    }
  } catch (err) {
    throw new Error(err);
  }
};
```


When the `#search-input` element contains a valid Pokemon id and the `#search-button` element is clicked, the UI should be filled with the correct data.

```js
async () => {
  try {
    const searchInput = document.getElementById('search-input');
    const searchButton = document.getElementById('search-button');
    let alertMessage;
    window.alert = (message) => alertMessage = message; // Override alert and store message

    const randomValidPokeId = String(Math.floor(Math.random() * 1025) + 1);

    searchInput.value = randomValidPokeId;
    searchInput.dispatchEvent(new Event('change'));
    searchButton.click();

    const res = await fetch('https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/' +  randomValidPokeId); // Fetch from proxy to simulate network delay

    if (res.ok) {
      await new Promise(resolve => setTimeout(resolve, 2000)); // Additional delay to allow UI to update

      const data = await res.json();
      const typesEl = document.getElementById('types');
      const actualTypes = data.types.map(typeSlot => typeSlot.type.name);

      assert.lengthOf(typesEl.children, actualTypes.length);
      assert.sameMembers(actualTypes, [...typesEl.children].map(el => el.innerText.trim().toLowerCase()));
    }
  } catch (err) {
    throw new Error(err);
  }
};
```

# --seed--

## --seed-contents--

```html

```

```css

```

```js

```

# --solutions--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      rel="icon"
      type="image/png"
      href="https://cdn.freecodecamp.org/universal/favicons/favicon.ico"
    />
    <title>Pokémon Search App</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <main>
      <img
        class="freecodecamp-logo"
        src="https://cdn.freecodecamp.org/platform/universal/fcc_primary.svg"
        alt="freeCodeCamp Logo"
      />
      <h1>Pokémon Search App</h1>
      <div class="container">
        <form role="search" id="search-form">
          <label for="search-input">Search for Pokémon Name or ID:</label>
          <input type="text" name="pokemon" id="search-input" required />
          <button id="search-button">Search</button>
        </form>
        <div class="output">
          <div class="top-container">
            <div class="name-and-id">
              <span id="pokemon-name"></span>
              <span id="pokemon-id"></span>
            </div>
            <div class="size">
              <span id="weight"></span>
              <span id="height"></span>
            </div>
            <div id="sprite-container" class="sprite-container"></div>
            <div id="types"></div>
          </div>
          <div class="bottom-container">
            <table>
              <tr>
                <th>Base</th>
                <th>Stats</th>
              </tr>
              <tr>
                <td>HP:</td>
                <td id="hp"></td>
              </tr>
              <tr>
                <td>Attack:</td>
                <td id="attack"></td>
              </tr>
              <tr>
                <td>Defense:</td>
                <td id="defense"></td>
              </tr>
              <tr>
                <td>Sp. Attack:</td>
                <td id="special-attack"></td>
              </tr>
              <tr>
                <td>Sp. Defense:</td>
                <td id="special-defense"></td>
              </tr>
              <tr>
                <td>Speed:</td>
                <td id="speed" class="speed"></td>
              </tr>
            </table>
          </div>
        </div>
      </div>
      <script src="./script.js"></script>
    </main>
  </body>
</html>
```

```css
/* CSS reset */

*,
*::before,
*::after {
  box-sizing: border-box;
}

* {
  margin: 0;
}

body {
  line-height: 1.5;
}

img {
  display: block;
}

/* Project styling */

body {
  height: 100vh;
  font-family: sans-serif;
  background-color: #1b1b32;
  color: #0a0a23;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.freecodecamp-logo {
  height: 30px;
  margin: 25px 0;
}

h1 {
  color: #f5f6f7;
  font-size: 1.7em;
  text-align: center;
}

.container {
  width: 325px;
  margin: 25px 0;
  background-color: #f5f6f7;
  border: 1px solid #f5f6f7;
  border-radius: 15px;
  box-shadow: 10px 10px 0px 0px rgba(223, 220, 220, 0.75);
}

.output,
#search-form {
  display: flex;
  justify-content: center;
}

#search-form {
  flex-wrap: wrap;
  margin: 10px 0;
  padding: 5px;
  border-radius: 8px 8px 0 0;
  gap: 10px;
}

label {
  align-self: center;
}

#search-input:focus-visible,
#search-button:focus-visible {
  outline: 3px solid #198eee;
}

#search-input {
  height: 40px;
  padding-left: 10px;
  width: 200px;
}

#search-button {
  padding: 14px 0;
  width: 80px;
  border-radius: 20px;
  text-align: center;
  background-color: #7f21ab;
  color: #f5f6f7;
  border: none;
}

.output {
  margin: 10px 0;
  padding: 5px;
  flex-direction: column;
  align-items: center;
}

.top-container,
.bottom-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  min-height: 325px;
}

.top-container {
  margin-bottom: 10px;
  padding: 10px;
  background-color: #f0f1f7;
}

.name-and-id {
  height: 28px;
  font-size: 1.1em;
  text-transform: capitalize;
  margin-bottom: 5px;
}

.size {
  height: 22px;
  font-size: 0.85rem;
}

.sprite-container {
  flex-grow: 2;
  display: flex;
  align-items: center;
  justify-content: center;
}

#sprite {
  width: 180px;
}

#types {
  min-height: 30px;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  gap: 5px;
}

.type {
  width: 66px;
  padding: 5px;
  font-size: 0.7rem;
  text-align: center;
  border-radius: 5px;
  background-color: red;
  text-transform: uppercase;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
  width: 100%;
  font-size: 1 rem;
  color: #f5f6f7;
  background-color: #7f21ab;
}

th:nth-child(even),
td:nth-child(even) {
  border-left: 5px solid #f5f6f7;
}

tr {
  border-bottom: 5px solid #f5f6f7;
}

td,
th {
  text-align: center;
  padding: 8px;
}

/* Special styling for Pokémon types */

.normal {
  background-color: #b7b7aa;
}

.fire {
  background-color: #ff6f52;
}

.water {
  background-color: #42a1ff;
}

.electric {
  background-color: #fecc33;
}

.grass {
  background-color: #78cc55;
}

.ice {
  background-color: #66ccfe;
}

.fighting {
  background-color: #d3887e;
}

.poison {
  background-color: #c68bb7;
}

.ground {
  background-color: #dfba52;
}

.flying {
  background-color: #8899ff;
}

.psychic {
  background-color: #ff66a3;
}

.bug {
  background-color: #aabb23;
}

.rock {
  background-color: #baaa66;
}

.ghost {
  background-color: #9995d0;
}

.dragon {
  background-color: #9e93f1;
}

.dark {
  background-color: #b59682;
}

.steel {
  background-color: #abaabb;
}

.fairy {
  background-color: #ed99ed;
}

@media screen and (min-width: 550px) {
  h1 {
    font-size: 2em;
  }

  .container {
    width: 450px;
  }

  #search-form,
  .top-container,
  .bottom-container {
    width: 95%;
  }

  .type {
    width: 75px;
  }
}
```

```js
const pokemonID = document.getElementById("pokemon-id");
const pokemonName = document.getElementById("pokemon-name");
const spriteContainer = document.getElementById("sprite-container");
const types = document.getElementById("types");
const height = document.getElementById("height");
const weight = document.getElementById("weight");
const hp = document.getElementById("hp");
const attack = document.getElementById("attack");
const defense = document.getElementById("defense");
const specialAttack = document.getElementById("special-attack");
const specialDefense = document.getElementById("special-defense");
const speed = document.getElementById("speed");
const searchForm = document.getElementById("search-form");
const searchInput = document.getElementById("search-input");

const getPokemon = async () => {
  try {
    const pokemonNameOrId = searchInput.value.toLowerCase();
    const response = await fetch(
      `https://pokeapi-proxy.freecodecamp.rocks/api/pokemon/${pokemonNameOrId}`,
    );
    const data = await response.json();

    // Set Pokémon info
    pokemonName.textContent = `${data.name.toUpperCase()}`;
    pokemonID.textContent = `#${data.id}`;
    weight.textContent = `Weight: ${data.weight}`;
    height.textContent = `Height: ${data.height}`;
    spriteContainer.innerHTML = `
      <img id="sprite" src="${data.sprites.front_default}" alt="${data.name} front default sprite">
    `;

    // Set stats
    hp.textContent = data.stats[0].base_stat;
    attack.textContent = data.stats[1].base_stat;
    defense.textContent = data.stats[2].base_stat;
    specialAttack.textContent = data.stats[3].base_stat;
    specialDefense.textContent = data.stats[4].base_stat;
    speed.textContent = data.stats[5].base_stat;

    // Set types
    types.innerHTML = data.types
      .map(
        (obj) => `<span class="type ${obj.type.name}">${obj.type.name}</span>`,
      )
      .join("");
  } catch (err) {
    resetDisplay();
    alert("Pokémon not found");
    console.log(`Pokémon not found: ${err}`);
  }
};

const resetDisplay = () => {
  const sprite = document.getElementById("sprite");
  if (sprite) sprite.remove();

  // reset stats
  pokemonName.textContent = "";
  pokemonID.textContent = "";
  types.innerHTML = "";
  height.textContent = "";
  weight.textContent = "";
  hp.textContent = "";
  attack.textContent = "";
  defense.textContent = "";
  specialAttack.textContent = "";
  specialDefense.textContent = "";
  speed.textContent = "";
};

searchForm.addEventListener("submit", (e) => {
  e.preventDefault();
  getPokemon();
});
```
