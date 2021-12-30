# Vue Portal
> PortalVue is a set of two components that allow you to render a component's template (or a part of it) anywhere in the document - even outside the part controlled by your Vue App!

부모 컴포넌트에서 자식 컴포넌트 외부에 렌더링할 때 사용하는 라이브러리.

## 1. 설치
```
# npm
npm install --save portal-vue

# yarn
yarn add portal-vue
```

```js
// main.js
import PortalVue from "portal-vue"

Vue.use(PortalVue)
```

## 2. 사용
`portal-target`: 렌더링 될 위치

`portal`: `portal-target`에 렌더링 될 컴포넌트

`portal-target`과 `portal`은 서로 각각 `name`, `to`로 매칭한다.

```html
// App.vue
<template>
  <div>
    <ChildComponent />
    <h1> App </h1>
    <portal-target name="destination"></portal-target>
  </div>
</template>

<script>
import ChildComponent from "@/components/ChildComponent.vue";

export default {
  components: {
    ChildComponent,
  },
}
</script>
```

```html
<template>
  <div>
    <h2>Child Component</h2>
    <portal to="destination">
      <p> Render in child component </p>
    </portal>
  </div>
<template>
```
### 실행 결과
![실행결과](./assets/Vue.use-not-working-img1.png)

## 3. 참고 문헌
- [Getting Started with Portal-Vue](https://portal-vue.linusb.org/guide/getting-started.html)