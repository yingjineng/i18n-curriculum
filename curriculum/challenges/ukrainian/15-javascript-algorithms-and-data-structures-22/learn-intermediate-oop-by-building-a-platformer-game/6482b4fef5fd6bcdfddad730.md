---
id: 6482b4fef5fd6bcdfddad730
title: Крок 12
challengeType: 0
dashedName: step-12
---

# --description--

Наступний крок — визначення деяких характеристик головного гравця гри.

Почніть зі створення нового `class` під назвою `Player`.

# --hints--

`Player` має бути класом.

```js
assert(
  typeof Player === 'function' 
);
```

Використайте ключове слово `class`.

```js
assert.match(code, /^\s*class/m);
```

Ви повинні створити новий клас під назвою `Player`

```js
assert.match(code, /class\s+Player\s*{\s*}\s*/);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Learn Intermediate OOP by Building a Platformer Game</title>
    <link rel="stylesheet" href="./styles.css" />
  </head>
  <body>
    <div class="start-screen">
      <h1 class="main-title">freeCodeCamp Code Warrior</h1>
      <p class="instructions">
        Help the main player navigate to the yellow checkpoints.
      </p>
      <p class="instructions">
        Use the keyboard arrows to move the player around.
      </p>
      <p class="instructions">You can also use the spacebar to jump.</p>

      <div class="btn-container">
        <button class="btn" id="start-btn">Start Game</button>
      </div>
    </div>

    <div class="checkpoint-screen">
      <h2>Congrats!</h2>
      <p>You reached the last checkpoint.</p>
    </div>

    <canvas id="canvas"></canvas>

    <script src="./script.js"></script>
  </body>
</html>

```

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --main-bg-color: #0a0a23;
  --section-bg-color: #ffffff;
  --golden-yellow: #feac32;
}

body {
  background-color: var(--main-bg-color);
}

.start-screen {
  background-color: var(--section-bg-color);
  width: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
  border-radius: 30px;
  padding: 20px;
  padding-bottom: 5px;
}

.main-title {
  text-align: center;
}

.instructions {
  text-align: center;
  font-size: 1.2rem;
  margin: 15px;
  line-height: 2rem;
}

.btn {
  cursor: pointer;
  width: 100px;
  margin: 10px;
  color: #0a0a23;
  font-size: 18px;
  background-color: var(--golden-yellow);
  background-image: linear-gradient(#fecc4c, #ffac33);
  border-color: var(--golden-yellow);
  border-width: 3px;
}

.btn:hover {
  background-image: linear-gradient(#ffcc4c, #f89808);
}

.btn-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.checkpoint-screen {
  position: absolute;
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  width: 100%;
  text-align: center;
  background-color: var(--section-bg-color);
  border-radius: 20px;
  padding: 10px;
  display: none;
}

#canvas {
  display: none;
}

@media (min-width: 768px) {
  .start-screen {
    width: 60%;
    max-width: 700px;
  }

  .checkpoint-screen {
    max-width: 300px;
  }
}

```

```js
const startBtn = document.getElementById("start-btn");
const canvas = document.getElementById("canvas");
const startScreen = document.querySelector(".start-screen");
const checkpointScreen = document.querySelector(".checkpoint-screen");
const checkpointMessage = document.querySelector(".checkpoint-screen > p");
const ctx = canvas.getContext("2d");
canvas.width = innerWidth;
canvas.height = innerHeight;
const gravity = 0.5;
let isCheckpointCollisionDetectionActive = true;

const proportionalSize = (size) => {
  return innerHeight < 500 ? Math.ceil((size / 500) * innerHeight) : size;
}

--fcc-editable-region--

--fcc-editable-region--

```
