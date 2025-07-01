# ✅ 7. 스코프와 클로저 이해

## 📌 요약 설명
이 단원에서는 JavaScript에서 매우 중요한 개념인 **스코프(Scope)**와 **클로저(Closure)**를 학습합니다. 스코프는 변수가 어디서 유효한지를 결정하고, 클로저는 함수가 외부 변수에 접근할 수 있게 해주는 원리입니다. 코드를 이해하고 유지보수하는 데 핵심이 되는 개념이므로, 예제와 함께 꼼꼼히 이해해야 합니다.

---

## 🧭 7.1 스코프(Scope)란?

### 개념 정리
스코프는 **변수에 접근할 수 있는 범위**를 의미합니다. JavaScript에서는 크게 **전역 스코프**와 **지역 스코프**로 나눌 수 있습니다.

```js
let a = 10; // 전역 변수

function showNumber() {
  let b = 5; // 지역 변수
  console.log(a); // 가능
  console.log(b); // 가능
}

showNumber();
console.log(b); // 오류 (b는 지역 변수이기 때문에 함수 밖에서는 사용 불가)
```

- `a`는 전역 변수로 함수 안에서도 접근할 수 있습니다.
- `b`는 함수 내부에서만 사용할 수 있는 지역 변수입니다.

---

## 🧩 7.2 블록 레벨 스코프

`let`, `const`는 블록 레벨 스코프를 가지며, `var`는 함수 레벨 스코프만 가집니다.

```js
if (true) {
  let x = 10;
  var y = 20;
}
console.log(x); // 오류
console.log(y); // 20
```

- `x`는 블록 안에서만 유효합니다 (`let` 사용).
- `y`는 블록을 벗어나도 유효합니다 (`var` 사용). 이는 오류를 유발할 수 있으므로 되도록 `let`과 `const`를 사용합니다.

---

## 🔁 7.3 중첩 함수와 스코프 체인

```js
let outerVar = '밖';

function outer() {
  let innerVar = '안';

  function inner() {
    console.log(outerVar); // '밖'
    console.log(innerVar); // '안'
  }

  inner();
}

outer();
```

- 내부 함수는 자신이 선언된 위치의 외부 스코프에 접근할 수 있습니다.
- 이를 **스코프 체인(Scope Chain)**이라고 합니다.

---

## 🧠 7.4 클로저(Closure)란?

### 개념 정리
클로저는 **함수가 자신이 선언된 렉시컬 환경(Lexical Environment)을 기억하는 것**을 의미합니다. 즉, 함수가 외부 함수의 변수에 접근할 수 있는 현상을 말합니다.

```js
function outer() {
  let count = 0;

  return function inner() {
    count++;
    console.log(count);
  };
}

const counter = outer();
counter(); // 1
counter(); // 2
```

- `inner` 함수는 `outer` 함수가 종료된 후에도 `count`에 접근할 수 있습니다.
- `outer()`가 실행되면서 `inner()`가 반환되고, 내부 변수 `count`는 계속 살아 있게 됩니다.

---

## 🔒 7.5 클로저의 실용 예시

### 상태 유지 예제
```js
function createCounter() {
  let num = 0;

  return function () {
    num++;
    return num;
  };
}

const countUp = createCounter();

console.log(countUp()); // 1
console.log(countUp()); // 2
console.log(countUp()); // 3
```

- 외부에서 `num` 변수에 직접 접근할 수 없고, `countUp` 함수만을 통해 값을 증가시킬 수 있습니다.
- 이러한 구조는 상태 보호와 은닉화(캡슐화)에 매우 유용합니다.

---

## 🧠 마무리

- 스코프는 변수가 유효한 범위를 정의하며, 전역과 지역으로 구분됩니다.
- `let`과 `const`는 블록 레벨 스코프를 가지므로 안전하게 사용 가능합니다.
- 클로저는 함수가 외부 함수의 변수에 접근할 수 있도록 해 주는 개념입니다.
- 클로저는 상태 유지, 정보 은닉 등 실무에서 자주 활용되므로 반드시 이해하고 익혀야 합니다.