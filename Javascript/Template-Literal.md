# Template Literal

문자열 사이에 변수 등을 넣고 싶을 떄 사용하는 문자열 표기법

만약 기존의 방법으로 문자열 안에 변수를 넣는다면
```js
var name = "Bob";
var str = "Hi, I'm " + name + ". Nice to meet you.";

console.log(str); // Hi, I'm Anna. Nice to mmet you.
```
처럼 일일히 +로 처리해줘야함.

만약 Template literal 방법으로 처리한다면
```js
var name = "Bob";
var str = `Hi, I'm ${name}. Nice to meet you."`;

console.log(str); // Hi, I'm Anna. Nice to mmet you.
```
처럼 문자열 안에 넣어서 사용이 가능함.

## 사용법
벡틱( &#96; )을 사용하여 문자열을 만들고 `${변수 이름}` 형식으로 변수를 삽입한다.
> 주의) 쌍따옴표( ' )가 아니라 키보드 숫자 1 옆에 있는 벡틱( &#96; )이다!

```js
var a = 10;
console.log(`a: ${a}`); // a: 10
```
