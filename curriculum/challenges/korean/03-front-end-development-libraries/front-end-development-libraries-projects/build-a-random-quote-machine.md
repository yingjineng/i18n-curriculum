---
id: bd7158d8c442eddfaeb5bd13
title: 무작위 인용구 기계 만들기
challengeType: 3
forumTopicId: 301374
dashedName: build-a-random-quote-machine
---

# --description--
**Note:** **React 18 has known incompatibilities with the tests for this project (see [issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922))**

**목표:** 이와 기능적으로 유사한 앱을 만드세요: <a href="https://random-quote-machine.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://random-quote-machine.freecodecamp.rocks/</a>.

아래 사용자 스토리를 만족시키고 모든 테스트를 통과하시오. 필요한 라이브러리나 API를 사용하시오. 자신만의 개성을 담아 디자인을 꾸며보세요.

이 프로젝트를 완료하기 위해 HTML, JavaScript, CSS, Bootstrap, SASS, React, Redux 및 jQuery를 혼합하여 사용할 수 있습니다. 이 섹션은 프론트엔드 프레임워크를 학습하는 것이 목적이기 때문에 (React 같은) 프론트엔드 프레임워크를 사용해야 합니다. 위에 나열된 기술만 사용하여 이 프로젝트를 완료하는 것이 권장되고 이외의 기술을 사용할 경우 문제가 있을 수 있습니다. Angular 및 Vue와 같은 다른 프론트엔드 프레임워크를 지원할 예정이지만 현재는 지원되지 않습니다. 이 프로젝트에 제안된 기술 스택을 사용하는 모든 이슈 보고서를 수용하고 문제를 해결하겠습니다. 즐거운 코딩하세요!

**유저 스토리 #1:** 해당하는 `id="quote-box"`를 가진 래퍼(wrapper) 요소를 볼 수 있습니다.

**유저 스토리 #2:** `#quote-box` 내에서 해당하는 `id="text"`를 가진 요소를 볼 수 있습니다.

**유저 스토리 #3:** `#quote-box` 내에서 해당하는 `id="author"`를 가진 요소를 볼 수 있습니다.

**유저 스토리 #4:** `#quote-box` 내에서 해당하는 `id="new-quote"`를 가진 클릭 가능한 요소를 볼 수 있습니다.

**유저 스토리 #5:** `#quote-box` 내에서 해당하는 `id="tweet-quote"`를 가진 클릭 가능한 `a` 요소를 볼 수 있습니다.

**유저 스토리 #6:** 처음 로드될 때, 명언 생성기는 `id="text"`를 가진 요소에 무작위 명언을 표시합니다.

**유저 스토리 #7:** 처음 로드될 때, 명언 생성기는 무작위 명언의 저자를 `id="author"`를 가진 요소에 표시합니다.

**유저 스토리 #8:** `#new-quote` 버튼을 클릭하면 명언 생성기는 새로운 명언을 가져와 `#text` 요소에 표시해야 합니다.

**유저 스토리 #9:** `#new-quote` 버튼을 클릭하면 명언 생성기는 새로운 명언의 저자를 가져와 `#author` 요소에 표시해야 합니다.

**유저 스토리 #10:** 현재 명언을 `#tweet-quote` `a`클릭하여 트윗할 수 있어야 합니다. 이 `a` 요소는 현재 명언을 트윗하기 위해 `href` 속성에 `"twitter.com/intent/tweet"` 경로를 포함해야 합니다.

**유저 스토리 #11:** `#quote-box` 래퍼(wrapper) 요소는 가로 중앙에 위치해야 합니다. 브라우저 줌 레벨을 100%로 설정하고 페이지를 최대화한 상태에서 테스트를 실행하세요.

You can build your project by <a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">using this CodePen template</a> and clicking `Save` to create your own pen. If you prefer to use another environment, then put this `<script>` tag into the body of your `index.html` file: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

완료가 되면 모든 테스트를 통과한 프로젝트의 URL을 제출하시오.

**주의:** 트워터는 iframe에 링크가 로드되는 것을 허용하지 않습니다. 트윗이 로드되지 않는다면 `#tweet-quote` 요소에 `target="_blank"` 또는 `target="_top"` 속성을 사용해 보세요. `target="_top"`은 현재 탭을 대체하므로 작업이 저장되었는지 확인하세요.

# --solutions--

```js
// solution required
```
