# [Programmers] level 1(20220514)

## 9. [핸드폰 번호 가리기](https://programmers.co.kr/learn/courses/30/lessons/12948)

### 문제설명

- 프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다.
- 전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 \*으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

### 제한사항

- phone_number는 길이 4 이상, 20이하인 문자열입니다.

### 👎🏻 풀이

```js
function solution(phone_number) {
  var answer = phone_number.length - 4;
  return "*".repeat(answer) + phone_number.slice(-4);
}
```

### 다른풀이

```js
function solution(phone_number) {
  var answer = "*".repeat(phone_number.length - 4) + phone_number.slice(-4);
  return answer;
}
```

## 10. [행렬의 덧셈](https://programmers.co.kr/learn/courses/30/lessons/12950)

### 문제설명

- 행렬의 덧셈은 행과 열의 크기가 같은 두 행렬의 같은 행, 같은 열의 값을 서로 더한 결과가 됩니다. 2개의 행렬 arr1과 arr2를 입력받아, 행렬 덧셈의 결과를 반환하는 함수, solution을 완성해주세요.

### 제한사항

- 행렬 arr1, arr2의 행과 열의 길이는 500을 넘지 않습니다.

### 👎🏻 풀이

```js
function solution(arr1, arr2) {
  var answer = [];

  for (let i = 0; i < arr1.length; i++) {
    [1, 2][(3, 4)];
    let sum = []; //비어있는 sum 배열변수를 넣어준다
    for (let j = 0; j < arr1[i].length; j++) {
      sum.push(arr1[i][j] + arr2[i][j]);
    }
    answer.push(sum); // 결국 answer이라는 변수안에도 sum을 push해줘야만 한다.
  }
  return answer;
}
```

### 다른 풀이

```js
function solution(arr1, arr2) {
  var answer = [[]];

  for (let i = 0; i < arr1.length; i++) {
    answer[i] = []; //이해가 잘 가지 않음.
    for (let j = 0; j < arr1[i].length; j++) {
      answer[i].push(arr1[i][j] + arr2[i][j]);
    }
  }
  return answer;
}
```

### 또 다른 풀이

```js
function solution(arr1, arr2) {
  var answer = []; // 1차원 배열만 선언
  for (let i = 0; i < arr1.length; i++) {
    // i만큼 비어있는 배열을 push해준다.-> 2차원배열을 만들어주는과정
    answer.push([]);
    // 사실 이 부분이 완벽하게 이해가 가진 않는다. 배열 안에 행렬대로 넣어주는 건 맞는데... 나 사실 바보일지도.. ? ㅎ
    for (let j = 0; j < arr1[i].length; j++) {
      answer[i].push(arr1[i][j] + arr2[i][j]);
    }
  }
  return answer;
}
```

- 근데 처음에 빈 값을 answer[i]에 넣어준다는 생각에 도달하기까지가 어려워던 것 같다.
- 나는 왜 이해가 안되니.😇

### [+추가] 괴수의 코드

```js
function solution(arr1, arr2) {
  return arr1.map((arr, i) => arr.map((n, j) => n + arr2[i][j]));
}
```

- 화살표함수가 두번 .. ? 이건 좀 더 자료를 읽어봐야할듯

### 배운점

1. [2차원 배열](https://dojang.io/mod/page/view.php?id=307)

- 자료형 배열이름[[세로크기][가로크기]];
- 자료형 배열이름[세로크기][가로크기]={{값,값,값}.{값,값,값}};
- 예를 들어서 세로크기가 3, 가로 크기가 4인 in형 2차원 배열을 선언한다면

```js
int arr[3][4] =
    {{가로요소4},
    {가로요소4},
    {가로요소4}
    }; // 세로 3줄 가로 요소 4
```

2. [map()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

- 함수 쓰임새를 설명하다가 이해가 가는 게 있어서 가져와본다.

```js
const nums = [1, 2, 3]; // 1,2,3을 배열에 넣는다.
let newNums = []; // 비어있는 배열
for (var i = 0; i < nums.length; i++) {
  newNums.push(nums[i] * 2); // nums길이만큼 i가 for문에서 돌고 끝난다. 조건은 num[i]를 *2 push (nums.length는 1부터 시작하므로 배열길이를 셈할때는 '<' 를 기본으로 사용한다.)
}
console.log(newNums);

// Result
[2, 4, 6];
```

- 위 함수를 map으로 바꾸면

```js
const nums = [1, 2, 3]; // 1,2,3을 배열에 넣는다.
const newNums = nums.map((x) => x * 2);
console.log(nuwNums);
```

## 11. [x만큼 간격이 있는 n개의 숫자](https://programmers.co.kr/learn/courses/30/lessons/12954)

### 문제설명

- 함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

### 제한사항

- x는 -10000000 이상, 10000000 이하인 정수입니다.(n은 1000 이하인 자연수입니다.)

### 👎🏻 풀이

```js
function solution(x, n) {
  var answer = [];

  for (let i = 1; i <= n; i++) {
    // i값이 1,2,3,4 -> 처럼 되어야 x에 곱해지기 때문에 i = 1 로 시작하는 것에 주의하자. 또한 마지막 i의 값도 같아야 하므로 <=로 입력하기로 한다.
    answer.push(i * x);
  }
  return answer;
}
```

### 배운점

## 12. [부족한 금액 계산하기](https://programmers.co.kr/learn/courses/30/lessons/82612)

### 문제설명

- 새로 생긴 놀이기구는 인기가 매우 많아 줄이 끊이질 않습니다. 이 놀이기구의 원래 이용료는 price원 인데, 놀이기구를 N 번 째 이용한다면 원래 이용료의 N배를 받기로 하였습니다. 즉, 처음 이용료가 100이었다면 2번째에는 200, 3번째에는 300으로 요금이 인상됩니다.
  놀이기구를 count번 타게 되면 현재 자신이 가지고 있는 금액에서 얼마가 모자라는지를 return 하도록 solution 함수를 완성하세요.
  단, 금액이 부족하지 않으면 0을 return 하세요.

### 제한사항

- 놀이기구의 이용료 price : 1 ≤ price ≤ 2,500, price는 자연수
- 처음 가지고 있던 금액 money : 1 ≤ money ≤ 1,000,000,000, money는 자연수
- 놀이기구의 이용 횟수 count : 1 ≤ count ≤ 2,500, count는 자연수

### 👎🏻 풀이

```js
function solution(price, money, count) {
  var total = 0;

  for (let i = 1; i <= count; i++) {
    total += price * i;
  }

  return money > total ? 0 : Math.abs(total - money);
}
```

### 배운점

1. 삼항연산자
   `조건 ? true : false`

## 13. [2016년](https://programmers.co.kr/learn/courses/30/lessons/12901)

### 문제설명

- 2016년 1월 1일은 금요일입니다. 2016년 a월 b일은 무슨 요일일까요? 두 수 a ,b를 입력받아 2016년 a월 b일이 무슨 요일인지 리턴하는 함수, solution을 완성하세요. 요일의 이름은 일요일부터 토요일까지 각각 SUN,MON,TUE,WED,THU,FRI,SAT입니다. 예를 들어 a=5, b=24라면 5월 24일은 화요일이므로 문자열 "TUE"를 반환하세요.

### 제한사항

- 2016년은 윤년입니다.
- 2016년 a월 b일은 실제로 있는 날입니다. (13월 26일이나 2월 45일같은 날짜는 주어지지 않습니다)

### 👎🏻 풀이

```js

```

### 배운점

function solution(arr, divisor) {
var answer = [];
for (let i=0; i<arr.length; i++) {
// divisor로 나누어 떨어지면 배수이므로 값을 담기
if (arr[i] % divisor == 0) {
answer.push(arr[i])
}
}
// 삼항연산자 배열에 값이 없으면 [-1] 반환. 값이 있을 경우 오름차순 정렬하여 반환.
return answer.length == 0? [-1]:answer.sort((a,b)=>a-b);
}

function solution(arr, divisor) {
const answer = arr.filter((num) => num % divisor === 0);
return answer.length === 0 ? [-1] : answer.sort((a, b) => a - b);
}
}
