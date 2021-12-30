# 마크다운 Markdown

> 마크다운(markdown)은 일반 텍스트 기반의 경량 마크업 언어다. _[Wikipedia](https://google.com)_




# 1. 문법

## 1.1. 글머리 Header
글머리(Header)는 `#`을 앞에 붙여 최대 6개까지 작성할 수 있다.

```
# 1
## 2
### 3
#### 4
##### 5
###### 6
```

# 1
## 2
### 3
#### 4
##### 5
###### 6

## 1.2. 인용문 BlockQuote
인용문(BlockQuote)은 ```>```을 앞에 붙여 사용한다.

```
> Stay Hungry, Stay Foolish.  
> _Steve jobs_
```

> Stay Hungry, Stay Foolish.  
> _Steve jobs_

## 1.3. 강조 Emphasis
```
*이텔릭체1* _이텔릭체2_
**볼드체1** __볼드체12__
~~취소선~~
<u>밑줄</u>
```

*이텔릭체1* _이텔릭체2_  
**볼드체1** __볼드체12__  
~~취소선~~  
<u>밑줄</u>  

## 1.4. 코드 블럭 Code Block (Github 지원)
"\```"을 이용한다.
<pre>
<code>
```
int main() {
  printf("Hello, World!");
}
```
</code>
</pre>

```
int main() {
  printf("Hello, World!");
}
```

코드블럭("\'''") 뒤에 언어 이름을 붙이면 문법 강조(Syntax Highlighting)가 가능하다.

<pre>
<code>
```C
int main() {
  printf("Hello, World!");
}
```
</code>
</pre>

```C
int main() {
  printf("Hello, World!");
}
```

## 1.5. 목록 List
순서가 있는 목록은 숫자와 점을 이용한다.

```
1. 첫 번쨰
2. 두 번쨰
3. 세 번째
```

1. 첫 번쨰
2. 두 번쨰
3. 세 번째

순서가 없는 목록

```
- 목록 1
* 목록 2
+ 목록 3
```

- 목록 1
* 목록 2
+ 목록 3

## 1.6. 링크 Link
```
[Google](https://google.com/)

<https://google.com>

[Naver][naverLink]
<< 공백 필요 >>
[naverLink]: https://naver.com/
```

[Google](https://google.com/)

<https://google.com>

[Naver][naverLink]

[naverLink]: https://naver.com/

## 1.7. 이미지 Image
이미지(Image)는 맨 앞에 `!`가 필요하다.
```
![대체 텍스트](http://www.gstatic.com/webp/gallery/5.jpg)
```

![대체 텍스트](http://www.gstatic.com/webp/gallery/5.jpg)

## 1.8. 수평선

```
* * *

***

*****

- - -

---------------------------------------
```

* * *

***

*****

- - -

---------------------------------------

## 1.9. 줄 바꿈
```
엔터 한번으로는 
줄바꿈이 되지 않는다.

엔터 두번

또는 문장 끝에서 띄어쓰기를   
3번 이상 하면 된다.
```

엔터 한번으로는 
줄바꿈이 되지 않는다.

엔터 두번

또는 문장 끝에서 띄어쓰기를   
3번 이상 하면 된다.

# 2. 기타

## 2.1. 참고 문헌
 - [ihoneymon/how-to-write-by-markdown.md](https://gist.github.com/ihoneymon/652be052a0727ad59601#file-how-to-write-by-markdown-md)
 - [MarkDown 사용법 총정리](https://heropy.blog/2017/09/30/markdown/)
