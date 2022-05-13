# [Programmers] level 1(20220513)

## 6. [없는 숫자 더하기](https://programmers.co.kr/learn/courses/30/lessons/86051)

### 문제설명

- 0부터 9까지의 숫자 중 일부가 들어있는 정수 배열 numbers가 매개변수로 주어집니다. numbers에서 찾을 수 없는 0부터 9까지의 숫자를 모두 찾아 더한 수를 return 하도록 solution 함수를 완성해주세요.

### 제한사항

- 1 ≤ numbers의 길이 ≤ 9
- 0 ≤ numbers의 모든 원소 ≤ 9
- numbers의 모든 원소는 서로 다릅니다.

### 문제

```js
function solution(numbers) {
  var answer = -1;
  return answer;
}
```

### 👎🏻 풀이

```js
function solution(numbers) {
  var answer = 0;
  // i가 0~9까지 숫자
  for (let i = 0; i < 10; i++) {
    // index에 포함되어있지 않다면 answer에 넣어준다.
    if (!numbers.includes(i)) answer += i;
  }
  return answer;
}
```

### 문제풀이

1. `.includes()` : 특정 문자열이 특정 문자열을 포함하는지 확인하는 메서드
   - 특정 문자열을 구분하는 메서드가 필요할 것 같다! 라는 생각이 들어 구글링 해봤다.
   - 문법
     `string.includes(searchString,length)` - searchString : 검색할 문자열의 필수 요소이다. 대소문자를 구별합니다. - length : 검색을 시작할 위치입니다. 값이 없다면 전체 문자열을 대상으로 합니다. - true, false 반환
   - 예
     `includes('z')`
     - z를 포함하므로 true를 반환
2. !(논리 연산자) : not 과 같다

## 7. [음양 더하기](https://programmers.co.kr/learn/courses/30/lessons/76501)

### 문제설명

- 어떤 정수들이 있습니다. 이 정수들의 절댓값을 차례대로 담은 정수 배열 absolutes와 이 정수들의 부호를 차례대로 담은 불리언 배열 signs가 매개변수로 주어집니다. 실제 정수들의 합을 구하여 return 하도록 solution 함수를 완성해주세요.

### 제한사항

- absolutes의 길이는 1 이상 1,000 이하입니다.
  - absolutes의 모든 수는 각각 1 이상 1,000 이하입니다.
- signs의 길이는 absolutes의 길이와 같습니다.
  - signs[i] 가 참이면 absolutes[i] 의 실제 정수가 양수임을, 그렇지 않으면 음수임을 의미합니다.

### 문제 이해

- inputdmfh 2개의 매개변수가 주어집니다.
  1. 정수배열:absolutes
  2. 부호: signs (true이면 양수, false이면 음수)

### 조건

1. 반복문을 통해서 두 배열을 순회한다.
2. signs은 양수면 true, 음수면 false
3. 반복이 끝나면 모든 값 return

### 문제

```js
function solution(absolutes, signs) {
  var answer = 123456789;
  return answer;
}
```

### 풀이

```js

```

### 문제풀이
