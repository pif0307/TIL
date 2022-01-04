# 화면 아무곳이나 클릭해도 v-bottom-sheet내의 컴포넌트가 반응하는 이슈

`v-bottom-sheet`에는 `retain-focus`라는 속성이 있다.

```
Tab focus will return to the first child of the dialog by default. Disable this when using external tools that require focus such as TinyMCE or vue-clipboard.
```
[Vuetify 공식 문서](https://vuetifyjs.com/en/api/v-bottom-sheet/)

우리가 웹에서 Tab을 누르면 다른 버튼/Input등으로 이동할 때 그 Tab의 시작점을 Tab focus라고 하고 `retain-focus`가 Tab focus를 `v-bottom-sheet`의 첫번쨰 자식 구성요소로 맞춰준다.

이 속성은 기본으로 켜져있어서 직접 꺼줘야한다.

```html
<v-bottom-sheet :retain-focus =false>
  <!-- -->
</v-bottom-sheet>