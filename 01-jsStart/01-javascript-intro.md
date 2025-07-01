
# ✅ 1. JavaScript 소개 및 개발 환경 설정

## 📌 요약 설명
이 단원에서는 JavaScript가 웹에서 어떤 역할을 수행하는지, 그리고 퍼블리셔가 왜 JavaScript를 익혀야 하는지를 이해하고, 본격적인 학습을 위한 개발 환경을 구축합니다. 브라우저 내 JavaScript의 실행 흐름, 코드 삽입 위치, 그리고 개발 툴의 활용법까지 함께 배웁니다.

---

## 🧭 1.1 JavaScript란 무엇인가?

### 🔍 개념 정리
- **JavaScript (JS)**는 웹 페이지에 **동적인 동작을 추가하는 프로그래밍 언어**입니다.
- HTML은 콘텐츠 구조, CSS는 스타일, JS는 **동작과 로직을 제어**합니다.
- JavaScript는 **브라우저 내에서 실행되는 클라이언트 사이드 언어**로 시작했지만, 현재는 Node.js를 통해 서버에서도 사용됩니다.

### 🎯 퍼블리셔가 JavaScript를 배워야 하는 이유
- HTML/CSS만으로는 **정적인 콘텐츠 구현에 한계**가 있습니다.
- **UI 인터랙션**(탭, 아코디언, 모달, 슬라이더 등)을 직접 구현할 수 있어야 실무 대응이 가능합니다.
- 디자이너-개발자-퍼블리셔 협업 환경에서 **JavaScript 이해가 협업 효율성에 핵심**입니다.

### ✅ 실무 활용 예시

| 기능 | HTML/CSS만으로 구현 가능? | JavaScript 필요 여부 |
|------|--------------------------|----------------------|
| 탭 메뉴 전환 | ❌ | ✅ 클릭 이벤트 필요 |
| 모달 팝업 열기/닫기 | ❌ | ✅ DOM 제어 필요 |
| 입력 실시간 검사 | ❌ | ✅ 이벤트 처리 필요 |
| 이미지 슬라이더 | ❌ | ✅ 타이머, 애니메이션 필요 |

---

## 🖥 1.2 JavaScript 동작 방식 이해

### 🧬 DOM과 JS의 관계
HTML 로딩 후 **DOM(Document Object Model)**이 생성됩니다.

JS는 이 DOM을 조작하여 동적인 변경을 일으킵니다 (텍스트 변경, 클래스 추가 등).

### 🔁 실행 흐름
1. HTML 해석
2. `<script>` 태그 실행
3. JS가 DOM을 제어  
   ※ 단, DOM 생성 전 실행되면 오류 발생 가능

### 💡 예시 코드
```html
<!-- 올바른 위치 -->
<body>
  <h1 id="title">안녕하세요</h1>
  <script>
    document.getElementById('title').textContent = 'Hello, JavaScript!';
  </script>
</body>
```

---

## 🧰 1.3 JavaScript 개발 환경 구성

### 🛠 선택 가능한 코드 에디터

#### ✅ VS Code (Visual Studio Code)
- Microsoft에서 개발한 **가볍고 확장성 높은 에디터**입니다.
- **무료**, 빠른 실행, 다양한 플러그인 제공합니다.
- 추천 확장: Prettier, ESLint, Live Server, JavaScript Snippets

#### ✅ WebStorm
- JetBrains에서 만든 **전문 JavaScript IDE**
- **유료(학생용 무료)**, 코드 자동완성, 리팩토링, 디버깅에 강합니다.
- HTML/CSS/JS 협업 편집과 TypeScript 연동에 강점입니다.

| 비교 항목 | VS Code | WebStorm |
|-----------|---------|----------|
| 가격 | 무료 | 유료 |
| 확장성 | 매우 뛰어남 | 기본 기능 강력 |
| 성능 | 가볍고 빠름 | 무겁지만 안정적 |
| 추천 대상 | 초·중급 개발자 | 중급 이상 or 팀 협업 환경 |

---

### 🗂 프로젝트 폴더 구조 예시
```
my-js-project/
├── index.html
├── js/
│   └── main.js
└── css/
    └── style.css
```

### 🔌 HTML에서 JS 연결하기
```html
<!-- HTML 내 인라인 스크립트 -->
<script>
  alert('JS 시작!');
</script>

<!-- 외부 파일로 분리 -->
<script src="./js/main.js"></script>
```

---

## 🧪 1.4 브라우저 콘솔로 JS 테스트하기

### 🔍 개발자 도구 (DevTools) 콘솔 활용
- Chrome 기준: **F12 → Console 탭**
- 간단한 변수 테스트, 오류 확인, DOM 확인 가능

```js
console.log('콘솔에서 출력');
let name = '퍼블리셔';
console.log('안녕하세요, ' + name + '님');
```

---

## ✅ 마무리
- JavaScript는 퍼블리셔에게 **UI 제어, 이벤트 처리, 동적 콘텐츠 조작**을 가능하게 해주는 필수 도구입니다.
- VS Code와 WebStorm 중 자신에게 맞는 에디터를 선택하고, HTML 문서에 JS를 삽입하는 방법을 익혀야 합니다.
- 브라우저 콘솔과 폴더 구조를 활용한 **기본적인 개발 환경**을 먼저 설정해야 학습 효율이 높아집니다.
