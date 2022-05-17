## 항해의 여정(8) (220515)

자세한 내용은 [벨로그:항해일지 시리즈 참고](https://velog.io/@energyy044/series)

### ⚡️ cs 스터디 시작

- 8명이서 cs 스터디 시작했다.

---

### ✏️ 알고리즘

1. var, let 변수

2. 배열 input 함수의 견해

배열 Input함수를 이해할 수가 없어서 . .

```jsx
function solution(s) {
    var answer = s.split(" "); -> 배열을 만들어주기위해서 answer에 저장
    var word = [];

    for(let i = 0; i< answer.length; i++){
        var sum = []; // 여기서 sum을 i만큼 돌려준다 -> sum=[],[],[]
        for(let j = 0; j<answer[i].length; j++){
					// answer[i]번째의 길이만큼 j를 돌려준다. 하단 그림 참조
            if(j % 2 === 0){
                sum.push(answer[i][j].toUpperCase()) // sum에 Push하겠다.answer[i][j]
            }else{
                sum.push(answer[i][j].toLowerCase())
            }

        }
        word.push(sum.join('')) - 1 결과값
    }

    return word.join(' '); - 2 결과값
}

```

3. 숫자를 split으로 배열만들기

4.# **1. 숫자를 문자로 변환 후 배열로 만들기 ( split이용 )**

타입이 숫자(number)인 경우 split을 사용할 수 없기 때문에

**숫자에 ''을 더해 문자로 만들어주고**,

**split('')을 사용하여 배열로 만들어 주는** 방법이다

```jsx
var answer = (n + "").split();
```

### 💭 안지현 기술매니저님과 멘토링

1. 항해 안에서 어떤 사람이 될 것인가 ?
2. css 안해놓으면 걸림돌 ! 잡고가라
3. 실전이 가장 중요 , 실전을 하기 위해서 지금 달리고 있는 것
4. css 코드를 작성하여 당근정원 키우기 : [GRID GARDEN](https://cssgridgarden.com/#ko)
5. Flexbox game : [GRID GARDEN](https://cssgridgarden.com/#ko)
6. [엘리언니 js 배열](https://www.youtube.com/watch?v=3CUjtKJ7PJg&list=PLv2d7VI9OotTVOL4QmPfvJWPJvkmv6h-2&index=11) : 배열 메소드를 많이 사용한다고 하니 꼭 보고 가도록 추천해주심

- [https://www.youtube.com/watch?v=3CUjtKJ7PJg&list=PLv2d7VI9OotTVOL4QmPfvJWPJvkmv6h-2&index=10](https://www.youtube.com/watch?v=3CUjtKJ7PJg&list=PLv2d7VI9OotTVOL4QmPfvJWPJvkmv6h-2&index=10)

### 오늘 한 것

1. 알고리즘 25번까지 풀고 정리

### 내일 목표

1. 알고리즘 32번까지 풀기
2. 노션에 업데이트 한 거 벨로그 + 깃헙에 공유
3. 내일은 알고리즘 시험

### 노션 다시보기
