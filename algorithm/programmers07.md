# [Programmers] level 1(20220815~)

## 1. [완주하지 못한 선수](https://school.programmers.co.kr/learn/courses/30/lessons/42576)

### 문제풀이
```js
function solution(participant, completion) {
  
    participant.sort();
    completion.sort(); 

    for(let i=0; i<participant.length; i++){
        // participant와 같지 않은 것들만 모아 return
        if(participant[i] !== completion[i])
            return (participant[i])
    }
 
}
```

### 이해 및 풀이설명
- 원래 filter함수로 풀고 있었는데 filter를 사용한다면 출력값이 Boolean이기때문에 걸러낼 수는 있지만 값을 도달하는데 다른 함수를 추가적으로 사용해야한다. 
따라서 for문을 사용해서 다시 풀어보았다.


## 2. [k번째 수](https://school.programmers.co.kr/learn/courses/30/lessons/42748)

### 문제 풀이
```js
function solution(array, commands) {
     var answer = [];

    for(let i=0; i<commands.length; i++){
    const a = array.slice(commands[i][0]-1,commands[i][1]).sort((a,b)=>{return a-b})
    answer.push(a[commands[i][2]-1])
    }
   
    return answer;
}
```
### 이해 및 풀이설명
- sort 사용 
    - `sort((a,b)=>{대괄호를 붙여서 사용})`
- `-1`을 해주지않으면 1번째를 지목했을 때 2번째부터 지목하게 된다. 우리는 0 번째가 아닌 0번째는 1번째로 사용되어야하기 때문이다.

