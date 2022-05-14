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
  var answer = "";
  for (let i = 0; i < phone_number.length; i++) {
    if (i >= phone_number.length - 4) {
      answer += phone_number[i];
    } else {
      answer += "*";
    }
  }
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
    let sum = [];
    for (let j = 0; j < arr1[i].length; j++) {
      sum.push(arr1[i][j] + arr2[i][j]);
    }
    answer.push(sum);
  }
  return answer;
}
```

### 다른 풀이

```js
function solution(arr1, arr2) {
  var answer = [[]];

  for (let i = 0; i < arr1.length; i++) {
    answer[i] = [];
    for (let j = 0; j < arr1[i].length; j++) {
      answer[i].push(arr1[i][j] + arr2[i][j]);
    }
  }
  return answer;
}
```

- 다른 풀이가 훨씬 쉬운 것 같기도 .. ? 근데 처음에 빈 값을 answer[i]에 넣어준다는 생각에 도달하기까지가 어려워던 것 같다. ㄷ
- 2차원 배열은 처음인데 약간 어제 풀었던 첫문제 별모양으로 직사각형 만들기랑 비슷한 느낌 ㅋㅋㅋ 별모양 직사각형 못잃어 ..

### [+추가] 괴수의 코드

```js
function solution(arr1, arr2) {
  return arr1.map((arr, i) => arr.map((n, j) => n + arr2[i][j]));
}
```

화살표함수가 두번 .. ? 이건 좀 더 자료를 읽어봐야할듯

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

2.[map()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

## 11. [x만큼 간격이 있는 n개의 숫자](https://programmers.co.kr/learn/courses/30/lessons/12954)

### 문제설명

- 함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

### 제한사항

- x는 -10000000 이상, 10000000 이하인 정수입니다.(n은 1000 이하인 자연수입니다.)

### 👎🏻 풀이

### 다른 풀이

### [+추가] 괴수의 코드

### 배운점
