# [Programmers] level 1(20220513)

## 1. [직사각형 별찍기](https://programmers.co.kr/learn/courses/30/lessons/12969?language=javascript)

### 문제설명

- 이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
  별(\*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.

### 제한조건

- n과 m은 각각 1000 이하인 자연수입니다.

### 풀이

```js
process.stdin.setEncoding("utf8");
process.stdin.on("data", (data) => {
  const n = data.split(" ");
  const a = Number(n[0]),
    b = Number(n[1]);

  for (let i = 0; i < b; i++) {
    let str = "";

    for (let j = 0; j < a; j++) {
      // str = str + "*";
      str += "*";
    }
    console.log(str);
  }
});
```

### 다른풀이

```js
process.stdin.setEncoding('utf8');
process.stdin.on('data', data => {
    const n = data.split(" ");
    const a = Number(n[0]), b = Number(n[1]);
    let row='';
    let square = '';
    for(let i=0; i< a; i++){
        row = row+"*";
    }
    for(let j=0; j < b; j++){
         square = square + row + '\n'

    }
console.log(square)

});
개인적으로 이 풀이 나한테 너무 어려웠다 그래서 다른 풀이를 찾아보았다.. !
```

```js
process.stdin.setEncoding("utf8");
process.stdin.on("data", (data) => {
  const n = data.split(" "); // 공백을 기준으로 배열을 만들어서
  const a = Number(n[0]),
    b = Number(n[1]); // 별 개수, 줄

  const c = "*".repeat(a); // a개만큼 별찍기
  //// 반복문을 사용하여 b만큼 돌려준다음
  for (i = 0; i < b; i++) {
    console.log(c); // 반복문을 사용하여 b만큼 돌려준다음
  }
});
```

### 배운점

- 기초가 없이 막 풀다보니까 헷갈리고 정확히 어떤 부분이 어떻게 구동되는지 정확하게 알지 못했다. 그래서 뒷 문제를 풀고 복습하러 다시 앞으로 넘어왔는데

```js
for (let i = 0; i < a; i++) {
  row = row + "*";
}
```

이 코드를 보고 i가 없는데 (배열에서는 [i]번째를 항상 가져옴) 어떻게 for문이 동작하지  
~~이건 심지어 밤 12시에 이해하였다.~~ 라면서 의문을 제기했다. (나혼자.. ) 결국 이해를 한 나에게^^..

---

## 👌🏻 2. [짝수와 홀수](https://programmers.co.kr/learn/courses/30/lessons/12937)

### 문제설명

- 정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.

### 제한조건

- num은 int 범위의 정수입니다.
- 0은 짝수입니다.

### 풀이

```js
function solution(num) {
  var answer = "";
  if (num % 2 == 0) {
    answer = "Even";
  } else {
    answer = "Odd";
  }
  return answer;
}
```

### 다른 풀이

```js
function solution(num) {
  var answer = "";
  if (Math.abs(num) % 2 == 0) {
    answer = "Even";
  } else {
    answer = "Odd";
  }
  return answer;
}
```

### 배운점

- 풀이가 잘 돌아가긴 했는데 다른 분들 문제를 찾아보니 제한조건에 int 범위의 정수라는 조건이 있었다. 그 말은 음수도 생각해야 한다는말이다.
  > 만약에 내가 `num%2==1`로 풀었다면 정답이 나오지 않는다. 음수면 결과값이 `-1`로 나오기 때문이다.
- 따라서 `Math.abs` 메소드를 사용해서 풀어준다면 훨씬 정확한 값을 찾을 수 있다!

### [+추가] 괴수의 코드

```js
function evenOrOdd(num) {
  return num % 2 ? "Odd" : "Even";
}
```

- 이건 삼항연산자라고 하는데 ? 전이 조건 : 앞이 true일때 뒤에는 false일때 실행되는 코드이다.

> 💡 javascript는 7가지 False! => 0,-0, NaN,Null,defined, false,''
> 💡 NaN은 0/0 이라고 한다. 또 0/0은 **_'숫자가 아니다!'_** 를 의미한다.

---

## 3. [가운데 글자 가져오기](https://programmers.co.kr/learn/courses/30/lessons/12903)

### 문제설명

- 단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

### 제한조건

- s는 길이가 1 이상, 100이하인 스트링입니다.

### 풀이

```js

```

### 다른 풀이

```js

```

### 배운점

## 👌🏻 4. [두 정수 사이의 합](https://programmers.co.kr/learn/courses/30/lessons/12912)

### 문제설명

- 두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution을 완성하세요. 예를 들어 a = 3, b = 5인 경우, 3 + 4 + 5 = 12이므로 12를 리턴합니다.

### 제한조건

- a와 b가 같은 경우는 둘 중 아무 수나 리턴하세요.
- a와 b는 -10,000,000 이상 10,000,000 이하인 정수입니다.
- a와 b의 대소관계는 정해져있지 않습니다.

### 풀이

```js
function solution(a, b) {
  var answer = 0;

  if (a <= b) {
    for (let i = a; i <= b; i++) {
      answer += i;
    }
  } else {
    for (let i = b; i <= a; i++) {
      answer += i;
    }
  }
  return answer;
}
```

## 👌🏻 5. [문자열을 정수로 바꾸기](https://programmers.co.kr/learn/courses/30/lessons/12925)

### 문제설명

- 문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

### 제한조건

- s의 길이는 1 이상 5이하입니다.
- s의 맨앞에는 부호(+, -)가 올 수 있습니다.
- s는 부호와 숫자로만 이루어져있습니다.
- s는 "0"으로 시작하지 않습니다.

### 풀이

```js
function solution(s) {
  return parseInt(s);
}
```
