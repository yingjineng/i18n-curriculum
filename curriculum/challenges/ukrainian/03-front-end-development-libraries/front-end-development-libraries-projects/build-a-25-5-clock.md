---
id: bd7158d8c442eddfaeb5bd0f
title: Створіть годинник 25 + 5
challengeType: 3
forumTopicId: 301373
dashedName: build-a-25--5-clock
---

# --description--

**Note:** **React 18 has known incompatibilities with the tests for this project (see [issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922))**

**Мета:** створити застосунок, функціонально схожий до <a href="https://25--5-clock.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://25--5-clock.freecodecamp.rocks</a>.

Виконайте історію користувача та пройдіть тести. Використовуйте необхідні вам бібліотеки або API. Оформіть за вашим власним стилем.

Для виконання цього проєкту можна використати різне поєднання HTML, JavaScript, CSS, Bootstrap, SASS, React, Redux та jQuery. Потрібно використати фронтенд фреймворк (наприклад, React), оскільки цей розділ стосується їх вивчення. Ми не рекомендуємо використовувати інші технології та ресурси, що не були вказані вище, але ви можете застосовувати їх на власний розсуд. Ми розглядаємо використання інших фронтенд фреймворків, серед яких Angular та Vue, але наразі вони не підтримуються. Ми візьмемо до уваги і спробуємо виправити всі звіти, що використовують запропонований технологічний стек у цьому проєкті. Щасливого програмування!

**Історія користувача №1:** я бачу елемент з `id="break-label"`, що містить рядок (наприклад, «Break Length»).

**Історія користувача №2:** я бачу елемент з `id="session-label"`, що містить рядок (наприклад, «Session Length»).

**Історія користувача №3:** я бачу два активні елементи з відповідними ID: `id="break-decrement"` та `id="session-decrement"`.

**Історія користувача №4:** я бачу два активні елементи з відповідними ID: `id="break-increment"` та `id="session-increment"`.

**Історія користувача №5:** я бачу елемент з відповідним `id="break-length"`, що за замовчуванням (при завантаженні) показує значення 5.

**Історія користувача №6:** я бачу елемент з відповідним `id="session-length"`, що за замовчуванням показує значення 25.

**Історія користувача №7:** я бачу елемент з відповідним `id="timer-label"`, що містить рядок, який позначає ініціалізацію сеансу (наприклад, «Session»).

**Історія користувача №8:** я бачу елемент з відповідним `id="time-left"`. ПРИМІТКА: зупинене чи активне, значення цього поля завжди має знаходитись у форматі `mm:ss` (тобто 25:00).

**Історія користувача №9:** я бачу активний елемент з відповідним `id="start_stop"`.

**Історія користувача №10:** я бачу активний елемент з відповідним `id="reset"`.

**Історія користувача №11:** якщо натиснути елемент з id зі значенням `reset`, то будь-який запущений таймер зупиниться, значення в межах `id="break-length"` повернеться до `5`, значення в межах `id="session-length"` повернеться до 25, а елемент в `id="time-left"` повернеться до початкового стану.

**Історія користувача №12:** коли я натискаю на елемент з id зі значенням `break-decrement`, то значення в межах `id="break-length"` зменшується на 1 та я бачу оновлене значення.

**Історія користувача №13:** коли я натискаю на елемент з id зі значенням `break-increment`, то значення в межах `id="break-length"` збільшується на 1 та я бачу оновлене значення.

**Історія користувача №14:** коли я натискаю на елемент з id зі значенням `session-decrement`, то значення в межах `id="session-length"` зменшується на 1 та я бачу оновлене значення.

**Історія користувача №15:** коли я натискаю на елемент з id зі значенням `session-increment`, то значення в межах `id="session-length"` збільшується на 1 та я бачу оновлене значення.

**Історія користувача №16:** я не можу встановити тривалість сеансу або перерви на &lt;= 0.

**Історія користувача №17:** я не можу встановити тривалість сеансу або перерви на > 60.

**Історія користувача №18:** коли я вперше натискаю елемент з `id="start_stop"`, то таймер запуститься з поточного значення в `id="session-length"`, навіть якщо значення більше чи менше за початкове значення 25.

**Історія користувача №19:** якщо таймер запущений, то елемент з id зі значенням `time-left` має відтворити залишковий час в форматі `mm:ss` (зменшуючись на 1 та оновлюючи дисплей кожні 1000 мс).

**Історія користувача №20:** якщо таймер запущений та я натискаю елемент з `id="start_stop"`, то відлік часу зупиниться.

**Історія користувача №21:** якщо таймер зупинений та я натискаю елемент з `id="start_stop"`, то відлік часу відновиться з моменту, на якому був зупинений.

**Історія користувача №22:** якщо відлік сеансу досягає нуля (ПРИМІТКА: таймер ПОВИНЕН досягти 00:00) та починається новий відлік, то елемент з id зі значенням `timer-label` має відтворити рядок, що вказує початок перерви.

**Історія користувача №23:** якщо відлік сеансу досягає нуля (ПРИМІТКА: таймер ПОВИНЕН досягти 00:00), то починається новий відлік перерви, що рахується від поточного значення в елементі `id="break-length"`.

**Історія користувача №24:** якщо відлік перерви досягає нуля (ПРИМІТКА: таймер ПОВИНЕН досягти 00:00) та починається новий відлік, то елемент з id зі значенням `timer-label` має відтворити рядок, що вказує на початок сеансу.

**Історія користувача №25:** якщо відлік перерви досягає нуля (ПРИМІТКА: таймер ПОВИНЕН досягти 00:00), то починається новий відлік сеансу, що рахується від поточного значення в елементі `id="session-length"`.

**Історія користувача №26:** якщо відлік досягає нуля (ПРИМІТКА: таймер ПОВИНЕН досягти 00:00), то має прозвучати звук, що означає вичерпаний час. Він має використати HTML5-елемент `audio` та мати відповідний `id="beep"`.

**Історія користувача №27:** аудіоелемент з `id="beep"` має тривати 1 секунду або більше.

**Історія користувача №28:** аудіоелемент з id зі значенням `beep` має зупинитись та перемотатись напочаток, якщо натиснути елемент з id зі значенням `reset`.

Ви можете створити свій проєкт, <a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">використавши цей шаблон CodePen</a> та натиснувши `Save`. If you prefer to use another environment, then put this `<script>` tag into the body of your `index.html` file: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

Як тільки закінчите, надайте посилання на свій проєкт з усіма пройденими тестами.

# --solutions--

```js
// solution required
```
