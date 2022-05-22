# ES5, ES6, ES7의 차이점

## Javascript의 ES란

- ES는 ECMA(European Computer Manufactures Association) SCRIPT의 약자이다.
- 자바스크립트는 90년대 Brendan Eich라는 사람에 의해 개발 됐다.이 후 자바스크립트를 견제하기 위해 MS에서 Jscript라는 언어를 개발해 IE(Internet Explorer)에 탑재 하였는데 이 두개의 스크립트의 표준이 필요하여 자바 스크립트를 ECMA라는 정보와 통신시스템의 비영리 표준 기구에 제출하였고 표준에 대한 작업을 ECMA-262라는 이름으로 96년 11월에 시작하여 97년 6월에 채택되었다.

### Javascript 와 ECMA Script

- 둘 다 Script지만 **자바스크립트는 언어**고, ECMA Script는 **규격, 표준**이다.

## ES5/ES6/E7 차이

### ES5

- ES4는 너무 급변하는 내용이 많아 거절되고, 그 후에 점진적 개선을 위해 ES5가 나왔다. 기본적으로 IE9부터 본격적으로 지원 하지만 ES5-shim을 사용하면 하위 버전에서도 특정 기능들을 지원 해준다.
- 배열과 관련해서 새로운 메소드들이 생겼는데 **forEach, map, filter , reduce, some, every**와 같은 메소드가 생겼다. 이 메소드들은 개발자가 **반복 횟수나 조건을 잘못 입력하는 실수를 줄여준다**.
  - Object에 대한 getter/setter 지원
  - 자바스크립트 strict 모드 지원
  - JSON지원 (원래는 XML을 사용했음)
  - bind() 메소드가 생겼다 ( this를 강제로 bind시켜줌)

### ES6(ES5 이 후 추가된 기능)

- let, const 키워드 추가
  기존 변수는 함수 scope을 가진 var 키워드를 이용하였는데, ES6에는 block scope를 가진 let과 const를 추가하였다.
  기존에는 상수형 키워드가 없어 대문자로 상수임을 표기했는데
  이젠 const가 추가되어 값의 변경을 통제할 수 있게되었다.
- arrow 문법 지원
  arrow 문법은 두 가지 장점을 제공한다. 첫 번째 익숙하고 편해지면 간결해진 코드 작성이 가능하다. 두 번째 this를 바인딩하지 않는다. - iterator / generator 추가 - module import / export 추가 - Promise 도입 ( Callback Hell을 해결해 줄 기법이 추가 되었습니다.) - Default, Rest 파라미터 - 해체 할당, Spread 연산자 - 템플릿 리터럴 - 호이스팅이 사라진 것 같은 효과 - 함수 단위 스코프에서 블록 단위 스코프로 변경
