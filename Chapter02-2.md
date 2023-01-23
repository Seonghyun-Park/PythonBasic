# Chapter02-2
- 파이썬 완전 기초
- 파이썬 변수

## 기본 선언

```python
n = 700 # 변수 앞에 자료형을 쓰지 않아도 된다.
```

## 출력

```python
print(n)
print(type(n)) # 변수의 자료형 출력
print()
```

![image](https://user-images.githubusercontent.com/121333241/210306734-87046171-6236-468b-ad1f-30bab33e07cb.png)

## 동시 선언

```python
x = y = z = 700
print(x, y, z)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210306754-df6a3f21-3923-4e3f-a481-44494845e165.png)

### 📌 선언

```python
var = 75
```

### 📌 재선언

```python
var = 'Change Value'
```

### 📌 출력

```python
print(var)
print(type(var))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210306787-7fb751a4-c0fa-4a7f-bce5-eae294af0c55.png)

## Object Reference
### 변수 값 할당 상태
1. 타입에 맞는 오브젝트 생성 
2. 값 생성
3. 콘솔 출력

### 예 :one:

```python
print(300) # 내부적으로 처리
print(int(300))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210306830-b7687375-1cd2-48db-9d04-6bf327928c62.png)

### 예 2️⃣

```python
# n -> 777
n = 777 
print(n, type(n))
print()

m = n
# m -> 777 <- n
print(m, n)
print(type(m), type(n))
print()

m = 400
print(m, n)
print(type(m), type(n))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210307143-69bd0bd3-9ff5-41bd-96d6-7fc18603ce6c.png)

![image](https://user-images.githubusercontent.com/121333241/210307164-9262ec5d-81a6-471c-ac5e-d1c24402b554.png)

![image](https://user-images.githubusercontent.com/121333241/210307042-52184fb3-b072-4e43-b630-87c73d07b3b5.png)

## id(identity) 확인: 객체의 고유값 확인

```python
m = 800
n = 655
print(id(m))
print(id(n))
print(id(m) == id(n))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210307087-71b1cf0c-9e77-4f3c-b90c-c8ac813a34c7.png)

## 같은 오브젝트 참조

```python
m = 800
n = 800
print(id(m))
print(id(n))
print(id(m) == id(n))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210307110-24b5030f-ee07-4477-8f35-2e54c4ac46b3.png)

## 다양한 변수 선언

- Camel Case(첫 글자가 소문자) : numberOfCollegeGraduates -> Method
- Pascal Case(첫 글자가 대문자) : NumberOfCollegeGraduates -> Class
- Snake Case(단어 사이에 _ 사용, 소문자로만 표현) : number_of_college_graduates

## 허용하는 변수 선언 법

```python
age = 1
Age = 2
aGe = 3
AGE = 4
a_g_e = 5
_age = 6
age_ = 7
_AGE_ = 8
```

## 예약어는 변수명으로 불가능 
- 예약어: 이미 python에서 사용하는 변수들

```python
"""
False	def	if	raise
None	del	import	return
True	elif	in	try
and	else	is	while
as	except	lambda	with
assert	finally	nonlocal	yield
break	for	not	
class	from	or	
continue	global	pass	
"""
```

### :dart: 전체 주석 : Ctrl + /
