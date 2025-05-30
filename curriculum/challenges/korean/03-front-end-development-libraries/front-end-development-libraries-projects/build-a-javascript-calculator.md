---
id: bd7158d8c442eddfaeb5bd17
title: 자바스크립트 계산기 만들기
challengeType: 3
forumTopicId: 301371
dashedName: build-a-javascript-calculator
---

# --description--
**Note:** **React 18 has known incompatibilities with the tests for this project (see [issue](https://github.com/freeCodeCamp/freeCodeCamp/issues/45922))**

**목표:** <a href="https://javascript-calculator.freecodecamp.rocks/" target="_blank" rel="noopener noreferrer nofollow">https://javascript-calculator.freecodecamp.rocks/</a>와 기능적으로 유사한 앱을 만드세요.

아래 사용자 스토리를 만족시키고 모든 테스트를 통과하시오. 필요한 라이브러리나 API를 사용하시오. 자신만의 개성을 담아 디자인을 꾸며보세요.

이 프로젝트를 완료하기 위해 HTML, JavaScript, CSS, Bootstrap, SASS, React, Redux 및 jQuery를 혼합하여 사용할 수 있습니다. 이 섹션은 프론트엔드 프레임워크를 학습하는 것이 목적이기 때문에 (React 같은) 프론트엔드 프레임워크를 사용해야 합니다. 위에 나열된 기술만 사용하여 이 프로젝트를 완료하는 것이 권장되고 이외의 기술을 사용할 경우 문제가 있을 수 있습니다. Angular 및 Vue와 같은 다른 프론트엔드 프레임워크를 지원할 예정이지만 현재는 지원되지 않습니다. 이 프로젝트에 제안된 기술 스택을 사용하는 모든 이슈 보고서를 수용하고 문제를 해결하겠습니다. 즐거운 코딩하세요!

**유저 스토리 #1:** 나의 계산기에는 `=` (등호)를 포함한 클릭 가능한 요소가 있어야 하며, 이에 해당하는 `id="equals"`가 있어야 합니다.

**유저 스토리 #2:** 나의 계산기에는 0부터 9까지 각각 하나의 숫자를 포함한 10개의 클릭 가능한 요소가 있어야 하며, 각각의 요소에는 다음과 같은 대응하는 ID가 있어야 합니다. `id="zero"`, `id="one"`, `id="two"`, `id="three"`, `id="four"`, `id="five"`, `id="six"`, `id="seven"`, `id="eight"`, 그리고 `id="nine"`.

**유저 스토리 #3:** 나의 계산기에는 4개의 클릭 가능한 요소가 있어야 하며, 각각은 4개의 주요 수학 연산자 중 하나를 포함하고 있어야 하며, 다음과 같은 대응하는 ID가 있어야 합니다. `id="add"`, `id="subtract"`, `id="multiply"`, `id="divide"`.

**유저 스토리 #4:** 나의 계산기에는 `.` (소수점) 기호를 포함한 클릭 가능한 요소가 있어야 하며, 이에 대응하는 `id="decimal"`이 있어야 합니다.

**유저 스토리 #5:** 계산기에는 `id="clear"`를 가진 클릭 가능한 요소가 있어야 합니다.

**유저 스토리 #6:** 계산기에는 값이 표시되는 요소가 있어야 하며, 이에 대응하는 `id="display"`가 있어야 합니다.

**유저 스토리 #7:** 언제든지 `clear` 버튼을 누르면 입력 및 출력 값이 지워지고 계산기가 초기화 상태로 돌아가야 하며, `display`라는 id를 가진 요소에는 0이 표시되어야 합니다.

**유저 스토리 #8:** 숫자를 입력하는 동안 입력한 내용을 `display`라는 id를 가진 요소에 볼 수 있어야 합니다.

**유저 스토리 #9:** 아무 순서로든지 어떤 길이의 숫자 체인에 대해 덧셈, 뺄셈, 곱셈 및 나눗셈을 수행할 수 있어야 하며, `=`를 누르면 올바른 결과가 `display`라는 id를 가진 요소에 표시되어야 합니다.

**유저 스토리 #10:** 숫자 입력 중에 계산기는 여러 개의 0으로 시작하는 숫자를 허용해서는 안 됩니다.

**유저 스토리 #11:** 소수점 요소를 클릭하면 현재 표시된 값에 `.`이 추가되어야 하며, 하나의 숫자에 두 개 이상의 `.`은 허용되지 않아야 합니다.

**유저 스토리 #12:** 계산기는 소수점을 포함하는 숫자에 대해 어떤 연산(`+`, `-`, `*`, `/`)이든 수행할 수 있어야 합니다.

**유저 스토리 #13:** 2개 이상의 연산자가 연속으로 입력되면 수행되는 연산은 마지막으로 입력된 연산자여야 하며(음의 부호(`-`)를 제외), 그 외의 연속된 연산자는 허용되지 않아야 합니다. 예를 들어, `5 + * 7 =`를 입력하면 결과는 `35`여야 합니다 (즉, `5 * 7`); 만약 `5 * - 5 =`를 입력하면 결과는 `-25`여야 합니다 (즉, `5 * (-5)`).

**유저 스토리 #14:** `=` 바로 뒤에 연산자를 누르면 이전 평가의 결과를 기반으로 새로운 계산을 시작해야 합니다.

**유저 스토리 #15:** 계산기는 반올림에 대해 소수 자릿수를 여러 개 가지고 있어야 합니다 (정확한 표준은 없지만, 최소 4자리까지는 합리적인 정밀도로 계산할 수 있어야 합니다. 예: `2 / 7`와 같은 계산).

**계산기 논리에 대한 참고:** 계산기 입력 논리에는 <dfn>즉시 실행 논리</dfn> 및 <dfn>수식 논리</dfn> 두 가지 주요 유형이 있습니다. 우리의 예시는 수식 논리를 사용하며 연산 순서 우선 순위를 준수합니다. 즉시 실행 논리는 이를 준수하지 않습니다. 두 가지 방식 중 어느 것이든 허용되지만, 선택한 방식에 따라 특정 방정식에 대해 결과가 다를 수 있다는 점을 주의하세요 (아래 예시 참조). 수학 계산이 다른 실제 계산기에서 검증될 수 있다면, 이를 버그로 간주하지 마십시오.

**예시:** `3 + 5 x 6 - 2 / 4 =`

-   **Immediate Execution Logic:** `11.5`
-   **수식/표현 논리:** `32.5`

You can build your project by <a href='https://codepen.io/pen?template=MJjpwO' target='_blank' rel="noopener noreferrer nofollow">using this CodePen template</a> and clicking `Save` to create your own pen. If you prefer to use another environment, then put this `<script>` tag into the body of your `index.html` file: `<script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>`

완료되면 모든 테스트가 통과되는 작동 프로젝트의 URL을 제출하십시오.

# --solutions--

```js
// solution required
```
