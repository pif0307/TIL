# HTML 링크(파일) 경로 정리

## 절대경로
```html
<img src="https://github.com/pif0307/images/image.png" alt="image" />
```

## 상대경로
```html
<img src="image/image.png" alt="image" />
```
앞에 `/`가 붙지 않으면 현재 경로에서부터 시작

```html
<img src="pif0307/images/image.png" alt="image" />
```
앞에 `/`가 붙으면 사이트 루트`*`에서 부터 시작
> `*`사이트 루트: `https://github.com/`같은 큰 주소