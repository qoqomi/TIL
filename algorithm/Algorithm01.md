**본 내용은 자바스크립트 알고리즘 문제풀이 강의를 토대로 작성하였습니다.**
### 유사배열객체과 배열의 차이 (Array.from 뭐냐?)
- 유사 객체 배열은 배열처럼 보이지만 key가 숫자이고 length값을 가지고 있는 객체를 말한다. 
- 배열같이 생겼지만 사실 **객체.. !** 이다. 
- 유사 배열 객체와 일반객체의 중요한 차이가 있다.
forEach,map,filter,reduce 같은 메서드를 사용할 수 없다는 것이다. 
----
이럴때에는 Array.from() 메서드를 사용한다. 

> Array.from() 메서드는 유사 배열 객체(array-like-Object )나 반복 가능한 객체(iterable object)를 얕게 복사해 새로운 Array 객체를 만든다. 

---
일단 유사배열객체와 배열의 차이점을 직관적이게 봐보자.
1. 아래와 같은 array를 만들고 어떤 값이 출력되는지 봤다.
```js
const array=[1,2,3,4,5]
```
![[스크린샷 2022-08-25 오후 3.35.48.png]]

예상하던 것과 같이 array에서 나오는 것과 동일한 결과값이 나왔다. (인덱스와 값, length의 속성)
2. 위와 같은 구성으로 만든 것이 유사 배열 객체이다.  

```js
const likeObj ={0:1,
                1:2, 
                2:3,
               length:3
               }
```
예상했던 결과대로 Prorotype은 객체로 나왔다.


- 위와같이 객체형태로 만들어놓고 이 값을 Array.from으로 돌려보았다. 

결과값이 ? Array(0)으로 바뀌었다.  !!
얕게 복사해서 새로운 배열을 만든 것이다. 

그럼이제 length:5 를 넣으면 어떤 값을 반환하는지 봐야한다. 

Holly.. 신기하다. 
length값 안에 undefined로 채워진 배열을 반환한다. 

### 하지만 내가 원하는 것은 undefined를 1로 초기화해주길 바라는 것임 
```js
let n=arr.length;
		                 
answer=Array.from({length:n}, ()=>1);
```
이렇게 된다면 만약 길이가 5인 경우[1,1,1,1,1] 의 값을 반환한다. 
아래 스크린샷을 보면 더 직관적이다. 


----
## 큰 수 출력하기
### 조건정리 
- 맨 첫번째값은 무조건 출력된다. 
- 자신의 바로 앞 수보다 큰 수만 출력한다. 
```js
function solution(arr) {

// 큰 수를 찾는 것과 같은 로직 
let answer=[],max=arr[0]
// 첫번째 수를 먼저 넣어준다. 
answer.push(arr[0])
// 1번째부터 차례로 돌면서 자신보다 앞 수보다 크면 answer에 넣어주고 max에 그 수로 바꾸어 준다.
for(let i=1; i<arr.length; i++){

if(arr[i-1] < arr[i]){

answer.push(arr[i])

max=arr[i]

}

}

return answer;

}
```

## 보이는 학생
```js
function solution(arr) {
//최대값을 구하는 첫번째 arr의 수를 넣어주고 첫번째 학생은 무조건 보이기때문에 answer=1로 초기값 세팅
let answer = 1, max = arr[0];
for(let i =1; i<arr.length; i++){
//최대값보다 그 다음 값이 크면 max의 값을 제일 큰 값으로 바꾸어 계산
	if(arr[i] > max){
		max=arr[i]
		answer++;
	}
}
return answer;

}
```

## 점수계산
```js
function solution(arr) {
//cnt 의 값으로 점수를 계산해서 최종값을 answer에 담아준다. 
let answer = 0, cnt = 0;
for (let x of arr) {
if (x === 1) {
	cnt++;
	answer += cnt;
}
else cnt = 0;
}
return answer;

}
```

## 등수 구하기 
### 조건 정리 
- 해당 문제에 조건 정리가 오래걸렸다. 
- 서로의 등수를 비교해야하는데 array.from을 몰랐기 때문.. 
- arr[i]번째와 arr[j]가 비교하면서 만약 arr[i]가 arr[j]보다 작다면 +1을 하여 등수를 낮춘다. 
- `Array.from({length:5},()=>1)`로 초기화하여 [1,1,1,1,1]와 같이 배열값에서부터의 시작을 만드는 것이 관건이라고 생각했다. 
```js

function solution(arr){  
    let n=arr.length;
    let answer=Array.from({length:n}, ()=>1);
                for(let i=0; i<n; i++){
                    for(let j=0; j<n; j++){
                        if(arr[j]>arr[i]) answer[i]++;
                    }
                }             
                return answer;
            }

```