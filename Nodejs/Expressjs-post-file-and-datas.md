# Expressjs에서 파일과 데이터를 동시에 불러오는 방법

## 1. 개요
음악을 업로드하는 사이트를 개발중에 음악의 이름, 설명등을 음악파일과 함께 업로드하고 싶었는데 방법을 몰라 구글링을 해봤다.

## 2. 프론트

우선 프론트엔드에서 백엔드로 파일을 전송할 때 `FormData`라는 형식으로 전송한다. 우선 파일과 함께 업로드하고싶은 데이터를 FormData안에 함께 `append()`함수를 이용해서 넣으면된다.

```js
var musicData = { title: "titleStr", "artist": "artistStr" };
var musicFile = getMusicData(); // 음악 파일을 불러오는 메소드

var formData = new FormData();
formData.append("title", musicData.title);
formData.append("artist", musicData.artist);
formData.append("musicFile", musicFile);


post(`/upload`, formData); // 사용하는 POST 함수
```

여기서 주의할 점은, `FormData`에 `Object` 형식 그대로 `append`하면 안된다!

[FormData.Append() 문서](https://developer.mozilla.org/ko/docs/Web/API/FormData/append)에 따르면 

```js
formData.append(name, value);
formData.append(name, value, filename);

// value: 필드의 값입니다. USVString 또는 Blob (File과 같은 sublcass를 포함하여) 일 수 있습니다.
```

`USVString` 또는 `Blob`만 입력이 가능해 `object`형식은 들어갈 수 없다.

만약 `object`그대로 `append`하고싶다면 `JSON`으로 바꾸고 넣으면 된다.

```js
formData.append("musicData", JSON.stringify(musicData));
```

이 방법은 [김재훈님 블로그](https://medium.com/jaehoon-techblog/simpleblog-%EA%B0%9C%EB%B0%9C-%EC%9D%BC%EC%A7%80-4-55a8d2a8604)를 참고하였다.

## 3. 백엔드(Expressjs)

프론트에서 전송한 `FormData`형식을 `req.body`에서 바로 쓰면 좋겠지만.. `expressjs`에서는 프론트에서 받은 `FormData`형식을 자동으로 값을 변환해주지 않는다.

`expressjs` 프로젝트를 최근에 만들었다면, 메인 서버js(app.js)에 이러한 내용이 적혀있을 것이다.

```js
app.use(express.json());
app.use(express.urlencoded({ extended: false }));
```

프론트에서 받아온 값을 `req.body`에서 데이터를 사용하게 끔 만드는 모듈인 `body-parser`이라는 라이브러리를 세팅하는 메소드인데, [body-parser 공식문서](https://www.npmjs.com/package/body-parser#readme)에는 이런 내용이 적혀있다.

```
This does not handle multipart bodies, due to their complex and typically large nature. For multipart bodies, you may be interested in the following modules:

- busboy and connect-busboy
- multiparty and connect-multiparty
- formidable
- multer
```

간단하게 해석하면, `body-parser`은 `multipart bodies`를 지원하지 않아 상기된 라이브러리를 사용하라는 내용이다.

그리고 중요한 것은, `FormData`는 `multipart bodies`이다. 

따라서 이 문제를 해결하기 위해서 밑의 라이브러리를 사용하면 되는데, `formidable`에는 `FormData`를 parse해주는 메소드를 가지고있다. 따라서 이것을 사용하면 해결할 수 있다.

설치
```
npm install formidable
```

공식문서에서 제공하는 기본 `expressjs` 예제는 다음과 같다:
```js
const express = require('express');
const formidable = require('formidable');

const app = express();

app.post('/api/upload', (req, res, next) => {
  const form = formidable({ multiples: true });

  form.parse(req, (err, fields, files) => {
    if (err) {
      next(err);
      return;
    }
    res.json({ fields, files });
  });
});

app.listen(3000, () => {
  console.log('Server listening on http://localhost:3000 ...');
});
```

`form.parse()`라는 함수 안에서 콜백 함수로 `fields`와 `files`라는 값을 불러오는데, `fields`가 프론트에서 불러온 값 `FormData`에 append한 파일을 제외한 값들(title, artist, musicData)이고, `files`가 append한 파일들(musicFile)이다.

아래는 필자가 작성한 코드이다:
```js
const formdiable = require("formidable");
const form = formdiable({ multiples: false });

router.post("/uploadMusic", function (req, res) {
  form.parse(req, (err, fields, file) => {
    if (err) {
      res.send(err);
    }

    console.log(fields.title + ", " + fields.artist); // titleStr, artistStr
  });
});
```