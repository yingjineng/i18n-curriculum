---
id: 587d778e367417b2b2512aab
title: Як покращити читабельність за допомогою контрасного тексту
challengeType: 0
videoUrl: 'https://scrimba.com/c/cKb3nCq'
forumTopicId: 301017
dashedName: improve-readability-with-high-contrast-text
---

# --description--

Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves your content's readability, but what exactly does "sufficient" mean?

В рекомендаціях Web Content Accessibility Guidelines (WCAG) пропонується виставляти коефіцієнт контрастності від 4.5 до 1 для звичайного тексту. Коефіцієнт вираховується шляхом порівняння відносної яскравості двох кольорів. Співвідношення варіюється від 1:1 для одного й того ж кольору (без контрасту) до 21:1 для білого на фоні чорного (найбільший контраст). Існує багато онлайн-засобів, які перевіряють контрастність та розраховують для вас цей коефіцієнт.

# --instructions--

Світло сірий текст на білому фоні в останньому пості блогу Кота Кампера зі співвідношенням коефіцієнта контрастності 1.5:1 ускладнює прочитання тексту. Змініть `color` тексту з наявного сірого (`#D3D3D3`) на темніший сірий (`#636363`), щоб покращити коефіцієнт контрастності до 6:1.

# --hints--

Ваш код повинен змінити текст `color` для `body` на темно-сірий.

```js
const body = document.querySelector('body');
const bodyColor = window.getComputedStyle(body).color; 
assert(bodyColor == 'rgb(99, 99, 99)');
```

Ваш код не повинен міняти колір фона `background-color` для `body`.

```js
const body = document.querySelector('body');
const backgroundColor = window.getComputedStyle(body).backgroundColor; 
assert.equal(backgroundColor , 'rgb(255, 255, 255)');
```

# --seed--

## --seed-contents--

```html
<head>
  <style>
  body {
    color: #D3D3D3;
    background-color: #FFF;
  }
  </style>
</head>
<body>
  <header>
    <h1>Deep Thoughts with Master Camper Cat</h1>
  </header>
  <article>
    <h2>A Word on the Recent Catnip Doping Scandal</h2>
    <p>The influence that catnip has on feline behavior is well-documented, and its use as an herbal supplement in competitive ninja circles remains controversial. Once again, the debate to ban the substance is brought to the public's attention after the high-profile win of Kittytron, a long-time proponent and user of the green stuff, at the Claw of Fury tournament.</p>
    <p>As I've stated in the past, I firmly believe a true ninja's skills must come from within, with no external influences. My own catnip use shall continue as purely recreational.</p>
  </article>
</body>
```

# --solutions--

```html
<head>
  <style>
  body {
    color: #636363;
    background-color: #FFF;
  }
  </style>
</head>
<body>
  <header>
    <h1>Deep Thoughts with Master Camper Cat</h1>
  </header>
  <article>
    <h2>A Word on the Recent Catnip Doping Scandal</h2>
    <p>The influence that catnip has on feline behavior is well-documented, and its use as an herbal supplement in competitive ninja circles remains controversial. Once again, the debate to ban the substance is brought to the public's attention after the high-profile win of Kittytron, a long-time proponent and user of the green stuff, at the Claw of Fury tournament.</p>
    <p>As I've stated in the past, I firmly believe a true ninja's skills must come from within, with no external influences. My own catnip use shall continue as purely recreational.</p>
  </article>
</body>
```
