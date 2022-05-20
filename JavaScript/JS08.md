# React 입문주차 S.A (220520)

## JavaScript의 자료형과 JavaScript만의 특성은 무엇일까?

### 느슨한 타입(loosely typed)의 동적(dynamic) 언어

1. 결론은 JavaScript 언어를 이렇게 부른다.
2. JavaScript의 역할
   1. 사용자와 웹사이트가 서로 상요작용하는 데 도움을 주는 기능을 제공한다.
   2. 사용자가 어떤 액션을 취했을 때 다른페이지를 열지 않아도 바로 결과를 보여준다.
3. JavaScript의 특징
   1. HTML 페이지 변경 및 HTML 엘리먼트와 콘텐츠의 추가나 제거
   2. css와 html 엘리먼트의 스타일 변경
   3. 사용자와의 상호작용, 폼의 유효성 검증
   4. 마우스와 키보드 이벤트에 대한 스크립트 실행
   5. 웹 브라우저 제어, 쿠키 등의 설정과 조회
   6. AJAX기술을 이용한 웹 서버와의 통신
4. JavaScript의 특징
   1. 객체지향언어이다. 하지만 상속과 클래스라는 개념이 없다.
   2. 인터프리터 언어이다. 클라이언트의 웹 브라우저에 의해 해석되고 실행된다.
   3. html문서 내애 기술되고 html 문서와 함께 수행된다.
   4. html연산제어 등 프로그래밍적인 요소를 추가하고 클라이언트의 자원을 활용할 수 있게 한다.
   5. 실행 컨텍스트와 클로저 ( 자신만의 독특한 과정을 통해 실행 컨덱스트를 만들고 그 안에서 실행이 진행된다.)
   6. ProtoType-based Object (즉 , 프로토타입 기반의 객체지향 언어)
   7. 동적타입의 느슨한 타입의 언어이다.
5. 느슨한 타입(loosely typed)의 동적(dynamic) 언어의 문제점
   1. 내부에서 제공되는 기능이 제한적이고 , 관련된 개발도구도 적은 편이다.
   2. 자바스크립트는 html 소스코드에 함께 작성되면서 소스코드가 외부로 공개되는데 이 과정에서 보안 취약점이 발생한다.
   3. b번 같은 경우는 다른 홈페이지가서 개발자 도구로 바로 들어가면 무슨 소스 썼는지 볼 수 있는? 이런걸 말하는 것 같다.
6. JavaScript 형변환
   1. 이 부분은 진짜 너무나 정보가 많은 아니라 주말에 따로 정리하겠다.
   2. 그래도 혹시 모르니까 공부한 [링크](https://velog.io/@yejinh/Javascript-%ED%98%95%EB%B3%80%ED%99%98) 첨부한다.
   3. js는 쓸데없이 gentle해서 지맘대로 배려한답시고 형을 변환한다.
   4. 예를 들면 1**+’1’로 적으면 숫자+문자니까 오류로 만들 법**한데 **gentle하게 ‘11’**로 만들어준다. → 알고리즘풀 때 너무 헷갈린다. 근데 나머지 연산자들에서는 그러지 않는다 그냥 정신나간 놈인듯
7. ==, ===
   1. 생긴 거랑 같이 같은게 느슨한게 == 이다 . type까지 알고 싶으면 ===을 사용하면 된다.
8. undefined와 null, Nan

   1. **undefined (자료형)**: 선언은 되었으나 값이 할당 되지 않은 상태

      1. 우리가 처음 개발자 도구에서 치는단어는

         ```jsx
         console.log("Hello world");
         ```

         - 결과를 돌려줄 게 없다! 라는 말이다. (undefined를 돌려준다고 생각해도 좋다)
         - 그럼 반환창에는 ‘Hello world’ 와 undefined가 찍혀있는 것을 볼 수 있다.

      2. 아래와 같이 Bool값에는 False값이 찍힌다.

         ```jsx
         var temp;
         Boolean(undefined) 에서는 false
         Number(undefined) 에서는 NaN
         String(undefined) 에서는 "undefined"
         ```

   2. **null(자료형)** : 아무 값도 나타내지 않는 특수한 값

      1. 의도적으로 빈값을 넣을때 사용한다.
      2. 초기화 해주어야 null 상태가 존재할 수 있다.
      3. 우리가 null 을 typeOf에 찍어보면 Object가 나온다. 만드는 초창기에 실수했다고 한다. 실수했는데 수정을 안해서 지금까지 썼다고 한다.
      4. 아래와 같이 Number에서는 NaN이 아니라 0이 찍힌다 .. 신기

         ```jsx
         Boolean(null) 에서는 false
         Number(null) 에서는 0
         String(null) 에서는 "null"
         ```

   3. NaN : Not a Number ! 숫자가 아니다 !
      1. NaN === NaN 은 false다. (왜..?) NaN을 검사하기 위해서는 IsNaN을 사용해야 한다.
      2. 왜? 냐는 물음에 생각해보면 0/0은 NaN이다(수학적으로) 저번에 이 물음에 대해 토론했었는데 이런 수학적인 이유때문에 false가 되는 게 아닐까 ? 추측해본다 .

## JavaScript 객체와 불변성이란?

- 먼저 자바스크립트는 데이터타입은 크게 2가지로 구분된다.

### 기본형데이터와 참조형 데이터

1. 기본형(Primitive type) : 값을 그대로 할당한다.
   1. 메모리 내에 고정된 크기로 저장되면서 원시 데이터 값 자체를 보관하고 불변적 기본적으로 데이터는 하나의 메모리를 사용한다. (재사용)
   2. **Number- String(문자열)- Boolean- null- undefinded- Symbol(ES6 부터 추가 됨, 객체 속성을 만드는 데이터 타입)**
2. 참조형(Reference Type) : 값이 저장된 주소 값을 할당(참조)
   1. Object
   2. Array(배열) : const 로 선언된 변수 배열에 Array.push를 적용할 수 있는 이유는배열은 참조 타입이기 때문에 데이터의 주소를 대입할 수 있기 때문이다.
   3. function(함수) / RegExp(정규표현식) : 문자열에 나타나는 특정 문자조합과 대응시키기 위해 사용되는 패턴이다.
   - Map
   - Et.

### JavaScript 형변환

- 형 변환에 대한것은 [블로그](https://curryyou.tistory.com/186?category=898979)를 참조한다.

### 불변 객체를 만드는 방법

- 어떤 블로거가 코딩시험을 보다가 객체 A를 배열 B에 Push한 후 객체 A의 내용을 바꿨는데 배열 B에 Push되어 있던 객체 값이 바뀐 결과가 발생했다고 한다. 이때 배열에 push한 값은 value로 들어간다고 착각했고, 설마 주소값까지 들어가나? 라는 생각은 정확히 맞았다고 한다.
- [불편객체](https://spiderwebcoding.tistory.com/8)란 변하지 않는것이라고 생각하면 된다. js는 2가지인데 **const와 Object.freeze()**를 사용하는 것이다.

1. const
   1. Js의 let과 함께 나온 아이이다 .Es6부터 지원한다. (let 과 var는 아래서 다루겠다)
   2. const는 변수가 아니다 . 상수다. → 상수는 절대 변하지 않는 값이다
   3. const는 할당된 값이 상수가 되는 것이 아닌 [바인딩](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=okkam76&logNo=221347019465)된 값이 상수가 되는 , 즉 `const text = {}` 에 text의 변수는 상수가 되니까 const 키워드로 선언된 **test변수에는 객체 재할당은 불가능하지만 객체의 속성은 변경이 가능하다.**
2. Objext.freeze()

   1. 자바스크립트에서 기본적으로 제공하는 메소드인 Object.freeze() 메소드이다. 공식 문서에서는 “객체를 동결하기 위한 메소드”라고 적혀있다.
   2. 이 메소드는 아래와 같이 사용된다.

   ```jsx
   let himdel = {
     //1. himdel값에 key : value 가진 객체를 바인딩 후
     name: "kim",
   };

   Object.freeze(himdel);
   ```

   c. Object.freeze(test)를 사용해 바인딩된 변수를 동결 객체로 만들었다. 때문에 **test 객체는 객체의 속성을 변경하는 시도는 불가능**하다.

### 얕은 복사와 깊은 복사

1. [얕은 복사](https://velog.io/@th0566/Javascript-%EC%96%95%EC%9D%80-%EB%B3%B5%EC%82%AC-%EA%B9%8A%EC%9D%80-%EB%B3%B5%EC%82%AC) :얕은 복사란 객체를 복사할 때 위의 예제처럼 원래값과 복사된 값이 같은 참조를 가리키고있는 것을 말한다. 객체안에 객체가 있을 경우 한개의 객체라도 원본 객체를 참조하고 있다면 이를 `얕은 복사`
   라고 한다.
2. 깊은 복사 : 깊은 복사된 객체는 객체안에 객체가 있을 경우에도 원본과의 참조가 완전히 끊어진 객체를 말한다.

## 스코프 sope

- 스코프는 즉 영역을 말하는데 js에는 전역과 지역 두가지가 존재한다.

1. 지역변수 : 함수안에서만(block안에서만) 돌아다닐 수 있는 함수이다.

   ```jsx

   function sayHello(name){

   **let msg = 'Hello'; // function 안에 선언**
       if(name){
           msg += name;
       }
       **console.log(msg)**// 출력 : Hello위
   }

   sayHello('위')
   ```

2. 전역변수 : 어디든 싸돌아다니는 함수이다.

   ```jsx
   **let msg = 'Hello'; // function밖으로 빼준다.**
   function sayHello(name){


       if(name){ .
           msg += name;
       }
       **console.log(msg)**// 출력 : Hello위
   }

   sayHello('위')

   ```

3. 지역변수와 전역변수가 나눠지는 이유는 뭘까.
   1. 프로그램 코드가 저장되는 영역이 있고 전역변수도 이에 속한다. 이게 **메모리에 저장되는데 지역변수까지 저장되면 너무 많은 메모리를 차지**하게 된다. 집으로 치자면 전역변수는 집을 산 건물주고 지역변수는 전세로 들어온 입주자로 생각하면 이해가 빠르다.

## 호이스팅과 TDZ는 무엇일까?

### 들어가기 전에...

- let보다는 var가 먼저 나왔다. js 만든 사람이 신이 아니기때문에 뭔가 더 업그레이드된 기능을 es6버전에 담아 출시했다. 여기서 **let이 나왔다**. let을 만들었다는 이유는 var에 문제가 있으니까 let을 만들었을거다 . 그럼 var의 문제점을 보자.! (이어지는 글이니 혼동금지)
- 여기서 자바스크립트는 특이한 특징이 있는데 (다른 언어는 안 그런다.) 처음부터 끝까지 실행되기 전에 js가 나와서 “너네 선언한 애 누구있냐 ?” 이럼서 메모리에 먼저 저장한다. 그러고 var a를 부르면 주섬주섬 꺼낸다 . 이러한 개념이 아래에 호이스팅이다.

1. 호이스팅

   1. **함수 안에 있는 선언들을 ‘모두’ 끌어올려서 해당 ‘함수 범위의 최상단에 선언’하는 것**
   2. 아래의 코드를 보자

      1. 할당된 것도 없는데 냅다 console.log를 찍어도 값이 나온다.
      2. 이게 가능한가 ? a에 할당된 것도 없는데 불러오면 무조건 오류 아닌가 ?
      3. 근데 이걸 가능케 한다 . 할당된 것이 없어도 값이 나온다. 이게 호이스팅이다. (console.log(a)를 찍으면 a를 찾을 수 없다고 에러가 바로 나온다 .)
      4. **호이스팅 시 변수의 선언과 초기화(undefined)를 같이 시켜버린다.**

         ```jsx
         **console.log(a)** //undefined
         **var** a = 1;
         console.log(a)  // 1
         ```

         ```jsx
         a = 1; // 뭔가 이상하지 않나 ? 이것도 실행이 된다.
         ```

      5. var 는 **함수만 지역변수로 호이스팅**되고 **나머지는 모두~ 전역변수**로 올린다.

         ```jsx
         var i = 1;
         console.log(i);
         var i = 2;
         console.log(i); // 중복의 i , 이거도 가능하다
         // 출력값 1,2
         ```

         ```jsx
         for (var i = 0; i < 5; i++) {
           console.log(i);
         }
         console.log(i); // 지역변수 i의 값, 이것도 값이 나온다.
         ```

   ### 이게 말이돼 ? let 출시해..

   - 위와 같은 이유로 let이 출시된다. let도 호이스팅이 된다. 대신 아래의 개념을 만들었다.
     ```jsx
     let i = 1;
     console.log(i);
     let i = 2;
     console.log(i); // Iendtifier 'a ' has already declared.. 오류가 나온다.
     ```
     ```jsx
     for (let i = 0; i < 5; i++) {
       console.log(i);
     }
     console.log(i); // i is not defined error가 나온다.
     // i는 지역변수가 되므로 밖에서 찾을 수 없다.
     ```

   1. TDZ(Temporal Death Zone)

      1. a가 호이스팅으로 ‘기억'이 된건 알겠어 , 근데 a선언문이 나오기 전까진 너는 a에 접근할 수 없어 ! 일시적으로 넌 죽은 zone이야

      ```jsx
      **console.log(a)** // Death zone
      let a = 1;
      console.log(a)
      ```

### 함수 선언문과 함수 표현식에서 호이스팅 방식의 차이

- 위에 내용을 이어서 이해해 보면서 함수 선언ans(`fuction(매개변수){}` ) , 함수 표현식 (`let 변수 = function[함수](){}` 의 다른점은 다음과 같다

1. **함수 선언식**은 함수 전체를 호이스팅한다. 정의된 범위의 맨 위로 호이스팅되서 **함수 선언 전에 함수를 사용할 수 있는 것**이다.
2. **함수 표현식**은 별도의 변수를 할당하게 되는데, 변수는 선언부와 할당부를 나누어 호이스팅한다. 선언부만! 호이스팅하게 된다.
3. 예제

   1. 함수 선언식- 정상으로 해당 값 출력 ([출처](https://taenami.tistory.com/86))

      ```jsx
      sum(50, 50); // 100
      minus(100, 50); // Uncaught TypeError: minus is not a function

      function sum(a, b) {
        // 함수 선언식
        return a + b;
      }

      var minus = function (a, b) {
        // 함수 표현식
        return a - b;
      };
      ```

      위는 호이스팅이 마치게 되면 다음과 같이 표현 할 수 있다.

      ```jsx
      function sum(a, b) { // 함수 선언식 - 함수 전체 호이스팅
        return a + b;
      };

      var minus; // 함수표현식 - 선언부만 호이스팅

      sum(50, 50); // 100
      minus(100, 50) // Uncaught TypeError: minus is not a function

      function (a,b) { // 함수 표현식 - 할당부는 그대로
        return a - b;
      }
      ```

4. 실행 컨텍스트 와 콜 스택

5. call : frunction 을 저장 → 우리가 작성한 js를 콜한다.

6. 스코프 체인, 변수 은닉화

## 실습 과제

1. b가 몇번째 라인에서 호출한 console.log 에서 찍혔는지 ?

- 내가 생각한 답 : let b = 101;
- 왜냐면 let은 블록레벨이다. let b는 첫번째 줄 let b와 동명이인일 뿐 같은 b가 아니다. 또한 동명이인인 이 b는 {}안에서만 논다.
- 결과 : 101

  ```jsx
  let b = 1;

  function hi() {
    const a = 1;

    let b = 100;

    b++;

    console.log(a, b);
  }

  //console.log(a);

  console.log(b);

  hi();

  console.log(b);
  ```

1. 수석을 풀고 돌렸을 때 error가 나는 이유와 해결법

   1. const는 블록레벨 scope이므로 funtion h1() 안에 머물고 있다면 그 밖으로 나갈 수 없다. 1번 풀이와 동일하다. 하지만 여기서는 const a라는 변수를 밖으로 빼주면 function hi{} 안에 종속되는 것이 아니니 에러가 사라진다.

   ```jsx
   let b = 1;
   const a = 1;

   function hi() {
     let b = 100;

     b++;

     console.log(a, b);
   }

   console.log(a);

   console.log(b);

   hi();

   console.log(b);
   ```

[자바스크립트란?](https://fe-churi.tistory.com/m/2)

[undefined, null,NaN](https://ryublock.tistory.com/43)
