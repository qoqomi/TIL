# [code-up]Python 기초 100제 (6011-6020)(20220429)

## 6011. 변수에 실수값을 저장한 후 변수에 저장되어 있는 값을 그대로 출력해보자.

```python
x = float(input())
print(x)

```

---

## 6012. 변수에 정수값을 2개를 출력하자.

```python
x = int(input())
y= int(input())
print(x)
print(y)
```

---

## 6013. 2개의 문자가 줄을 바꿔 입력된다. 출력은 순서를 바꿔 한줄에 한 문자(character)씩 출력한다.

```python
x = str(input())
y= str(input())

print(y)
print(x)
```

---

## 6014. 실수 1개를 입력받아 줄을 바꿔 3번 출력한다.

```python
x=input()
print(x)
print(x)
print(x)
```

---

## 6015. 공백을 두고 입력된정수(integer) 2개를 입력받아 줄을 바꿔 출력해보자.

```python
a,b = input().split()
print(a)
print(b)
```

---

## 6016. 공백을 두고 문자(character) 2개를 입력받아 순서를 바꿔 출력해보자.

```python
a,b = map(str,input().split())
print(b,a)
```

---

## 6017. 정수(integer), 실수, 문자(character), 문자열(string) 등 1개만 입력받아 한 줄로 3번 출력해보자.

```python
a= input()
print(a,a,a)
```

---

## 6018. 24시간 시:분 형식으로 시간이 입력될 때, 그대로 출력하는 연습을 해보자.

```python
a,b= input().split(':')
print(a,b,sep=':')
```

---

## 6019. "연도.월.일"을 입력받아 "일-월-연도" 순서로 바꿔 출력해보자.

```python
a,b,c= input().split('.')
print(c,b,a,sep='-')
```

---

## 6020. 주민번호는 다음과 같이 구성된다.<br>XXXXXX-XXXXXXX

- 왼쪽 6자리는 생년월일(YYMMDD)이고, 오른쪽 7자리는 성별,출생지역,확인코드로 구성되어있다.
  주민번호를 입력받아 형태를 바꿔 출력해보자.

```python
a,b= input().split('-')
print(a,b,sep='')
```

---

## 🔥 정리

### 🖇 변수

- 정수(integer) : float
- 실수 : int
- 문자(character) : str / 문자열에는 공백문자가 포함될 수 있다.

### 🖇 split()

- python의 `input()`은 한줄 단위로 입력받는다. <br> `input().split()`을 사용하면, 공백을 기준으로 입력된 값들을 나누어 자른다.
- `a,b = 1,2` 를 실행하면 a에는 1 ,b에는 2가 들어간다.

### 🖇 map 함수

1. 구조

```python
map=(변환 함수, 순회 가능한 데이터)
```

2. 예를들어
   `a,b = map(str,input().split())`
   라면 입력받는 인수가 float=실수형태로 들어와도 str=문자 형태로 출력된다.

### 🖇 split() vs sep()

1. split()

- split은 구분자를 기준으로 문자열을 잘라 배열로 입력할 때 사용하는 메서드

- 입력하는 인수의 값을 받는다. 출력값에 영향을 미치지 않는다. <br>예를 들어

  ```Python
    a,b= input().split('$')
    print(a,b)
  ```

  - 입력 : **23$23** 을 입력해야 출력 결과를 볼 수 있다.
  - 출력 : **23 23**

2. sep()

- 출력에 영향을 미친다.
- seperator는 구분가능한 요소로 분리해준다는 의미가 있다.

```
//,sep='표시를 원하는 문자'
a,b= input().split(',')
print(a,b,sep=':')
```

- 입력 : **23,23** 을 입력해야 출력 결과를 볼 수 있다.
- 출력 : **23:23**
