# [Programmers] level 1(20220515~6)

## 16. [문자열 내 p와 y의 개수](https://programmers.co.kr/learn/courses/30/lessons/12916)

### 문제설명

- 대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

- 예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

### 제한사항

- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있습니다.

### sudo code

    // 1.입력 : s"문자열"
    // 2, 문자열 i번째를 p가 있는지 비교한다.
    // 3. 만약 p가 있다면 p개수를 count 해라
    // 4. 문자열 i번째를 y가 있는지 비교한다.
    // 5. 만약 y가 있다면 y의 개수를 count 해라
    // 6. p의 개수와 y의 개수가 같다면
    // 7. true
    // 8. 같지 않다면 false
    // 4. 아무것도 없는 경우 true

### 풀이

```js
function solution(s) {
  var answer = true;
  var p = 0;
  var y = 0;
  for (let i = 0; i < s.length; i++) {
    if (s[i] === "p" || s[i] === "P") {
      //대,소문자 구별을 해주지 않는다면 오류
      p++;
    } else if (s[i] === "y" || s[i] === "Y") {
      y++;
    }
  }
  if (p != y) {
    return false;
  }

  return answer;
}
```

### 다른풀이

```js
function numPY(s) {
  //함수를 완성하세요
  return (
    s.toUpperCase().split("P").length === s.toUpperCase().split("Y").length
  );
}
```

## 17. [문자열 다루기 기본](https://programmers.co.kr/learn/courses/30/lessons/12918)

### 문제설명

- 문자열 s의 길이가 4 혹은 6이고, 숫자로만 구성돼있는지 확인해주는 함수, solution을 완성하세요. 예를 들어 s가 "a234"이면 False를 리턴하고 "1234"라면 True를 리턴하면 됩니다.

### 제한사항

- s는 길이 1 이상, 길이 8 이하인 문자열입니다

### sudo code

// 1. 입력: "string"
// 2. 출력 : boolean
// 3. s의 길이가 4 or 6이고 그렇지 않으면 false를 retrun한다. // 1조건 끝  
// 4. 문자가 들어있다면 false //2시작
// 5. 숫자만 있다면 true

### 풀이

```js
function solution(s) {
  var answer = true;

  if (!(s.length === 4 || s.length === 6)) {
    return false;
  }

  for (let i = 0; i < s.length; i++) {
    if (isNaN(Number(s[i]))) {
      // isNaN과 Number 함수의 대소문자를 유의하자
      return false;
    }
  }
  return answer;
}
```

### 풀이 참조

1. isNaN = is not a number

- true or false 를 반환하므로 그런 조건으로 만들어줘야한다. => Number(s[i])를 씌우면 true or false를 출력한다.

### 다른풀이

```js
function alpha_string46(s) {
  return s.length == 4 || s.length == 6 ? !isNaN(s) : false;
}
```

## 18. [서울에서 김서방 찾기](https://programmers.co.kr/learn/courses/30/lessons/12919)

### 문제설명

- String형 배열 seoul의 element중 "Kim"의 위치 x를 찾아, "김서방은 x에 있다"는 String을 반환하는 함수, solution을 완성하세요. seoul에 "Kim"은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

### 제한사항

- seoul은 길이 1 이상, 1000 이하인 배열입니다.
- seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.
- "Kim"은 반드시 seoul 안에 포함되어 있습니다.

### sudo code

    //var answer = '';
    // 입력: 배열
    // 출력 :string(김서방은"x"에 있다)
    // 1. 배열의 0 번째에 kim..? 있다면
    // 2. 김서방은 0에 있다
    // 3. 만약에 1번째에 kim이 있다면
    // 4. 김서방은 1에 있다
    // `김서방은 ${i}에 있다`

### 풀이

```js
function solution(seoul) {
  for (let i = 0; i < seoul.length; i++) {
    if (seoul[i] === "Kim") {
      return `김서방은 ${i}에 있다`;
    }
  }
}
```

### 풀이 참조

- `김서방은 ${i}에 있다` -> 이런쓰임은 처음이다 알아두자

## 19. [수박수박](https://programmers.co.kr/learn/courses/30/lessons/12922)

### 문제설명

- 길이가 n이고, "수박수박수박수...."와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 "수박수박"을 리턴하고 3이라면 "수박수"를 리턴하면 됩니다.

### 제한사항

- n은 길이 10,000이하인 자연수입니다.

### sudo code

    // 만약 첫번째가 홀수라면 수 를 출력한다
    // 두번째가 짝수면 박을 출력한다
    // 그렇게 i번 돈다
    //n에 값을 push 한다.

### 풀이

```js
function solution(n) {
  var answer = "";
  for (let i = 1; i <= n; i++) {
    if (i % 2 === 1) {
      answer = answer + "수";
    } else {
      answer = answer + "박";
    }
  }

  return answer;
}
```

### 풀이 참조

1. 처음에 돌렸을 때 '박박박'만 나왔다. 왜냐면

```js
        if(n[i] % 2 === 1){
            answer = answer + "수";
```

- n을 배열안에 넣었기때문이다.n은 이미 숫자이므로 .length를 해줄 필요도, 배열안에 넣어서 표현할 필요도 없다.

### 다른 풀이

```js
const waterMelon = (n) => {
  return "수박".repeat(n / 2) + (n % 2 === 1 ? "수" : "");
};
```

- repeat 함수 : `string.repeat( count )`
  - 'abc'.repeat( 2 ) -> 'abcabc'

## 20. [완주하지 못한 선수](https://programmers.co.kr/learn/courses/30/lessons/42576)

### 문제설명

- 수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.
- 마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.

### 제한사항

- 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.
- completion의 길이는 participant의 길이보다 1 작습니다.
- 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.
- 참가자 중에는 동명이인이 있을 수 있습니다.

### sudo code

### 풀이

### 풀이 참조

### 다른 풀이
