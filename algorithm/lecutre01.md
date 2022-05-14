[Programmers] Hello,Javascript


console.log("pi_int의 값은", pi_int, "입니다." );


## 산술 연산자 
Math.pow(2,3) // 2의 3승 
Math.sqrt(16)  // 스퀘어 루트 

Math.random() // 아무런 인자를 받지 않는 함수는 호출 시  0~1 사이에 다양한 난수를 배정한다. 

## for 문 

초기화 코드를 선언해야하는 ㅇ

var array = [1,2,3,4,5,6,7,8,9,0]
for (var i = 0; i< array.length++; i++){
    // 반복 실행될 코드
    console.log(array[i]);
}

## function 
함수 solution은 인자 a와 b를 입력받습니다. 2번째 줄을 수정해서 solution이 a와 b의 합을 return하도록 만들어 보세요.

```js
function solution(a,b){
     var sum = a+b; // sum 변수에 담아서 
    return sum // sum을 반환한다.
}
```
```js
function solution(a,b){
     var sum = a+b; // sum 변수에 담아서 
    return sum // retrun해준다 
}
```

## 관계연산자
1.Relational 관계 
- true ,false로 반환된다. ->Boolean 자료형  

2.Operator 연산자

## For 

```
var array = [1,2,3,4,5,6,7,8,9];

var i = 0; // 반복문 진입 전 초기 코드 
while(i < array.length){
    console.log(array[i]);
    i++;
}