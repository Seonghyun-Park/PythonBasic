# Chapter02-2
### 파이썬 완전 기초
# 파이썬 변수

# 기본 선언

```python
n = 700 # 변수 앞에 자료형을 쓰지 않아도 된다.
```

# 출력

```python
print(n)
print(type(n)) # 변수의 자료형 출력
print()
```

# 동시 선언

```python
x = y = z = 700
print(x, y, z)
print()
```

# 선언

```python
var = 75
```

# 재선언

```python
var = 'Change Value'
```

# 출력

```python
print(var)
print(type(var))
print()
```

# Object Reference
## 변수 값 할당 상태
1. 타입에 맞는 오브젝트 생성 
2. 값 생성
3. 콘솔 출력

## 예1)

```python
print(300) # 내부적으로 처리
print(int(300))
print()
```

# 예2)

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

# id(identity) 확인: 객체의 고유값 확인

```python
m = 800
n = 655
print(id(m))
print(id(n))
print(id(m) == id(n))
print()
```

# 같은 오브젝트 참조

```python
m = 800
n = 800
print(id(m))
print(id(n))
print(id(m) == id(n))
print()
```

# 다양한 변수 선언
### Camel Case(첫 글자가 소문자) : numberOfCollegeGraduates -> Method
### Pascal Case(첫 글자가 대문자) : NumberOfCollegeGraduates -> Class
### Snake Case(단어 사이에 _ 사용, 소문자로만 표현) : number_of_college_graduates

# 허용하는 변수 선언 법

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

# 예약어는 변수명으로 불가능 (예약어는 이미 python에서 사용하는 변수들)

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

# 전체 주석 : Ctrl + /