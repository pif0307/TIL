# 뷰 컴포넌트의 v-model 또는 value 값을 업데이트 하지 않는 이슈

Vue는 실시간으로 값의 변화를 감지하지 못해 `v-model`, `value`에 입력된 값을 스크립트내에서 변화시키면 컴포넌트가 감지하지 못하고 업데이트하지 않는 상황이 있다.   

## 해결 방법

따라서 Vue에서는 해결책을 제시하고 있다:
```js
var vm = new Vue({
  data: {
    a: 1
  }
})
// `vm.a` is now reactive

vm.b = 2
// `vm.b` is NOT reactive
```
`vm.a`는 컴포넌트가 감지하여 값을 반영하고, `vm.b`는 컴포넌트가 감지하지 못해 값을 반영하지 못한다. 따라서

```js
Vue.set(vm.someObject, 'b', 2)
```
라는 함수를 사용하면 `vm.b`도 컴포넌트가 감지하고 값을 반영한다.

만약 methods 내에서 사용하고싶으면
```js
this.$set(this, '[data 이름]', [값])
```
같은 형식으로 사용하면 된다.

## 예시 코드
실시간으로 증가하는 `musicTime`을 컴포넌트에 실시간으로 반영하는 스크립트

```html
<template>
  <div>
    <!-- Vuetify -->
    <v-progress-linear
      :value="progressValue"
    >
    </v-progress-linear>
  </div>
</template>

<script>
export default {
  data() {
    return {
      progressValue: 0,
    };
  },

  computed: {
    ...mapState("musicPlayer", ["musicTime"]),
  },

  watch: {
    musicTime: function () {
      this.$set(this, "progressValue", musicTime);
    }
  }
};
</script>
```

## 참고 문서
- [Vue 공식 문서 - Change Detection Caveats](https://vuejs.org/v2/guide/reactivity.html#Change-Detection-Caveats)