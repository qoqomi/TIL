# [Programmers] level 1(20220515~6)

## 21. [이상한 문자 만들기](https://programmers.co.kr/learn/courses/30/lessons/12930)

### 문제설명

- 문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요

### 제한사항

- 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
- 첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

### 풀이

```js
function solution(s) {
  var answer = s.split(" ");

  var word = [];
  for (let i = 0; i < answer.length; i++) {
    var sum = [];
    for (let j = 0; j < answer[i].length; j++) {
      if (j % 2 === 0) {
        sum.push(answer[i][j].toUpperCase());
      } else {
        sum.push(answer[i][j].toLowerCase());
      }
    }
    word.push(sum.join(""));
  }

  return word.join(" ");
}
```

## 22. [자릿수 더하기](https://programmers.co.kr/learn/courses/30/lessons/12931)

### 문제설명

- 자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.
  예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.

### 풀이

```js
function solution(n) {
  var answer = n.toString().split("");
  var sum = 0;

  for (let i = 0; i < answer.length; i++) {
    sum = sum + parseInt(answer[i]);
  }
  return sum;
}
```

## 23. [자연수 뒤집어 배열로 만들기](https://programmers.co.kr/learn/courses/30/lessons/12932)

### 문제설명

- 자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

### 풀이

```js
function solution(n) {
  var answer = n.toString().split("").reverse().map(Number);

  return answer;
}
```

## 24. [정수 내림차순으로 배치하기](https://programmers.co.kr/learn/courses/30/lessons/12932)

### 문제설명

- 함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.

### 풀이

```js
function solution(n) {
  return Number(n.toString().split("").reverse().join("")); // join()괄호 안에 ''를 꼭 넣어줘야한다. 그렇지 않으면 값이 null이 되어버린다.
}
```

## 25. [정수 제곱근 판별](https://programmers.co.kr/learn/courses/30/lessons/12934)

### 문제설명

- 임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
- n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

### 풀이

```js
//만약 n이 x의 제곱이라면
// (x+1) 를 retrun
// 아니면 -1
function solution(n) {
  if (Number.isInteger(Math.sqrt(n))) {
    return Math.pow(Math.sqrt(n) + 1, 2);
  } else {
    return -1;
  }
}
```

## 26. [제일 작은 수 제거하기](https://programmers.co.kr/learn/courses/30/lessons/12935)

### 문제설명

- 수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

### 풀이

```js
function solution(arr) {
  if (arr.length <= 1) {
    return [-1];
  } else {
    arr.splice(arr.indexOf(Math.min(...arr)), 1);
  }
  return arr;
}
```

## 27. [콜라츠 추측](https://programmers.co.kr/learn/courses/30/lessons/12943)

### 문제설명

- 생략

### 풀이

```js
function solution(num) {
  var count = 0;

  for (count = 0; count < 500; count++) {
    if (num != 1) {
      if (num % 2 == 0) {
        num = num / 2;
      } else if (num % 2 == 1) {
        num = num * 3 + 1;
      }
    } else {
      return count;
    }
  }
  return -1;
}
```

## 28. [하샤드 수](https://programmers.co.kr/learn/courses/30/lessons/12947)

## 29. [3진법 뒤집기](https://programmers.co.kr/learn/courses/30/lessons/68935)

### 문제설명

- 생략

### 풀이

```js
function solution(n) {
  var answer = n.toString(3).split("").reverse().join("");
  return parseInt(answer, 3);
}

// function solution(n) {
//     return parseInt(n.toString(3).split('').reverse().join(''), 3)
// }
```

## 30. [최소직사각형](https://programmers.co.kr/learn/courses/30/lessons/86491)
