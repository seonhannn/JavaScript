# JavaScript Basic

> 유튜브 '코딩앙마'님의 강의를 듣고 기록한 내용입니다.

let은 한 번 선언 후 데이터를 바꿀 수 있다.

```
let name = "Jiseon"; 
name = "google";
```

const는 한 번 선언 후 데이터를 바꿀 수 없다.

```
const age = 21;
age = 20; // error!
```

변수명은 문자, 숫자, $, _ 만 사용하여 이해하기 쉽게 선언해야 한다.

첫 글자는 숫자가 될 수 없으며 예약어를 사용할 수 없다.

보통 상수는 대문자로 선언한다.

문자형의 데이터는 ", ', `를 사용하여 정의할 수 있다. 문자로 사용하고자 할 때는 \를 앞에 붙여주면 된다.

`와 ${}로 변수를 사용할 수 있다. 

```
const name = 'seonhannn';
const message = `My name is ${name}`;
console.log(message); // console.log는 화면에 표시해주며, 사칙연산이 가능하다.
console.log(`${age+1}`);
```

숫자를 0으로 나누면 무한대가 나오며, 문자열을 숫자로 나누면 'NaN'이 뜬다. 이는 숫자가 아니라는 의미이다.

Boolean은 true 또는 false 두 가지의 값을 갖는다.

null은 값이 존재하지 않음을, undefined는 값이 할당되지 않았음을 뜻한다.

typeof 연산자로 변수의 자료형을 알아낼 수 있다.

```
console.log(typeof 3);
console.log(typeof name);
console.log(typeof true);
console.log(typeof "hello");
console.log(typeof null);
console.log(typeof undefined);
```

문자와 숫자를 다음과 같이 연결할 수도 있다.

```
const a = "나는 ";
const b = 21;
console.log(a + b + "세 입니다.";
```

alert는 메시지를 띄우지만 사용자와 상호작용하지는 않는다. 단지 정보 전달용이다.

prompt는 메시지를 띄우고 사용자에게 값을 입력받는다. 인수는 두 개를 입력할 수도 있으며 두번째 인수가 default 값이다.

confirm은 확인을 받으며 true 또는 false 두 가지의 값을 갖는다.

```
const id = prompt("아이디를 입력하세요.");
alert("환영합니다. " + id + "님");
alert(`환영합니다. ${id}님.`); // 위의 코드와 결과가 같다.
```

만약 alert 창을 취소 클릭하면 null 값이 들어가게 된다.

```
const mathScore = prompt("수학 몇 점?");
const engScore = prompt("영어 몇 점?");
const result = (mathScore + engScore) / 2;
console.log(result);
```

prompt는 입력받은 숫자를 문자로 인식한다. 자동 형변환은 원하지 않는 결과가 나오게 할 수 있으므로 명시적 형변환을 하도록 해야 한다.

```
Number(null); // 0
Number(undefined); // NaN

Number(0) // false
Number("0") // true

Number('') // false
Number(' ') // true
```

거듭제곱은 ** 을 사용해 구할 수 있다.

연산자를 줄여서 쓸 수 있다. 

```
let num = 10;
num = num + 10;
num += 10; // 위 코드와 결과가 같다.
```

증가 연산자, 감소 연산자

```
num++;
num--;
// 그 줄의 코드가 끝난 후 연산된다.
```

```
++num++;
--num;
// 그 줄의 코드가 실행되기 전에 먼저 연산된다.
```

비교 연산자

===은 타입까지 확인해준다. 

```
1 == "1" // true
1 === "1" // false
```

if문은 조건을 확인 후 참이면 코드를 실행한다.

```
if (age > 19) {
  console.log("성인입니다.");
  } else if (age < 19) {
  console.log("미성년자입니다.");
  } else {
  console.log("19세입니다.");
  }
```

명확한 횟수가 정해져 있으면 for문을, 정해져 있지 않다면 while문을 사용한다.

switch는 case가 많을 경우 else if문 보다 간겨랗게 하기 위해 사용한다.

&&가 ||보다 우선순위가 높다. 

함수

```
function sayHello(name) { // 함수, 함수명, 매개변수
  console.log(`Hello, ${name}`);
}

sayHello('seonhannn');
```

매개변수를 없애려면 작성하지 않으면 된다.

```
function sayHello(name) {
  let msg = 'Hello';
  if(name) {
    msg += `, ${name}`;
  }
  console.log(msg);
}

sayHello('seonhannn');
```

지역 변수를 전역 변수와 같은 이름으로 선언할 수 있다. 

함수는 return 으로 값을 반환할 수 있다. 함수를 종료하는 목적으로 사용하기도 한다.

함수 선언문은 어디서든 호출 가능하나, 함수 표현식은 함수에 도달해야 사용할 수 있다.

화살표 함수는 다음과 같다.

```
function showError() {
  console.log('error');
}

let showError = () => {
  console.log('error');
}
```

객체는 다음과 같이 생성할 수 있다.

```
const user = {
  name : 'seonhannn',
  age : 21,
}
```
프로퍼티의 구분은 쉼표로 하며, 코드를 관리하기 쉽도록 마지막 프로퍼티에도 쉼표를 추가해주는 것이 좋다.

객체에 접근할 때는 점 또는 대괄호를 사용한다.

```
const user = {
  name : 'seonhannn',
  age : 21,
}

console.log(user.name);
user[name] = 'jiseon';
console.log(user.name);
```

객체를 삭제할 때는 delete 키워드를 사용한다.

```
const user = {
  name : 'seonhannn',
  age : 21,
}

delete.user.age;
console.log(user.age);
```

단축 프로퍼티는 다음과 같다.

```
const name = 'seonhannn';
const age = 21;

const user = {
  name,
  age,
  gender : 'female',
}
```

프로퍼티 존재 여부를 확인할 때는 in을 사용한다.

```
const user = {
  name : 'seonhannn',
  age : 21,
}

console.log('age' in user);
```

```
function makeObject(name, age) {
  return {
    name,
    age,
    hobby : 'read a book',
  }
}

const Jiseon = makeObject('seonhannn', 21);
console.log(Jiseon);
console.log('age' in Jiseon);
console.log('birthday' in Jiseon);
```

```
function isAdult(user) {
  if(!('age' in user) || user.age < 20) {
    return false;
  } else {
    return true;
  }
}

const Jiseon = {
  name : 'Jiseon',
  age : 21,
}

isAdult(Jiseon);
```

객체의 프로퍼티를 추출할 때 for in을 사용한다.

```
const seonhannn = {
  name : 'seonhannn',
  age : 21,
}

for(key in seonhannn) {
  console.log(seonhannn.key);
}
```

객체 프로퍼티로 할당된 함수를 메서드라고 한다.

배열은 순서가 있는 리스트이다. 숫자, 객체, 문자, 함수 등을 포함할 수 있다.

push - 배열 끝에 요소를 추가

pop - 배열 끝 요소를 제거

shift, unshift는 배열 앞의 요소를 추가하고 제거한다. 여러 개의 요소를 제어할 수도 있다.

```
let days = ['mon', 'tue', 'wed'];
days[0] = 'sun';
console.log(days.length); // 배열 길이 확인
days.push('thu');
days.shift('sat');

for(let index = 0; index < days.length; index++) {
  console.log(days[index];
}

for(let day of days) {
  console.log(day)
}
```
