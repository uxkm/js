
# ✅ 4. 조건문 (if, switch)

## 📌 요약 설명
이 단원에서는 JavaScript에서 조건에 따라 코드의 흐름을 분기하는 조건문에 대해 학습합니다. `if`, `else`, `else if`, `switch` 문을 활용하여 특정 조건을 만족할 때만 동작하는 UI 로직을 구현할 수 있습니다. 퍼블리셔가 자주 접하는 유효성 검사, 인터랙션 조건 처리 등에 반드시 필요한 내용입니다.

---

## 🔍 4.1 조건문이란?

### 개념 정리
- 조건문은 주어진 **조건의 참/거짓 여부**에 따라 실행할 코드를 선택하는 문장입니다.
- 프로그램의 흐름을 제어하고 다양한 분기 처리를 할 수 있습니다.

---

## 🔎 4.2 if 문

### 기본 구조
```js
if (조건) {
  // 조건이 참일 때 실행되는 코드
}
```

### else 문과 else if 문
```js
if (조건1) {
  // 조건1이 참일 때 실행
} else if (조건2) {
  // 조건2가 참일 때 실행
} else {
  // 위 조건 모두 거짓일 때 실행
}
```

### 예제
```js
let score = 85;

if (score >= 90) {
  console.log('A등급입니다.');
} else if (score >= 80) {
  console.log('B등급입니다.');
} else {
  console.log('C등급입니다.');
}
```

---

## 🔄 4.3 switch 문

### 기본 구조
```js
switch (값) {
  case 조건값1:
    실행문;
    break;
  case 조건값2:
    실행문;
    break;
  default:
    기본 실행문;
}
```

### 예제
```js
let browser = 'Chrome';

switch (browser) {
  case 'Edge':
    console.log('Edge 브라우저입니다.');
    break;
  case 'Chrome':
  case 'Firefox':
    console.log('지원되는 브라우저입니다.');
    break;
  default:
    console.log('지원되지 않는 브라우저입니다.');
}
```

### 유의사항
- `break` 문을 생략하면 다음 case로 넘어가며 실행됩니다.
- `default`는 선택사항이지만 보통 모든 case에 해당하지 않을 경우를 대비해 사용합니다.

---

## 🧠 마무리

- 조건문은 UI 상태 분기, 유효성 검사, 접근성 처리 등에 광범위하게 사용됩니다.
- `if`문은 유연하고 직관적이며, `switch`문은 고정된 값 비교에 효과적입니다.
- 상황에 맞는 조건문을 선택하여 사용자 경험을 제어할 수 있습니다.
