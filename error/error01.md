# [MarkDown] VScode 에 이미지 넣기

Github에 READMe.md 파일을 작성하다보면 이미지 파일을 넣고 싶다.

---

## 1. 에러나는 이유

- 저장소에 복사한 후 링크 넣는 방법을 이용하여 사용하라는글이 많았지만
  근데 원하는 모양이 (나는 이미지가 바로 나오는 것을 원했음) 나오지 않을 뿐더러 에러가 났다. 아래 사진과 같이 말이다.

![error01-1](./image/error01-1.png)

## 2. 해결 방법

### 결론

- 결론적으로 이미지를 넣기 위해 어느 저장소에 복사한 후 링크를 넣어줘야하지만 (위에 방법) 그럴 필요 없이 github의 **프로젝트 작성 시 img라는 폴더를 만들고 거기에 이미지를 넣은 다음 그 이미지의 링크를 걸어주는 게** 속 편하다.

### 사용방법

**![이미지 이름](이미지 URL)**

"이미지 이름은 이미지의 이름이고 나는 그냥 폴더명을 넣어주었다.
그리고 이미지 URL은 이미지의 실제 링크주소를 넣어주면 된다. 위의 작성 코드는 HTML의 문법과 비슷하다.

```html
<img src="이미지 URL" />
```

### 실습

1. image폴더 만들기!

- **error**>**error01.md**와 **image** 파일을 같이 생성했다.
  ![error01-1](./image/error02-3-01.png)

2. image 파일에 넣고 싶은 파일을 넣는다.

3. 넣고싶은 Md파일에 이미지 url 주소 넣어준다.

- 나는 google/png 파일을 넣었다. <br> 그리고 error01.md 파일에 image를 넣어주려고 한다.

4. !를 넣지 않았을 때

- 맨 앞에 !가 없을 때는 아래와 같이 출력된다.
  ![error01-1](./image/error02-3-02.png)
  ![error01-1](./image/error02-3-03.png)

5. !를 넣으면
   ![error01-1](./image/error02-3-04.png)
   ![error01-1](./image/error02-3-05.png)

- 출처
  [하이! 제니스](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=chandong83&logNo=220812226888)
