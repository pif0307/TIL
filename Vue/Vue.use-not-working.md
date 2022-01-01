# Vue.use()가 먹히지 않는 오류

```js
import Vue from "vue";
import App from "./App.vue";
import router from "./router";
import PortalVue from "portal-vue";

Vue.config.productionTip = false;

new Vue({
  router,
  render: (h) => h(App),
}).$mount("#app");

Vue.use(PortalVue);
```
portal vue 플러그인을 사용하려고 적용시켰을 때 발생한 문제이다.

`new Vue()`함수로 앱을 이미 실행해 버린 상태에서 라이브러리를 사용하려 해서 발생한 문제였다.

따라서 `Vue.use()`함수로 플러그인을 앱 시작 전에 호출해주면 된다.

```js
import Vue from "vue";
import App from "./App.vue";
import router from "./router";
import PortalVue from "portal-vue";

Vue.config.productionTip = false;

Vue.use(PortalVue);

new Vue({
  router,
  render: (h) => h(App),
}).$mount("#app");
```

### 실행결과
