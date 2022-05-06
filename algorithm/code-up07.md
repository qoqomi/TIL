# [code-up]Python 기초 100제 (6061-6070)(20220506)

## 6061. 비트단위로 OR 하여 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다. (-2147483648 ~ +2147483647)

### ✍🏻 출력: 두 정수를 비트단위(bitwise)로 or 계산을 수행한 결과를 10진수로 출력한다.

```python
a,b=map(int,input().split())

print(a|b)
```

---

## 6062. 비트단위로 XOR 하여 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다. (-2147483648 ~ +2147483647)

### ✍🏻 출력: 두 정수를 비트단위(bitwise)로 xor 계산을 수행한 결과를 10진수로 출력한다.

```python
a,b=map(int,input().split())

print(a^b)
```

---

## 6063. 정수 2개 입력받아 큰 값 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다. (-2147483648 ~ +2147483647)

### ✍🏻 출력: 두 정수 중 큰 값을 10진수로 출력한다.

```python
a,b=map(int,input().split())

c = a if (a>=b) else b
print(c)
```

---

## 6064. 정수 3개 입력받아 가장 작은 값 출력하기

### ✍🏻 입력: 2개의 정수가 공백을 두고 입력된다. (-2147483648 ~ +2147483647)

### ✍🏻 출력: 가장 작은 값을 출력한다.

```python
a,b,c=map(int,input().split())

d = (a if (a < b) else b) if ((a if (a < b) else b) < c) else c
print(d)
```

---

## 6065. 정수 3개 입력받아 짝수만 출력하기

### ✍🏻 입력: 3개의 정수(a, b, c)가 공백을 두고 입력된다. (0 ~ +2147483647 범위의 정수들이 입력되며 적어도 1개는 짝수이다.)

### ✍🏻 출력: 짝수만 순서대로 줄을 바꿔 출력한다.

```python
a,b,c=map(int,input().split())

if a % 2==0 :
    print(a)
if b % 2 == 0:
    print(b)
if c % 2 == 0:
    print(c)
```

---

## 6066. 정수 3개 입력받아 짝/홀 출력하기

### ✍🏻 입력: 3개의 정수(a, b, c)가 공백을 두고 입력된다. (0 <= a,b,c <= 2147483647)

### ✍🏻 출력: 입력된 순서대로 짝(even)/홀(odd)을 줄을 바꿔 출력한다.

```python
a,b,c=map(int,input().split())

if a % 2==0 :
    print("even")
else:
    print("odd")

if b % 2==0 :
    print("even")
else:
    print("odd")

if c % 2==0 :
    print("even")
else :
    print("odd")
```

---

## 6067. 정수 1개 입력받아 분류하기

### ✍🏻 입력: 정수 1개가 입력된다. (-2147483648 ~ +2147483647, 단 0은 입력되지 않는다.)

### ✍🏻 출력: 음수이면서 짝수이면, A / 음수이면서 홀수이면, B /양수이면서 짝수이면, C /양수이면서 홀수이면, D를 출력한다.

```python
a = int(input())

if (a < 0) & (a % 2 == 0) :
    print("A")
elif (a < 0) & (a % 2 == 1):
    print("B")
elif (a > 0) & (a % 2 == 0):
    print("C")
else:
    print("D")
```

---

## 6068. 정수(0 ~ 100) 1개가 입력된다.

### ✍🏻 입력: 정수 1개가 입력된다. (-2147483648 ~ +2147483647, 단 0은 입력되지 않는다.)

### ✍🏻 출력: 평가 결과를 출력한다.

```python
a = int(input())

if (a >= 90) :
    print("A")
elif (a >= 70) :
    print("B")
elif (a >= 40):
    print("C")
else:
    print("D")
```

---

## 6069. 평가 입력받아 다르게 출력하기

### ✍🏻 입력: 영문자 1개가 입력된다. (A, B, C, D 등 문자 1개가 입력된다.)

### ✍🏻 출력: 문자에 따라 다른 내용이 출력된다.

```python
a = str(input())

if (a =="A") :
    print("best!!!")
elif (a == "B") :
    print("good!!")
elif (a == "C"):
    print("run!")
elif (a == "D"):
    print("slowly~")
else:
    print("what?")

```

---

## 6070. 월 입력받아 계절 출력하기

### ✍🏻 입력: 월을 의미하는 1개의 정수가 입력된다.(1 ~ 12)

### ✍🏻 출력: 계절 이름을 출력한다.

```python
a = int(input())

if a//3==1 :
    print("spring")
elif a//3 ==2:
    print("summer")
elif a//3 ==3:
    print("fall")
else:
    print("winter")

```

## 🔥 정리

### 3항 연산자

`True일때 사용할 값 if if조건 else false일때 사용할 값`
