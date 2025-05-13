---
id: bd7158d8c242eddfaeb5bd13
title: 构建个人作品集
challengeType: 25
dashedName: build-a-personal-portfolio
demoType: onClick
---

# --description--

完成以下用户故事并通过所有测试以完成本实验。

**用户需求：**

1. 你的作品集应有一个 `id` 为 `welcome-section` 的欢迎部分。
2. 欢迎部分应包含一个带有文本的 `h1` 元素。
3. 你的作品集应有一个 `id` 为 `project-section` 的项目部分。
4. 项目部分应包含至少一个 `class` 为 `project-tile` 的元素用于展示项目。
5. 项目部分应至少包含一个指向项目的链接。
6. 你的作品集应有一个 `id` 为 `navbar` 的导航栏。
7. 导航栏应至少包含一个可点击跳转到页面不同部分的链接。
8. 你的作品集应有一个 `id` 为 `profile-link` 的链接，点击后在新标签页打开你的 GitHub 或 freeCodeCamp 个人主页。
9. 你的作品集应至少包含一个媒体查询。
10. 欢迎部分的高度应等于视口高度。
11. 导航栏应始终位于视口顶部。

**注意：** 请确保在 HTML 中链接样式表并应用 CSS。

# --hints--

你的作品集应该有一个 `id` 为 `welcome-section` 的欢迎部分。

```js
const el = document.getElementById('welcome-section');
assert.isNotNull(el);
```

你的 `#welcome-section` 元素应该包含一个 `h1` 元素。

```js
assert.isAbove(
  document.querySelectorAll('#welcome-section h1').length,
  0,
  'Welcome section should contain an h1 element '
);
```

在 `#welcome-section` 元素中，你不应该有任何空的 `h1` 元素。

```js
assert.isAbove(
  document.querySelectorAll('#welcome-section h1')?.[0]?.innerText?.length,
  0,
  'h1 element in welcome section should contain your name or camper ' + 'name '
);
```

你的作品集应该有一个 `id` 为 `project-section` 的“项目”部分。

```js
const el = document.getElementById('project-section');
assert.isNotNull(el);
```

你的作品集应该包含至少一个 class 为 `project-tile` 的元素。

```js
assert.isAbove(
  document.querySelectorAll('#project-section .project-tile').length,
  0
);
```

你的 `#project-section` 元素应该包含至少一个 `a` 元素。

```js
assert.isAbove(document.querySelectorAll('#project-section a').length, 0);
```

你的作品集应该有一个 `id` 为 `navbar` 的导航栏。

```js
const el = document.getElementById('navbar');
assert.isNotNull(el);
```

你的 `#navbar` 元素应该包含至少一个 `a` 元素，其 `href` 属性以 `#` 开头。

```js
const links = [...document.querySelectorAll('#navbar a')].filter(
  nav => (nav?.getAttribute('href') || '').substring(0, 1) === '#'
);

assert.isAbove(links.length, 0, 'Navbar should contain an anchor link ');
```

你的作品集应该有一个 `id` 为 `profile-link` 的 `a` 元素。

```js
const el = document.getElementById('profile-link');
assert.isNotNull(el);
assert.strictEqual(el.tagName, 'A');
```

你的 `#profile-link` 元素应该有一个值为 `_blank` 的 `target` 属性。

```js
const el = document.getElementById('profile-link');
assert.isNotNull(el);
assert.strictEqual(el.target, '_blank');
```

你的作品集应该至少有一个媒体查询。

```js
const htmlSourceAttr = Array.from(document.querySelectorAll('source')).map(el => el.getAttribute('media'))
const cssCheck = new __helpers.CSSHelp(document).getCSSRules('media')
assert.isTrue(cssCheck.length > 0 || htmlSourceAttr.length > 0);
```

你的 `#navbar` 元素应该始终位于视口的顶部。

```js
(async () => {
  const timeout = milliseconds =>
    new Promise(resolve => setTimeout(resolve, milliseconds));

  const navbar = document.getElementById('navbar');
  assert.approximately(
    navbar?.getBoundingClientRect().top,
    0,
    15,
    "Navbar's parent should be body and it should be at the top of " +
      'the viewport '
  );

  window.scroll(0, 500);

  await timeout(1);

  assert.approximately(
    navbar?.getBoundingClientRect().top,
    0,
    15,
    'Navbar should be at the top of the viewport even after ' + 'scrolling '
  );
  window.scroll(0, 0);
})();
```

# --seed--

## --seed-contents--

```html
<!doctype html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>个人作品集</title>
  </head>
  <body></body>
</html>
```

```css

```

# --solutions--

```html
<!doctype html>
<html>
  <head>
    <link rel="stylesheet" href="styles.css" />
    <link
      rel="stylesheet"
      href="https://use.fontawesome.com/releases/v5.15.4/css/all.css"
      integrity="sha384-DyZ88mC6Up2uqS4h/KRgHuoeGwBcD4Ng9SiP4dIRy0EXTlnuz47vAwmeGwVChigm"
      crossorigin="anonymous"
    />
    <link
      href="https://fonts.googleapis.com/css?family=Poppins:200i,300,400&display=swap"
      rel="stylesheet"
    />
    <link
      href="https://fonts.googleapis.com/css?family=Raleway:700&display=swap"
      rel="stylesheet"
    />
  </head>

  <body>
    <!-- 导航栏开始 -->

    <nav id="navbar" class="nav">
      <ul class="nav-list">
        <li>
          <a href="#welcome-section">关于</a>
        </li>
        <li>
          <a href="#project-section">作品</a>
        </li>
        <li>
          <a href="#contact">联系</a>
        </li>
      </ul>
    </nav>

    <!-- 导航栏结束 -->

    <!-- 欢迎部分开始 -->

    <section id="welcome-section" class="welcome-section">
      <h1>你好，我是 Mimic</h1>
      <p>一名前端开发者</p>
    </section>

    <!-- 欢迎部分结束 -->

    <!-- 项目部分开始 -->

    <section id="project-section" class="projects-section">
      <h2 class="projects-section-header">以下是我的部分项目</h2>

      <div class="projects-grid">
        <a
          href="https://codepen.io/freeCodeCamp/full/zNqgVx"
          target="_blank"
          class="project project-tile"
        >
          <img
            class="project-image"
            src="https://cdn.freecodecamp.org/testable-projects-fcc/images/tribute.jpg"
            alt="项目"
          />
          <p class="project-title">
            <span class="code">&lt;</span>
            致敬页面
            <span class="code">&#47;&gt;</span>
          </p>
        </a>
        <a
          href="https://codepen.io/freeCodeCamp/full/qRZeGZ"
          target="_blank"
          class="project project-tile"
        >
          <img
            class="project-image"
            src="https://cdn.freecodecamp.org/testable-projects-fcc/images/random-quote-machine.png"
            alt="项目"
          />
          <p class="project-title">
            <span class="code">&lt;</span>
            随机名言机
            <span class="code">&#47;&gt;</span>
          </p>
        </a>
        <a
          href="https://codepen.io/freeCodeCamp/full/wgGVVX"
          target="_blank"
          class="project project-tile"
        >
          <img
            class="project-image"
            src="https://cdn.freecodecamp.org/testable-projects-fcc/images/calc.png"
            alt="项目"
          />
          <p class="project-title">
            <span class="code">&lt;</span>
            JavaScript 计算器
            <span class="code">&#47;&gt;</span>
          </p>
        </a>
        <a
          href="https://codepen.io/freeCodeCamp/full/mVEJag"
          target="_blank"
          class="project project-tile"
        >
          <img
            class="project-image"
            src="https://cdn.freecodecamp.org/testable-projects-fcc/images/map.jpg"
            alt="项目"
          />
          <p class="project-title">
            <span class="code">&lt;</span>
            全球地图数据
            <span class="code">&#47;&gt;</span>
          </p>
        </a>
        <a
          href="https://codepen.io/freeCodeCamp/full/wGqEga"
          target="_blank"
          class="project project-tile"
        >
          <img
            class="project-image"
            src="https://cdn.freecodecamp.org/testable-projects-fcc/images/wiki.png"
            alt="项目"
          />
          <p class="project-title">
            <span class="code">&lt;</span>
            维基百科浏览器
            <span class="code">&#47;&gt;</span>
          </p>
        </a>
        <a
          href="https://codepen.io/freeCodeCamp/full/KzXQgy"
          target="_blank"
          class="project project-tile"
        >
          <img
            class="project-image"
            src="https://cdn.freecodecamp.org/testable-projects-fcc/images/tic-tac-toe.png"
            alt="项目"
          />
          <p class="project-title">
            <span class="code">&lt;</span>
            井字棋游戏
            <span class="code">&#47;&gt;</span>
          </p>
        </a>
      </div>

      <a
        href="https://codepen.io/FreeCodeCamp/"
        class="btn btn-show-all"
        target="_blank"
        >查看全部<i class="fas fa-chevron-right"></i
      ></a>
    </section>

    <!-- 项目部分结束 -->

    <!-- 联系部分开始 -->

    <section id="contact" class="contact-section">
      <div class="contact-section-header">
        <h2>让我们一起合作吧……</h2>
        <p>你喜欢喝什么咖啡？</p>
      </div>
      <div class="contact-links">
        <a
          href="https://facebook.com/freecodecamp"
          target="_blank"
          class="btn contact-details"
          ><i class="fab fa-facebook-square"></i> Facebook</a
        >
        <a
          id="profile-link"
          href="https://github.com/freecodecamp"
          target="_blank"
          class="btn contact-details"
          ><i class="fab fa-github"></i> GitHub</a
        >
        <a
          href="https://twitter.com/freecodecamp"
          target="_blank"
          class="btn contact-details"
          ><i class="fab fa-twitter"></i> Twitter</a
        >
        <a href="mailto:example@example.com" class="btn contact-details"
          ><i class="fas fa-at"></i> 发送邮件</a
        >
        <a href="tel:555-555-5555" class="btn contact-details"
          ><i class="fas fa-mobile-alt"></i> 拨打电话</a
        >
      </div>
    </section>

    <!-- 联系部分结束 -->

    <!-- 页脚部分开始 -->

    <footer>
      <p>
        **这只是一个虚构的作品集。所有项目和联系方式均为示例。
      </p>
      <p>
        &copy; 为
        <a href="https://www.freecodecamp.org/" target="_blank"
          >freeCodeCamp <i class="fab fa-free-code-camp"></i
        ></a>
        创建
      </p>
    </footer>

    <!-- 页脚部分结束 -->
</body>
</body>

  </body>

</html>
```

```css
/* 自定义属性/变量  */
:root {
  --main-white: #f0f0f0;
  --main-red: #be3144;
  --main-blue: #45567d;
  --main-gray: #303841;
}

/* 基础重置 */
* {
  margin: 0;
  padding: 0;
}

/* box-sizing 和字体大小设置 */
*,
*::before,
*::after {
  box-sizing: inherit;
}

html {
  box-sizing: border-box;

  /* 设置字体大小，便于 rem 计算
   * 默认文档字体大小 = 16px, 1rem = 16px, 100% = 16px
   * (100% / 16px) * 10 = 62.5%, 1rem = 10px, 62.5% = 10px
  */
  font-size: 62.5%;
  scroll-behavior: smooth;
}

/* 不同屏幕尺寸下的字体大小媒体查询
 * 这样可以自动适配响应式
 * rem 单位会随着 html 字体大小缩放
*/

/* 断点计算方式
 * 屏幕宽度除以浏览器基础字体大小
 * 例如：断点 980px
 * 980px / 16px = 61.25em
*/

/* 1200px / 16px = 75em */
@media (max-width: 75em) {
  html {
    font-size: 60%;
  }
}

/* 980px / 16px = 61.25em */
@media (max-width: 61.25em) {
  html {
    font-size: 58%;
  }
}

/* 460px / 16px = 28.75em */
@media (max-width: 28.75em) {
  html {
    font-size: 55%;
  }
}

/* 基础样式 */

body {
  font-family: 'Poppins', sans-serif;
  font-size: 1.8rem;
  /* 18px */
  font-weight: 400;
  line-height: 1.4;
  color: var(--main-white);
}

h1,
h2 {
  font-family: 'Raleway', sans-serif;
  font-weight: 700;
  text-align: center;
}

h1 {
  font-size: 6rem;
}

h2 {
  font-size: 4.2rem;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
  color: var(--main-white);
}

img {
  display: block;
  width: 100%;
}

/* 导航栏 */

.nav {
  display: flex;
  justify-content: flex-end;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: var(--main-red);
  box-shadow: 0 2px 0 rgba(0, 0, 0, 0.4);
  z-index: 10;
}

.nav-list {
  display: flex;
  margin-right: 2rem;
}

@media (max-width: 28.75em) {
  .nav {
    justify-content: center;
  }

  .nav-list {
    margin: 0 1rem;
  }
}

.nav-list a {
  display: block;
  font-size: 2.2rem;
  padding: 2rem;
}

.nav-list a:hover {
  background: var(--main-blue);
}

/* 欢迎部分 */

.welcome-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-color: #000;
  background-image: linear-gradient(62deg, #3a3d40 0%, #181719 100%);
}

.welcome-section > p {
  font-size: 3rem;
  font-weight: 200;
  font-style: italic;
  color: var(--main-red);
}

/* 项目部分 */

.projects-section {
  text-align: center;
  padding: 10rem 2rem;
  background: var(--main-blue);
}

.projects-section-header {
  max-width: 640px;
  margin: 0 auto 6rem auto;
  border-bottom: 0.2rem solid var(--main-white);
}

@media (max-width: 28.75em) {
  .projects-section-header {
    font-size: 4rem;
  }
}

/* “自动”图片网格，无需媒体查询 */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  grid-gap: 4rem;
  width: 100%;
  max-width: 1280px;
  margin: 0 auto;
  margin-bottom: 6rem;
}

@media (max-width: 30.625em) {
  .projects-section {
    padding: 6rem 1rem;
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }
}

.project {
  background: var(--main-gray);
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
  border-radius: 2px;
}

.code {
  color: var(--main-gray);
  transition: color 0.3s ease-out;
}

.project:hover .code {
  color: #ff7f50;
}

.project-image {
  height: calc(100% - 6.8rem);
  width: 100%;
  object-fit: cover;
}

.project-title {
  font-size: 2rem;
  padding: 2rem 0.5rem;
}

.btn {
  display: inline-block;
  padding: 1rem 2rem;
  border-radius: 2px;
}

.btn-show-all {
  font-size: 2rem;
  background: var(--main-gray);
  transition: background 0.3s ease-out;
}

.btn-show-all:hover {
  background: var(--main-red);
}

.btn-show-all:hover > i {
  transform: translateX(2px);
}

.btn-show-all > i {
  margin-left: 10px;
  transform: translateX(0);
  transition: transform 0.3s ease-out;
}

/* 联系部分 */

.contact-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 100%;
  height: 80vh;
  padding: 0 2rem;
  background: var(--main-gray);
}

.contact-section-header > h2 {
  font-size: 6rem;
}

@media (max-width: 28.75em) {
  .contact-section-header > h2 {
    font-size: 4rem;
  }
}

.contact-section-header > p {
  font-style: italic;
}

.contact-links {
  display: flex;
  justify-content: center;
  width: 100%;
  max-width: 980px;
  margin-top: 4rem;
  flex-wrap: wrap;
}

.contact-details {
  font-size: 2.4rem;
  text-shadow: 2px 2px 1px #1f1f1f;
  transition: transform 0.3s ease-out;
}

.contact-details:hover {
  transform: translateY(8px);
}

/* 页脚 */

footer {
  font-weight: 300;
  display: flex;
  justify-content: space-evenly;
  padding: 2rem;
  background: var(--main-gray);
  border-top: 4px solid var(--main-red);
}

footer > p {
  margin: 2rem;
}

footer i {
  vertical-align: middle;
}

@media (max-width: 28.75em) {
  footer {
    flex-direction: column;
    text-align: center;
  }
}
```
