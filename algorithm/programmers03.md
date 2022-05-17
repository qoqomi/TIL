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

- map 함수의 쓰임새
  ```js
  var num = [1,2,3,4]
  arr1.map( ()=> ) // 괄호를 먼저 만들어주고
  arr1.map( (values,index)=> ) // values는 num 배열안에 하나하나의 item을 가져온다. 이게 callback함수라는거고 values, index는 변수라 다른 값을 넣어도 상관없다.
  ```
  - 따라서
  ```js
   var num = [1,2,3,4]
   var sample = b.map(values = > values*2)
   // 이러면 출력값이 [2, 4, 6, 8] 이 된다.
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

### 다른풀이

```js
function solution(x, n) {
  return Array(n)
    .fill(x)
    .map((v, i) => (i + 1) * v);
  // 1. Array(n)의 배열 생성 -> fill로 x값을 채워준다
  // 2. map(v)->callbac함수로 x값을 불러오고
  // 3. i는 indexr값
  // 4. i는 0 부터 시작하므로 +1해주고 i*v 로 retrun
}
```

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

### [가우스](https://velog.io/@elinapark/%EA%B0%80%EC%9A%B0%EC%8A%A4-%EA%B3%B5%EC%8B%9D%EB%93%B1%EC%B0%A8%EC%88%98%EC%97%B4%EC%9D%98-%ED%95%A9)로 한다면.. ?

1. 이용료 price , 횟수 count 내가 가진 돈 money 에 가우스를 사용하면
   이용료 _ 마지막 이용횟수 _ (마지막 이용횟수 + 1) / 2 는 이용하는 지불값이고
   거기서 내 돈을 빼준다.

```js
function solution(price, money, count) {
  const result = (price * count * (count + 1)) / 2 - money;
}
```

2. 금액이 부족하지 않으면 0 으로 return하라함. 부족하지 않다는건 내 돈이 많다는거니까

```js
//result > 0 이면 true 아니면 0
return result > 0 ? result : 0;
```

- 이해안감 .. ㅋ

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
function solution(a, b) {
  var date = new Date(2016, a - 1, b);
  console.log(date.toString()); //Tue May 24 2016 00:00:00 GMT+0900 (Korean Standard Time)
  return date.toString().slice(0, 3).toUpperCase();
}
```

## 14. [나누어 떨어지는 숫자 배열](https://programmers.co.kr/learn/courses/30/lessons/12910)

### 문제설명

- array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요. divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

### 제한사항

- arr은 자연수를 담은 배열입니다.
- 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
- divisor는 자연수입니다.
- array는 길이 1 이상인 배열입니다.

### 👎🏻 풀이

```js
function solution(arr, divisor) {
  var answer = [];
  for (let i = 0; i < arr.length; i++) {
    // i는 arr의 index
    if (arr[i] % divisor === 0) {
      // 만약 arr의 i번째의 원소가 divisor로 나누었을 때 0이라면
      answer.push(arr[i]); // answer에 넣어준다.
    }
  }
  // 주의할점은  나머지 원소는 버려지기 때문에 담을 필요가 없어 for문을 나가야 한다는 거다 .
  answer.sort(function (a, b) {
    return a - b;
  }); //sort로 오름차순 선언
  if (answer.length === 0) {
    // 새로운 if문으로 answer값이 없을때 -1 push
    answer.push(-1);
  }
  return answer;
}
```

### 다른풀이

```js
function solution(arr, divisor) {
  var answer = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] % divisor === 0) answer.push(arr[i]);
  }

  return answer.length > 0 ? answer.sort((a, b) => a - b) : [-1];
}
```

### 배울점

1. sort 함수

```js
//오름차순
변수.sort(function (a, b) {
  return a - b;
});
//내림차순
변수.sort(function (a, b) {
  return b - a;
});
```

---

## 15. [내적](https://programmers.co.kr/learn/courses/30/lessons/12910)

### 문제설명

- 길이가 같은 두 1차원 정수 배열 a, b가 매개변수로 주어집니다. a와 b의 내적을 return 하도록 solution 함수를 완성해주세요.
- 이때, a와 b의 내적은 a[0]*b[0] + a[1]*b[1] + ... + a[n-1]\*b[n-1] 입니다. (n은 a, b의 길이)

### 제한사항

- a, b의 길이는 1 이상 1,000 이하입니다.
- a, b의 모든 수는 -1,000 이상 1,000 이하입니다.

### 👎🏻 풀이

```js
function solution(a, b) {
  //var answer = [];
  var sum = 0;
  for (let i = 0; i < a.length; i++) {
    sum = sum + a[i] * b[i];
  }
  return sum;
}
```

### 다른풀이

```js
a.reduce;
```

### 배울점

1. 배열요소를 곱해서 모두 더하기(number) vs 배열 요소마다 곱하기(배열)

- 배열요소를 곱해서 모두 더하기
  - 입력값 :a= [1,2,3,4],b=[-3,-1,0,2]
  - 과정 : (1 _ -3) + (2_-1) + (3 _ 0) + (4 _ 2) = -3 -2 + 0 +8 =3
  - 출력값 :sum = 3

```js
function solution(a, b) {
  //var answer = [];
  var sum = 0;
  for (let i = 0; i < a.length; i++) {
    sum = sum + a[i] * b[i];
  }

  return sum;
}
```

/ 배열 요소마다 곱하기 (배열)

- 입력값 :a= [1,2,3,4],b=[-3,-1,0,2]
- 과정 : [(1 * -3), (2*-1) + (3 * 0) , (4 * 2) ]
- 출력값 :sum = [-3,-2,0,8]

```js
function solution(a, b) {
  //var answer = [];
  var sum = [];
  for (let i = 0; i < a.length; i++) {
    sum.push(a[i] * b[i]);
  }

  return sum;
}
```

---
