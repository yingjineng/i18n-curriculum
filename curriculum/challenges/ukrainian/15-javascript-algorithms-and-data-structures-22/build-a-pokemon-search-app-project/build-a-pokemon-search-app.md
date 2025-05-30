---
id: 6555c1d3e11a1574434cf8b5
title: Створіть застосунок Pokémon Search
challengeType: 14
forumTopicId: 16003
dashedName: build-a-pokemon-search-app
---

# --description--

У цьому проєкті ви створите застосунок, який шукатиме покемонів за іменем або ID та відтворюватиме результати для користувача. Щоб отримати дані та зображення покемонів, використайте <a href="https://pokeapi-proxy.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">PokéAPI Proxy</a> від freeCodeCamp.

 **Примітка:** перші 13 кроків потрібно виконати у файлі `index.html`.

**Мета:** створити застосунок, функціонально схожий до <a href="https://pokemon-search-app.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://pokemon-search-app.freecodecamp.rocks</a>.

**Історія користувача:**

1. You should have an `input` element with an `id` of `"search-input"`, and is required.
1. Ви повинні мати елемент `button` з `id` зі значенням `"search-button"`.
1. Ви повинні мати елемент з `id` зі значенням `"pokemon-name"`.
1. Ви повинні мати елемент з `id` зі значенням `"pokemon-id"`.
1. Ви повинні мати елемент з `id` зі значенням `"weight"`.
1. Ви повинні мати елемент з `id` зі значенням `"height"`.
1. Ви повинні мати елемент з `id` зі значенням `"types"`.
1. Ви повинні мати елемент з `id` зі значенням `"hp"`.
1. Ви повинні мати елемент з `id` зі значенням `"attack"`.
1. Ви повинні мати елемент з `id` зі значенням `"defense"`.
1. Ви повинні мати елемент з `id` зі значенням `"special-attack"`.
1. Ви повинні мати елемент з `id` зі значенням `"special-defense"`.
1. Ви повинні мати елемент з `id` зі значенням `"speed"`.
1. Якщо елемент `#search-input` містить значення `Red` та натиснути на елемент `#search-button`, то має з’явитись попередження з текстом `"Pokémon not found"`.
1. Якщо елемент `#search-input` містить значення `Pikachu` та натиснути на елемент `#search-button`, то значеннями в елементах `#pokemon-name`, `#pokemon-id`, `#weight`, `#height`, `#hp`, `#attack`, `#defense`, `#special-attack`, `#special-defense` та `#speed` відповідно мають бути `PIKACHU`, `#25` або `25`, `Weight: 60` або `60`, `Height: 4` або `4`, `35`, `55`, `40`, `50`, `50` та `90`.
1. Якщо елемент `#search-input` містить значення `Pikachu` та натиснути на елемент `#search-button`, то на сторінку потрібно додати елемент `img` з `id` зі значенням `"sprite"` та `src` зі значенням спрайту покемона `front_default`.
1. Якщо елемент `#search-input` містить значення `Pikachu` та натиснути на елемент `#search-button`, то елемент `#types` повинен містити один внутрішній елемент зі значенням `ELECTRIC`. The `#types` element content should be cleared between searches.
1. Якщо елемент `#search-input` містить значення `94` та натиснути на елемент `#search-button`, то значеннями в елементах `#pokemon-name`, `#pokemon-id`, `#weight`, `#height`, `#hp`, `#attack`, `#defense`, `#special-attack`, `#special-defense` та `#speed` відповідно мають бути `GENGAR`, `#94` або `94`, `Weight: 405` або `405`, `Height: 15` або `15`, `60`, `65`, `60`, `130`, `75` та `110`.
1. Якщо елемент `#search-input` містить значення `94` та натиснути на елемент `#search-button`, то на сторінку потрібно додати елемент `img` з `id` зі значенням `sprite` та `src` зі значенням спрайту покемона `front_default`.
1. Якщо елемент `#search-input` містить значення `94` та натиснути на елемент `#search-button`, то елемент `#types` повинен містити два внутрішні елементи з текстовими значеннями `GHOST` та `POISON` відповідно. The `#types` element content should be cleared between searches.
1. When the `#search-input` element contains an invalid Pokemon name, and the `#search-button` element is clicked, an alert should appear with the text `"Pokémon not found"`.
1. Якщо елемент `#search-input` містить дійсний `id` Покемона та натиснути на елемент `#search-button`, то UI має бути заповненим правильними даними.

Виконайте історію користувача та пройдіть тести, наведені нижче, щоб завершити цей проєкт. Оформте за власним стилем. Щасливого програмування!

**Примітка:** при запуску тестів буде невелика затримка. Будь ласка, зачекайте декілька секунд, щоб тести завершились. Не оновлюйте сторінку під час виконання тестів.

# --hints--

Ви повинні мати елемент `input` з `id` зі значенням `"search-input"`. The `input` should be marked as required.

```js
const el = document.getElementById('search-input');
assert.strictEqual(el?.nodeName?.toLowerCase(), 'input');
assert.isTrue(el?.required);
```

Ви повинні мати елемент `button` з `id` зі значенням `"search-button"`.

```js
const el = document.getElementById('search-button');
assert.strictEqual(el?.nodeName?.toLowerCase(), 'button');
```

Ви повинні мати елемент з `id` зі значенням `"pokemon-name"`.

```js
const el = document.getElementById('pokemon-name');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"pokemon-id"`.

```js
const el = document.getElementById('pokemon-id');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"weight"`.

```js
const el = document.getElementById('weight');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"height"`.

```js
const el = document.getElementById('height');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"types"`.

```js
const el = document.getElementById('types');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"hp"`.

```js
const el = document.getElementById('hp');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"attack"`.

```js
const el = document.getElementById('attack');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"defense"`.

```js
const el = document.getElementById('defense');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"special-attack"`.

```js
const el = document.getElementById('special-attack');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"special-defense"`.

```js
const el = document.getElementById('special-defense');
assert.exists(el);
```

Ви повинні мати елемент з `id` зі значенням `"speed"`.

```js
const el = document.getElementById('speed');
assert.exists(el);
```

Якщо елемент `#search-input` містить значення `Red` та натиснути на елемент `#search-button`, то має з’явитись попередження з текстом `"Pokémon not found"`.

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

Якщо елемент `#search-input` містить значення `Pikachu` та натиснути на елемент `#search-button`, то значеннями в елементах `#pokemon-name`, `#pokemon-id`, `#weight`, `#height`, `#hp`, `#attack`, `#defense`, `#special-attack`, `#special-defense` та `#speed` відповідно мають бути `PIKACHU`, `#25` або `25`, `Weight: 60` або `60`, `Height: 4` або `4`, `35`, `55`, `40`, `50`, `50` та `90`.

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

Якщо елемент `#search-input` містить значення `Pikachu` та натиснути на елемент `#search-button`, то на сторінку потрібно додати елемент `img` з `id` зі значенням `"sprite"` та `src` зі значенням спрайту покемона `front_default`.

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

Якщо елемент `#search-input` містить значення `Pikachu` та натиснути на елемент `#search-button`, то елемент `#types` повинен містити один внутрішній елемент зі значенням `ELECTRIC`. Make sure the `#types` element content is cleared between searches.

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

Якщо елемент `#search-input` містить значення `94` та натиснути на елемент `#search-button`, то значеннями в елементах `#pokemon-name`, `#pokemon-id`, `#weight`, `#height`, `#hp`, `#attack`, `#defense`, `#special-attack`, `#special-defense` та `#speed` відповідно мають бути `GENGAR`, `#94` або `94`, `Weight: 405` або `405`, `Height: 15` або `15`, `60`, `65`, `60`, `130`, `75` та `110`.

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

Якщо елемент `#search-input` містить значення `94` та натиснути на елемент `#search-button`, то на сторінку потрібно додати елемент `img` з `id` зі значенням `"sprite"` та `src` зі значенням спрайту покемона `front_default`.

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

Якщо елемент `#search-input` містить значення `94` та натиснути на елемент `#search-button`, то елемент `#types` повинен містити два внутрішні елементи з текстовими значеннями `GHOST` та `POISON` відповідно. Make sure the `#types` element content is cleared between searches.

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

Якщо елемент `#search-input` містить недійсне ім’я покемона та натиснути на елемент `#search-button`, то має з’явитись попередження з текстом `"Pokémon not found"`.

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
