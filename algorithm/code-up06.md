# [code-up]Python 기초 100제 (6051-6060)(20220505)

## 6051. 정수 2개 입력받아 비교하기4

### ✍🏻 입력: 2개의 정수(a, b)가 공백으로 구분되어 입력된다.

### ✍🏻 출력: a를 b로 나눈 나머지를 출력한다.

```python

a,b = map(int,input().split())

print(a!=b)

```

---

## 6052. 정수 입력받아 참 거짓 평가하기

### ✍🏻 입력: 정수 1개가 입력된다.

### ✍🏻 출력: 입력된 값이 0이면 False, 0이 아니면 True 를 출력한다.

```python

a = int(input())

print(bool(a))

```

---

## 6053. 참 거짓 바꾸기

### ✍🏻 입력: 정수 1개가 입력된다.

### ✍🏻 출력: 입력된 정수의 불 값이 False 이면 True, True 이면 False 를 출력한다.

```python

a = bool(int(input()))

print(not a)

```

---

## 6054. 둘 다 참일 경우만 참 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다.

### ✍🏻 출력: 둘 다 True 일 경우에만 True 를 출력하고, 그 외의 경우에는 False 를 출력한다.

```python
a,b = map(int,input().split())


print(bool(a) and bool(b))

```

---

## 6055. 하나라도 참이면 참 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다.

### ✍🏻 출력: 하나라도 참일 경우 True 를 출력하고, 그 외의 경우에는 False 를 출력한다.

```python
a,b = map(int,input().split())

print(not(bool(a) and bool(b)))

```

---

## 6056. 참/거짓이 서로 다를 때에만 참 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다.

### ✍🏻 출력: 하나라도 참일 경우 True 를 출력하고, 그 외의 경우에는 False 를 출력한다.

```python
a,b = map(int,input().split())

print(bool(a and not b) or bool(not a and b))

```

---

## 6057. 참/거짓이 서로 같을 때에만 참 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다.

### ✍🏻 출력: 두 값의 True / False 값이 서로 같을 경우만 True 를 출력하고, 그 외의 경우에는 False 를 출력한다.

```python
a,b = map(int,input().split())

print(bool(a and b) or bool(not a and not b))

```

---

## 6058. 둘 다 거짓일 경우만 참 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다.

### ✍🏻 출력: 두 값의 True / False 값이 모두 False 일 때만 True 를 출력하고, 그 외의 경우에는 False 를 출력한다.

```python
a,b = map(int,input().split())

print(bool(not a and not b))

```

---

## 6059. 비트단위로 NOT 하여 출력하기

### ✍🏻 입력: 정수 1개가 입력된다. (-2147483648 ~ +2147483647)

### ✍🏻 출력: 비트 단위로 1 -> 0, 0 -> 1로 바꾼 후 그 값을 10진수로 출력한다.

```python
a=int(input())

print(~a)
```

---

## 6060. 비트단위로 AND 하여 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다. (-2147483648 ~ +2147483647)

### ✍🏻 출력: 두 정수를 비트단위(bitwise)로 and 계산을 수행한 결과를 10진수로 출력한다.

```python
a,b=map(int,input().split())

print(a&b)
```

---

## 🔥 정리

### bool()

- `bool()`을 이용하면 입력된 식이나 값을 평가해 불 형의 값(true or false)을 출력해준다.
- **_0 은 Flase_**, **_나머지 값은 True_**
- 불 대수(boolean algebra)는 수학자 불이 만들어낸 것으로 **_True(참)/False(거짓) 값만 가지는 논리값_**과 **_그 값들 사이의 연산_**을 다룬다.

### bool Not

- 또는 거짓의 논리값을 역(반대)으로 바꾸기 위해서 not 예약어(reserved word, keyword)를 사용할 수 있다.

### XOR연산자

```python
print(bool(a and not b) or bool(not a and b))
```

- 위 코드는 아래의 결과 값과 같다.

```
print(xor(0,0))//False
print(xor(0,1))//True
print(xor(1,0))//False
print(xor(1,1))//True
```

### 비트단위 연산자

- 종류 : ~(bitwise not), &(bitwise and), |(bitwise or), ^(bitwise xor),
  <<(bitwise left shift), >>(bitwise right shift)

1. 예를 들어 1을 입력했을 때 저장되는 1을 32비트 2진수로 표현하면 -> 00000000 00000000 00000000 00000001
2. ~1 (not)으로 바꾸면 -> 11111111 11111111 11111111 11111110
3. not(~)으로 바꾼 2진수를 10진수로 바꾸면 -> -2

- 비트단위연산자로 not(~)을 표현하는 방법은 다음과 같다.

````python
a = int(input())
print(~a)```
````
