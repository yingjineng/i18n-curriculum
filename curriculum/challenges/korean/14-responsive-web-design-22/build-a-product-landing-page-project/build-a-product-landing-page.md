---
id: 587d78af367417b2b2512b04
title: 제품 랜딩 페이지 만들기
challengeType: 14
forumTopicId: 301144
dashedName: build-a-product-landing-page
---

# --description--

**목표:** <a href="https://product-landing-page.freecodecamp.rocks" target="_blank" rel="noopener noreferrer nofollow">https://product-landing-page.freecodecamp.rocks</a>를 참고하여 기능적으로 유사한 페이지를 구축하세요. **이 데모 프로젝트를 복사하지 마세요.**.

**유저 스토리:**

1. 제품 랜딩 페이지에는 `id="header"` 속성이 있는 `header` 요소가 있어야 합니다.
1. `<header>` 요소 내에 있는 `id="header-img"`에 해당하는 이미지를 볼 수 있습니다. (여기에는 로고 이미지가 적합합니다.)
1. `#header` 요소 안에 `id="nav-bar"`에 해당하는 `nav` 요소를 볼 수 있습니다.
1. `nav` 요소 안에 클래스가 `nav-link`인 클릭할 수 있는 요소가 최소 세 개 있습니다.
1. `nav` 요소 안에 있는 `.nav-link` 버튼을 클릭하면, 랜딩 페이지의 해당 섹션으로 이동하게 됩니다.
1. `id="video"`인 제품 비디오를 임베드된 상태로 시청할 수 있습니다.
1. 당신의 랜딩 페이지에는 `id="form"`에 해당하는 `form` 요소가 있습니다.
1. 폼 안에는 `id="email"`인 `input` 필드가 있어서 이메일 주소를 입력할 수 있습니다.
1. `#email` 입력 필드에는 사용자가 필드의 용도를 알 수 있도록 placeholder 텍스트가 있어야 합니다.
1. `#email` 입력 필드는 HTML5 검증을 사용하여 입력된 텍스트가 이메일 주소인지 확인합니다.
1. 폼 안에는 `id="submit"`인 제출 `input` 요소가 있습니다.
1. 당신이 `#submit` 요소를 클릭하면 이메일이 정적 페이지(이 모의 URL을 사용하세요: `https://www.freecodecamp.com/email-submit`)로 제출됩니다.
1. 내비게이션 바는 항상 뷰포트의 상단에 있어야 합니다.
1. 당신의 제품 랜딩 페이지에는 최소한 하나의 미디어 쿼리가 있어야 합니다.
1. 당신의 제품 랜딩 페이지는 최소한 한 번 이상 CSS 플렉스박스를 사용해야 합니다.

아래의 사용자 스토리를 충족시키고 모든 테스트를 통과하여 이 프로젝트를 완료하세요. 자신만의 개성을 담아 디자인을 꾸며보세요. 즐거운 코딩 하세요!

**참고:** 스타일시트를 연결하고 CSS를 적용하려면 HTML에 `<link rel="stylesheet" href="styles.css">`를 추가하세요.

# --hints--

`id`가 헤더인 `header` 요소를 포함해야 합니다.

```js
const el = document.getElementById('header')
assert(!!el && el.tagName === 'HEADER')
```

`img` 요소에는 `header-img`라는 `id`가 있어야 합니다.

```js
const el = document.getElementById('header-img')
assert(!!el && el.tagName === 'IMG')
```

`#header-img`는 `#header`의 자손이어야 합니다.

```js
const els = document.querySelectorAll('#header #header-img')
assert(els.length > 0)
```

`#header-img`에는 `src` 속성이 있어야 합니다.

```js
const el = document.getElementById('header-img')
assert(!!el && !!el.src)
```

`#header-img`의 `src` 값은 유효한 URL(즉, `http`로 시작하는) 이어야 합니다.

```js
const el = document.getElementById('header-img')
assert(!!el && /^http/.test(el.src))
```

`nav` 요소에는 `nav-bar`라는 `id`가 있어야 합니다.

```js
const el = document.getElementById('nav-bar')
assert(!!el && el.tagName === 'NAV')
```

`#nav-bar`는 `#header`의 자손이어야 합니다.

```js
const els = document.querySelectorAll('#header #nav-bar')
assert(els.length > 0)
```

`#nav-bar` 안에 최소한 3개의 `.nav-link` 요소가 있어야 합니다.

```js
const els = document.querySelectorAll('#nav-bar .nav-link')
assert(els.length >= 3)
```

각 `.nav-link` 요소는 `href` 속성을 가져야 합니다.

```js
const els = document.querySelectorAll('.nav-link')
els.forEach(el => {
  if (!el.href) assert(false)
})
assert(els.length > 0)
```

각 `.nav-link` 요소는 랜딩 페이지의 해당 요소에 연결되어야 합니다 (다른 요소의 id 값을 가진 `href` 값을 가져야 함. 예: `#footer`).

```js
const els = document.querySelectorAll('.nav-link')
els.forEach(el => {
  const linkDestination = el.getAttribute('href').slice(1)
  if (!document.getElementById(linkDestination)) assert(false)
})
assert(els.length > 0)
```

`video` 또는 `iframe` 요소를 `video`라는 `id` 값으로 가져야 합니다.

```js
const el = document.getElementById('video')
assert(!!el && (el.tagName === 'VIDEO' || el.tagName === 'IFRAME'))
```

`#video`는 `src` 속성을 가져야 합니다.

```js
let el = document.getElementById('video')
const sourceNode = el.children;
let sourceElement = null;
if (sourceNode.length) {
  sourceElement = [...video.children].filter(el => el.localName === 'source')[0];
}
if (sourceElement) {
  el = sourceElement;
}
assert(el.hasAttribute('src'));
```

`form` 요소는 `form`이라는 `id` 값을 가져야 합니다.

```js
const el = document.getElementById('form')
assert(!!el && el.tagName === 'FORM')
```

`input` 요소는 `email`이라는 `id` 값을 가져야 합니다.

```js
const el = document.getElementById('email')
assert(!!el && el.tagName === 'INPUT')
```

`#email`은 `#form`의 자손이어야 합니다.

```js
const els = document.querySelectorAll('#form #email')
assert(els.length > 0)
```

`#email`은 placeholder 텍스트를 가진 `placeholder` 속성을 가져야 합니다.

```js
const el = document.getElementById('email')
assert(!!el && !!el.placeholder && el.placeholder.length > 0)
```

`#email`은 HTML5 유효성 검사를 사용하도록 `type`을 `email`로 설정해야 합니다.

```js
const el = document.getElementById('email')
assert(!!el && el.type === 'email')
```

`input` 요소는 `submit`이라는 `id` 값을 가져야 합니다.

```js
const el = document.getElementById('submit')
assert(!!el && el.tagName === 'INPUT')
```

`#submit`은 `#form`의 자손이어야 합니다.

```js
const els = document.querySelectorAll('#form #submit')
assert(els.length > 0)
```

`#submit`은 `type`이 `submit`이어야 합니다.

```js
const el = document.getElementById('submit')
assert(!!el && el.type === 'submit')
```

`#form`은 `action` 속성에 `https://www.freecodecamp.com/email-submit` 값을 가져야 합니다.

```js
const el = document.getElementById('form')
assert(!!el && el.action === 'https://www.freecodecamp.com/email-submit')
```

`#email`은 `name` 속성에 `email` 값을 가져야 합니다.

```js
const el = document.getElementById('email')
assert(!!el && el.name === 'email')
```

`#nav-bar`은 항상 뷰포트의 상단에 위치해야 합니다.

```js
(async () => {
  const timeout = (milliseconds) => new Promise((resolve) => setTimeout(resolve, milliseconds));

  const header = document.getElementById('header');
  const headerChildren = header.children;
  const navbarCandidates = [header, ...headerChildren];

  // Return smallest top position of all navbar candidates
  const getNavbarPosition = (candidates = []) => {
    return candidates.reduce(
      (min, candidate) =>
        Math.min(min, Math.abs(candidate?.getBoundingClientRect().top)),
      Infinity
    );
  };
  assert.approximately(
    getNavbarPosition(navbarCandidates),
    0,
    15,
    '#header or one of its children should be at the top of the viewport '
  );

  window.scroll(0, 500);
  await timeout(1);

  assert.approximately(
    getNavbarPosition(navbarCandidates),
    0,
    15,
    '#header or one of its children should be at the top of the ' +
      'viewport even after scrolling '
  );

  window.scroll(0, 0);
})();
```

제품 랜딩 페이지는 최소한 하나의 미디어 쿼리를 사용해야 합니다.

```js
const htmlSourceAttr = Array.from(document.querySelectorAll('source')).map(el => el.getAttribute('media'))
const cssCheck = new __helpers.CSSHelp(document).getCSSRules('media')
assert(cssCheck.length > 0 || htmlSourceAttr.length > 0);
```

제품 랜딩 페이지는 CSS Flexbox를 최소한 한 번 이상 사용해야 합니다.

```js
const hasFlex = (rule) => ["flex", "inline-flex"].includes(rule.style?.display)
const stylesheet = new __helpers.CSSHelp(document).getStyleSheet()
const cssRules = new __helpers.CSSHelp(document).styleSheetToCssRulesArray(stylesheet)
const mediaRules = new __helpers.CSSHelp(document).getCSSRules('media')
const usesFlex = cssRules.find(rule => hasFlex(rule))
const usesFlexMedia = mediaRules.find(mediaRule => {
  return [...mediaRule.cssRules].find(rule => hasFlex(rule))
})
assert(usesFlex || usesFlexMedia)
```

# --seed--

## --seed-contents--

```html

```

```css

```

# --solutions--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="stylesheet" href="styles.css" />
    <title>Product Landing Page</title>
  </head>
  <body>
    <header id="header">
      <nav id="nav-bar">
        <img
          id="header-img"
          src="https://upload.wikimedia.org/wikipedia/commons/3/39/Pokeball.PNG"
          max-height="50px"
        />
        <a href="#Features" class="nav-link">Features</a> |
        <a href="#Video" class="nav-link">See our facility!</a> |
        <a href="#Pricing" class="nav-link">Purchase</a>
        <hr />
      </nav>
    </header>
    <main>
      <h1>
        Pokemon Daycare Service
      </h1>
      <section id="Features">
        <h2>What we offer</h2>
        <div class="flex-here">
          <div class="flex-left">
            <img
              id="bullet"
              src="https://upload.wikimedia.org/wikipedia/commons/3/39/Pokeball.PNG"
              max-height="25px"
            />
          </div>
          <div class="flex-right">Guaranteed friendly and loving staff!</div>
        </div>
        <div class="flex-here">
          <div class="flex-left">
            <img
              id="bullet"
              src="https://upload.wikimedia.org/wikipedia/commons/3/39/Pokeball.PNG"
              max-height="25px"
            />
          </div>
          <div class="flex-right">
            Comfortable environment for Pokemon to explore and play!
          </div>
        </div>
        <div class="flex-here">
          <div class="flex-left">
            <img
              id="bullet"
              src="https://upload.wikimedia.org/wikipedia/commons/3/39/Pokeball.PNG"
              max-height="25px"
            />
          </div>
          <div class="flex-right">
            Multiple membership plans to fit your lifestyle!
          </div>
        </div>
      </section>
      <section id="Video">
        <h2>Check us out!</h2>
        A sneak peek into our facility:
        <br />
        <iframe
          id="video"
          width="520"
          height="347"
          src="https://www.youtube.com/embed/Nw-ksH2r6AQ"
          frameborder="0"
          allowfullscreen
          alt="A video tour of our facility"
        >
        </iframe>
      </section>
      <section id="Pricing">
        <h2>Membership Plans</h2>
        <div class="flex-mem">
          <div class="flex-mem-box">
            <font size="+2">Basic Membership</font><br />
            <ul>
              <li>One Pokemon</li>
              <li>Food and berries provided</li>
            </ul>
            <em>$9.99/month</em>
          </div>
          <div class="flex-mem-box">
            <font size="+2">Silver Membership</font><br />
            <ul>
              <li>Up to Three Pokemon</li>
              <li>Food and berries provided</li>
              <li>Grooming and accessories included</li>
            </ul>
            <em>$19.99/month</em>
          </div>
          <div class="flex-mem-box">
            <font size="+2">Gold Membership</font><br />
            <ul>
              <li>Up to six Pokemon!</li>
              <li>Food and berries provided</li>
              <li>Grooming and accessories included</li>
              <li>Personal training for each Pokemon</li>
              <li>Breeding and egg hatching</li>
            </ul>
            <em>$29.99/month</em>
          </div>
        </div>
      </section>
      <form id="form" action="https://www.freecodecamp.com/email-submit">
        <p>Sign up for our newsletter!</p>
        <label for="email"><p>Email:</p><input name="email" id="email" type="email" placeholder="johnsmith@email.com" required></label>
        <input type="submit" id="submit">
      </form>
      <footer>
        <a href="../">Return to Project List</a> |
        <a href="https://www.nhcarrigan.com">Return to HomePage</a>
      </footer>
    </main>
  </body>
</html>
```

```css
body {
  background-color: #3a3240;
  color: white;
}
main {
  max-width: 750px;
  margin: 50px auto;
}
input {
  background-color: #92869c;
}
a:not(.nav-link) {
  color: white;
}
#header-img {
  max-height: 25px;
}
#nav-bar {
  position: fixed;
  width: 100%;
  text-align: center;
  top: 0%;
  background-color: #92869c;
}
h1 {
  text-align: center;
}
body {
  text-align: center;
}
footer {
  text-align: center;
}
#bullet {
  max-height: 25px;
}
.flex-here {
  display: flex;
  justify-content: center;
}
.flex-left {
  height: 25px;
}
.flex-mem {
  display: flex;
  justify-content: center;
}
.flex-mem-box {
  background-color: #92869c;
  border-color: black;
  border-width: 5px;
  border-style: solid;
  margin: 10px;
  padding: 10px;
  color: black;
}
@media (max-width: 350px) {
  #video {
    width: 300;
    height: 200;
  }
}
```
