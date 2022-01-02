# Object 관련 함수

## Object.assign
```js
Object.assign(target, source1, source2, ...)
```

`target` 오브젝트에 `sources`들을 병합하는 메소드

### 예시
```js
var obj1 = {a: 1, b: 2};
var obj2 = {c: 4, d: 2};
var obj3 = Object.assign(obj1, obj2);

console.log(obj3); // {a: 1, b: 2, c: 4, d: 2}
```

```js
var obj1 = {a: 1, b: 2};
var obj2 = {a: 4, c: 2};
var obj3 = Object.assign(obj1, obj2);

console.log(obj3); // {a: 4, b: 2, c: 2}
```
공통 값이 있을때는 `target`에 `source`들이 덮어지는 식이다.