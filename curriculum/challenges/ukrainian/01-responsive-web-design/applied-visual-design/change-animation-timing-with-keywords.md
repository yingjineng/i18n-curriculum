---
id: 587d78a8367417b2b2512ae7
title: Змінити час анімації за допомогою ключових слів
challengeType: 0
videoUrl: 'https://scrimba.com/c/cJKvwCM'
forumTopicId: 301045
dashedName: change-animation-timing-with-keywords
---

# --description--

In CSS animations, the `animation-timing-function` property controls how quickly an animated element changes over the duration of the animation. If the animation is a car moving from point A to point B in a given time (your `animation-duration`), the `animation-timing-function` says how the car accelerates and decelerates over the course of the drive.

Існує певний набір готових ключових слів, які містять найпоширеніші завдання. Наприклад, якщо значення за замовчуванням - `ease`, то анімація починається повільно, на середині прискорюється і знову уповільнюється вкінці. Інші завдання відповідають за властивість `ease-out`, при якій анімація починається швидко і сповільнюються вкінці, властивість `ease-in`, де анімація починається повільно і прискорюється вкінці, та властивість `linear`, яка надає анімації постійну незмінну швидкість.

# --instructions--

До кожного елементу з id `ball1` та `ball2` додайте властивість `animation-timing-function`, та для `#ball1` встановіть властивість `linear`, а до `#ball2` додайте `ease-out`. Зверніть увагу на те, як по різному рухаються анімовані елементи, при чому анімація зупиняється одночасно, якщо властивість `animation-duration` кожного елемента встановлено на 2 секунди.

# --hints--

Значення властивості `animation-timing-function` елементів з id `ball1` має бути `linear`.

```js
const ballOne =document.querySelector('#ball1'); 
const ballOneStyle = window.getComputedStyle(ballOne); 

const ball1Animation = __helpers.removeWhiteSpace(ballOneStyle?.animationTimingFunction);
assert.isTrue(ball1Animation == 'linear' || ball1Animation == 'cubic-bezier(0,0,1,1)');
```

Значення властивості `animation-timing-function` для елементів з id `ball2` має бути `ease-out`.

```js
const ballTwo = document.querySelector('#ball2'); 
const ballTwoStyle = window.getComputedStyle(ballTwo); 

const ball2Animation = __helpers.removeWhiteSpace(ballTwoStyle?.animationTimingFunction);
assert.isTrue(ball2Animation == 'ease-out' || ball2Animation == 'cubic-bezier(0,0,0.58,1)');
```

# --seed--

## --seed-contents--

```html
<style>

  .balls {
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 {
    left:27%;

  }
  #ball2 {
    left:56%;

  }

  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }

</style>

<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```

# --solutions--

```html
<style>
  .balls {
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 {
    left:27%;
    animation-timing-function: linear;
  }
  #ball2 {
    left:56%;
    animation-timing-function: ease-out;
  }

  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```
