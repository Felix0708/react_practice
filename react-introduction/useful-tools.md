### react_introduce



#### 27) 리액트 개발 할 때 사용하면 편리한 도구들

##### Prettier

[Prettier](https://prettier.io/) 는 자동으로 코드의 스타일을 관리해주는 도구입니다. 가령, 문자열을 사용 할 때 ' 를 쓸지 " 를 쓸지, 또는 세미콜론 (;) 를 코드 뒤에 붙일지 말지, 들여쓰기는 얼마나 할지, 이런 것들을 관리해줄 수 있습니다. 이 도구는 CLI 를 통해 명령어를 입력하여 사용 할 수도 있고, 다양한 에디터와 연동해서 사용 할 수도 있습니다.

루트 디렉터리 (최상위 디렉터리)에 .prettierrc 파일을 만들고 에디터에서 Prettier 익스텐션을 설치

- **trailingComma**: `"none"`, `"es5"`, `"all"` 으로 설정을 할 수 있는데, 객체 또는 배열이 여러줄로 구성되어 있으면 다음과 같이 맨 마지막 줄에 쉼표를 붙여줍니다.
- **tabWidth**: 들여쓰기의 크기를 정합니다. 저는 개인적으로 2칸을 선호합니다. 여러분이 4칸이 좋다면 4로 설정을 하셔도 됩니다.
- **semi**: 세미콜론 (;) 을 쓸지 말지 정합니다. 저는 개인적으로 사용하는것을 선호합니다. 사용하고 싶다면 `true` 로 설정하세요.
- **singleQuote**: 문자열을 입력 할 때 `"` 를 쓸지 `'` 를 쓸지 정합니다. 저는 `'` 를 사용하는것을 선호합니다. 만약에 `"` 만 쓰고 싶다면 `false` 로 설정하세요.

##### ESLint

ESLint 는 자바스크립트의 문법을 확인해주는 도구입니다. CRA 로 만든 프로젝트에는 이미 적용이 되어있어서 만약에 우리가 자바스크립트 실수를 하게 되면 터미널에 오류 또는 경고가 나타나게 되죠.

ESLint 의 VS Code 익스텐션을 설치

VS Code 와의 연동은 우리가 `useEffect` 같은 Hook 을 사용 할 때 사용하면 굉장히 유용

`useEffect` 에 등록한 함수에서 `value` 상태를 참조하는데, `deps` 배열에 이를 빠뜨리게 되면 이렇게 경고가 나타납니다. 여기서 초록색 줄에 마우스를 올리고 "빠른 수정" 을 눌러서 "Fix this ..." 메뉴를 누르게 되면 자동으로 `deps` 에 우리가 넣어야 하는 값이 포함됩니다.

이런 작업을 코드를 저장 할 때 자동으로 처리되도록 할 수 도있는데요, `⌘ + ,` (윈도우/리눅스에서는 `Ctrl + ,`) 키를 눌러서 VS Code 환경 설정을 열은 뒤, Auto Fix on Save 를 검색해서 이를 체크하세요. 그러면, 앞으로 ESLint 가 자동으로 고칠 수 있는 것들은 저장을 할 때 자동으로 고쳐줍니다.

##### Snippet

Snippet 은 도구라기보단, 에디터마다 내장되어있는 기능입니다. 한국어로는 "코드 조각" 이라고도 부르는데요, Snippet 의 용도는 자주 사용되는 코드에 대하여 단축어를 만들어서 코드를 빠르게 생성해내는 것 입니다.

우선, 여러분들이 우선적으로 해야 할 것은 VS Code 에서 .js 확장자에 대하여 언어 모드를 JavaScript React 로 설정하는 것 입니다. 기본 설정으로는 일반 JavaScript 로 되어있는데 이를 JavaScript React 로 바꿔주세요.

정말 간단한 함수형 컴포넌트이죠? 이를 스니펫으로 만들어보겠습니다. 우선, Sample 이라는 키워드가 있는 곳에 파일 이름이 들어가게 하고 싶기 때문에 Sample 을 `${TM_FILENAME_BASE}` 로 바꿔주세요. 이 값은 스니펫에서 사용 할 수 있는 변수입니다.

그 다음, Hello React 부분을 ${1} 이라고 작성해주세요. 이 부분이 나중에 스니펫을 통해 코드를 생성하게 됐을 때 텍스트 커서가 맨 처음 위치할 곳입니다.

그 다음에 이 코드를 복사해서 [Snippet Generator](https://snippet-generator.app/) 웹서비스를 열어서 좌측 코드 에디터에 붙여넣으세요.

상단에 Description 과 Tab Trigger 라는 입력창이 있는데, Description 에는 설명을, Tab Trigger 에는 단축어를 넣으시면 됩니다. 저는 **f**unctional **c**omponent 라는 의미로, fc 라고 넣었습니다. 또는, react functional component 라는 의미로 rfc 라고 입력을 해도 됩니다. 여러분의 마음대로 설정하세요.

그럼 우측에 코드 스니펫 코드가 생성되는데, 이를 복사하세요.

그 다음에는 VS Code 에서 `F1` 키 또는 `⌘ + ⇧ + P` (윈도우는 `Ctrl + Shift + P`) 를 누르고 Configure Snippet 을 검색하세요.

그리고 javascriptreact.json 을 선택하면 snippet 을 위한 json 파일이 열리는데 거기에 방금 복사한 내용을 붙여넣으면 됩니다.