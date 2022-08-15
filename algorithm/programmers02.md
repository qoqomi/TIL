# [Programmers] level 1(20220513)

## 6. [없는 숫자 더하기](https://programmers.co.kr/learn/courses/30/lessons/86051)

### 문제설명

- 0부터 9까지의 숫자 중 일부가 들어있는 정수 배열 numbers가 매개변수로 주어집니다. numbers에서 찾을 수 없는 0부터 9까지의 숫자를 모두 찾아 더한 수를 return 하도록 solution 함수를 완성해주세요.

### 제한사항

- 1 ≤ numbers의 길이 ≤ 9
- 0 ≤ numbers의 모든 원소 ≤ 9
- numbers의 모든 원소는 서로 다릅니다.

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

### 다른풀이

```js
function solution(numbers) {
  return 45 - numbers.reduce((acc, acr) => acc + acr);
  // number.reduce((acc,acr) => (acr+acc)) 괄호가 어떻게 들어가는지 잘 보고
}
```

### 문제풀이

1. `.includes()` : 특정 문자열이 특정 문자열을 포함하는지 확인하는 메서드
   - 특정 문자열을 구분하는 메서드가 필요할 것 같다! 라는 생각이 들어 구글링 해봤다.
   - 문법
     `string.includes(searchString,length)`
     - searchString : 검색할 문자열의 필수 요소이다. 대소문자를 구별합니다.
     - length : 검색을 시작할 위치입니다. 값이 없다면 전체 문자열을 대상으로 합니다. - true, false 반환
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

### 👎🏻 풀이

```js
function solution(absolutes, signs) {
  var answer = 0;

  for (let i = 0; i < absolutes.length; i++) {
    //만약 signs의 i 번째가 true(양수)라면
    if (signs[i] == true) {
      answer += absolutes[i];
      // i번째 false(음수)라면
    } else {
      answer -= absolutes[i];
    }
  }
  return answer;
}
```

### 문제풀이

1.`for(let i = 0; i < absolutes.length; i++)`

- 문제 푸는게 오래걸렸던 이유 중 하나
- `i <= absolutes.length;`일 때 작동이 되지 않는다
- 왜... 냐면 이유를 알았다. .`length`는 1부터 1,2,3,4 이렇게 1부터 시작하고 i는 초기값이 0 이므로 `=<`를 사용하게 되면 1234 01234 의 차이를 가지게 된다.

### 새로운 풀이 
```js
function solution(absolutes, signs) {
  return absolutes.reduce((acc,acr,idx)=> acc + acr*(signs[idx] ? 1 : -1),0)
}
```
- 이런 경우에는 reduce를 사용하는데 누적기 역할을 주로 하며 누적하여 계산해준다. accr값을 지정해놨었는데 그건 큰 5산이였음
acc값이 초기값으로 0 이 들어가고 그 뒤에 해당하는 부분부터 acr로 누적되어 계산됨을 알고 있어야한다.

## 8. [평균 구하기](https://programmers.co.kr/learn/courses/30/lessons/12944)

### 문제설명

- 정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

### 제한사항

- arr은 길이 1 이상, 100 이하인 배열입니다.
- arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

### 👍🏻 풀이

```js
function solution(arr) {
  var answer = 0; //변수의 값을 초기화
  // arr배열길이만큼 반복문
  for (i = 0; i < arr.length; i++) {
    // 입력된 정수는 모두 더해준다.
    answer += arr[i];
  }
  // 배열길이만큼 나눔으로 평균값을 구한다.
  return answer / arr.length;
}
```

---

## reduce 함수

- 찾아보다가 reduce함수가 좋다고 조원분도 추천해서 보내주셨다.
- reduce 함수는 연산문제 제외하고도 다른 곳에도 많이 쓰인다는데 아직 거기까진 이해할 수 없었다..ㅋㅋ!!
- 이와 같이 sort, every, some, find, findIndex, includes도 다 reduce로 구현 가능합니다. reduce가 이들 모두의 아버지였던 것입니다. ㅠㅠ 라면서 보내주신 [reduce의 링크](https://www.zerocho.com/category/JavaScript/post/5acafb05f24445001b8d796d)
