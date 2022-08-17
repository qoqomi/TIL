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

---

## ✨Infinity vs Nan 

Infinity 와 NaN은 미리 정의된 변수이다. 
infinity는 양의 무한대이며 NaN은 숫자가 아닌 값 (Not a Number)를 표현한다. 

### Infinity
자바스크립트에서 표현할 수 있는 양의 수를 넘는 **무한대**를 나타내기도 한다. 
또한 어떤 수를 **0으로 나누었을 때** 나오는 값이기도 하다. 

### NaN
자바스크립트에서 숫자가 아닌 값을 나타낸다. 
Nan은 특이하게 자기 자신과 다른 값을 비교할 수 없다.
그렇기 때문에 숫자인지 아닌지는 inNaN() 함수를 사용하여 비교한다.

`Math.min`함수를 사용 중 배열에서는 min과 max를 사용할 수 없다.
Math.min,max는 배열이 아니라 고유한 변수를 기대하기 때문이다. 
Es6/ES2015 문법에서부터 사용할 수 있게 되었다. 

1. `Math.min.apply(null,arr)` 

```js
const arr = [30, 40, 10, 20];
let answer= Math.min.apply(null,arr)

```

2. 스프레드 [...] 문법 
```js
const arr = [30, 40, 10, 20];
let answer = Math.min(...arr)
```
---
### Q6. 홀수 
- 자연수의 홀수인 자연수를 모두 골라서 그 합을 구하고 고른 홀수들 중 최소값을 찾는 프로그램을 작성하라 . 

---
#### ✨ minNumber 초기화
>💡 안정적인 가장 큰 수로 초기화 -> 안정적? 정수를 정확하고 올바르게 비교할 
       수 있다. 

사용법은 아래와 같다. 

```js

let sum = 0, min=Number.Max_SAFE_INTEGER;
```

---

#### 문제풀이
```js
		function solution(arr) {
		
		let answer = [];
		
		// sum: 홀수의 합 저장 , min: 최소값 저장
		
		let sum = 0 , min = Number.MAX_SAFE_INTEGER;
		
		//새로운 for문 : x에 arr에 속해있는 배열값이 차례로 들어간다.
		
		for(let x of arr){
		
		if(x%2 === 1){
		
		sum +=x;

		// 이런방식으로 제일 작은 값을 구할 수 있다.
		if(x<min) min=x;
		
		}
		
		}
		
		answer.push(sum);
		answer.push(min);
		
		return answer;
		
		}
		
		arr = [12, 77, 38, 41, 53, 92, 85];
		
		console.log(solution(arr));
		
```


### Q7. 10부제
- %는 나머지를 알려준다.  / 는 몫을 알려준다.  좀 까먹지좀 ㅁ ㅏ .. 
- 
```js
<script>

function solution(day, arr) {

	let answer = 0;
	
	for(let x of arr){
	
		if(x % 10 === day){
		
		answer+=1
		
		}

}

return answer;

}

  

arr = [25, 23, 11, 47, 53, 17, 33];

console.log(solution(3, arr));

</script>

```