# [Programmers] level 1(20220517~18)

## 31. [같은 숫자는 싫어](https://programmers.co.kr/learn/courses/30/lessons/12906)

### 문제설명

- 배열 arr가 주어집니다. 배열 arr의 각 원소는 숫자 0부터 9까지로 이루어져 있습니다. 이때, 배열 arr에서 연속적으로 나타나는 숫자는 하나만 남기고 전부 제거하려고 합니다. 단, 제거된 후 남은 수들을 반환할 때는 배열 arr의 원소들의 순서를 유지해야 합니다. 예를 들면,

- arr = [1, 1, 3, 3, 0, 1, 1] 이면 [1, 3, 0, 1] 을 return 합니다.
- arr = [4, 4, 4, 3, 3] 이면 [4, 3] 을 return 합니다.
- 배열 arr에서 연속적으로 나타나는 숫자는 제거하고 남은 수들을 return 하는 solution 함수를 완성해 주세요.

### 풀이

```js
function solution(arr) {
  var newbox = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] !== arr[i + 1]) {
      newbox.push(arr[i]);
    }
  }

  return newbox;
}
```

## 32. [두 개 뽑아서 더하기](https://programmers.co.kr/learn/courses/30/lessons/68644)

### 문제설명

- 정수 배열 numbers가 주어집니다. numbers에서 서로 다른 인덱스에 있는 두 개의 수를 뽑아 더해서 만들 수 있는 모든 수를 배열에 오름차순으로 담아 return 하도록 solution 함수를 완성해주세요.

### 풀이

```js
function solution(numbers) {
  let total = [];

  for (let i = 0; i < numbers.length; i++) {
    for (let n = i + 1; n < numbers.length; n++) {
      total.push(numbers[i] + numbers[n]);
    }
  }
  var get = [...total];

  var set = new Set(get);
  console.log(set);
  var end = [...set];

  return end.sort(function (a, b) {
    return a - b;
  });
}
```

## 33. [로또의 최고 순위와 최저 순위](https://programmers.co.kr/learn/courses/30/lessons/77484)

### 문제설명

- 로또 6/45(이하 '로또'로 표기)는 1부터 45까지의 숫자 중 6개를 찍어서 맞히는 대표적인 복권입니다. 아래는 로또의 순위를 정하는 방식입니다.

### 풀이

```js

```

## 34. [모의고사](https://programmers.co.kr/learn/courses/30/lessons/42840)

### 문제설명

- 수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.[이하 생략]

### 풀이

```js
function solution(answers) {
  var list = [
    [1, 2, 3, 4, 5],
    [2, 1, 2, 3, 2, 4, 2, 5],
    [3, 3, 1, 1, 2, 2, 4, 4, 5, 5],
  ];

  var point = [0, 0, 0];
  var answer = [];
  for (let i = 0; i < answers.length; i++) {
    //왜 나눠주지 .. ?
    // 왜냐면 배열을 계속 순환시켜줘야하기 때문이다 우리는 입력을 5개만 넣을 경우가 아닌 100개를 넣을 수도 있다 .
    if (answers[i] === list[0][i % 5]) {
      point[0] += 1;
    }
    if (answers[i] === list[1][i % 8]) {
      point[1] += 1;
    }
    if (answers[i] === list[2][i % 10]) {
      point[2] += 1;
    }
  }
  console.log(point);
  var max = [];
  for (let j = 0; j < point.length; j++) {
    if (max < point[j]) {
      max = point[j];
    }
  }
  for (let y = 0; y < point.length; y++) {
    if (max === point[y]) {
      answer.push(y + 1);
    }
  }
  return answer;
}
// 다른 풀이
//  function solution(answers) {
//     var answer = [];
//     var a1 = [1, 2, 3, 4, 5];
//     var a2 = [2, 1, 2, 3, 2, 4, 2, 5]
//     var a3 = [ 3, 3, 1, 1, 2, 2, 4, 4, 5, 5];

//     var a1c = answers.filter((a,i)=> a === a1[i%a1.length]).length;
//     var a2c = answers.filter((a,i)=> a === a2[i%a2.length]).length;
//     var a3c = answers.filter((a,i)=> a === a3[i%a3.length]).length;
//     var max = Math.max(a1c,a2c,a3c);
// 이렇게 비교해서 넣는 것이 위에 코드보다 훨씬 이해하기 쉽다.
//     if (a1c === max) {answer.push(1)};
//     if (a2c === max) {answer.push(2)};
//     if (a3c === max) {answer.push(3)};

//     return answer;
// }
```

## 35. [모의고사](https://programmers.co.kr/learn/courses/30/lessons/12915)

### 문제설명

- 문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 예를 들어 strings가 ["sun", "bed", "car"]이고 n이 1이면 각 단어의 인덱스 1의 문자 "u", "e", "a"로 strings를 정렬합니다.[이하 생략]

### 풀이

```js
// sort함수는 문자열에 쓰이는 함수인게 맞다 하지만 이 문제 같은 문자열 문제에서 .sort(function (a,b){return a-b}) 와 같이 오름차순 내림차순으로 정렬하면 적용되지 않는다 .숫자만 적용되기 때문
// 또한 return 1 , -1값을 받아 알아서 오름차순과 내림차순을 정렬해준다.
function solution(strings, n) {
  return strings.sort((a, b) => {
    if (a[n] > b[n]) {
      return 1;
    }
    if (a[n] < b[n]) {
      return -1;
    }
    if (a[n] === b[n]) {
      if (a > b) {
        return 1;
      }
      if (a < b) {
        return -1;
      }
    }
  });
}
```

## 36. [문자열 내림차순으로 배치하기](https://programmers.co.kr/learn/courses/30/lessons/12917)

### 문제설명

- 문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요. s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

### 풀이

```js
function solution(s) {
  //sort 함수 ! 오름차순으로 작용 . 위와 동일하다
  return s.split("").sort().reverse().join("");
}
```

## 37. [소수 만들기](https://programmers.co.kr/learn/courses/30/lessons/12977)

## 38. [숫자 문자열과 영단어](https://programmers.co.kr/learn/courses/30/lessons/81301)

## 39. [시저 암호](https://programmers.co.kr/learn/courses/30/lessons/12926)

### 문제설명

- 어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 됩니다. "z"는 1만큼 밀면 "a"가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.

### 풀이

```js
1. 알파벳 대문자(65) < 소문자(97)
2. a - > z 숫자가 더 커진다.
3. 알파벳 -> 숫자 : char->CodeAt
4. 숫자 -> 알파벳 : from->CharCode


function solution(s, n) {
    let result = "";
    for (let i=0; i<s.length;i++) {
        if ( s[i] == ' ' )
            result += ' '
        else
            result += String.fromCharCode( (s.charCodeAt(i)>90)

                    ? (s.charCodeAt(i)+n-97)%26+97
                    : (s.charCodeAt(i)+n-65)%26+65)
    }
    return result;
}
```

## 40. [신규 아이디 추천](https://programmers.co.kr/learn/courses/30/lessons/72410)
