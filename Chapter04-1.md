# Chapter04-1
- 파이썬 제어문
- if 실습

## 기본 형식

```python
print(type(True)) # 0이 아닌 수, "abc", [1,2,3...], (1,2,3...), {1,2,3...} ... 
# -> 값이 존재한다.
print(type(False)) # 0, "", [], (), {} ...
# -> 값이 존재하지 않는다. 비어있다.
```

## 예 1

```python
if True: 
    print('Good') # 파이썬에서는 indent(들여쓰기)를 하지 않으면 에러 발생
    
if False: # False는 실행되지 않는다.
    print('Bad')
```

## 예 2

```python
if False:
    print('Bad')
else:
    print('Good!')    

print()    
```    

## 관계 연산자
- ,>, >=, <, <=, ==, !=

```python
x = 15
y = 10
```

### 양변이 같을 때 True

```python
print(x == y)
```

### 양변이 다를 때 True

```python
print(x != y)
```

# 왼쪽이 클 때 True

```python
print(x > y)
```

### 왼쪽이 크거나 같을 때 True

```python
print(x >= y)
```

### 오른쪽이 클 때 True

```python
print(x < y)
```

### 오른쪽이 크거나 같을 때 True

```python
print(x <= y)

print()
```

## 예 3

```python
city = ""
if city:
    print("You are in:", city)
else:
    print("plz enter your city")
    
city2 = "seoul"
if city2:
    print("You are in:", city2)
else:
    print("plz enter your city") 
    
print()
```
    
## 논리 연산자 (중요)
- and, or, not

```python
a = 75
b = 40
c = 10

print('and:', a > b and b > c) # a > b > c
print('or:', a > b or b > c) 
print('not:', not a > b) 
print('not:', not b > c)
print(not True)
print(not False) # 반대로 출력
print()
```

## 산술, 관계, 논리 우선순위
- 산술 > 관계 > 논리

```python
print('e1 :', 3 + 12 > 7 + 3)
print('e2 :', 5 + 10 * 3 > 7 + 3 * 20)
print('e3 :', 5 + 10 > 3 and 7 + 3 == 10)
print('e4 :', 5 + 10 > 0 and not 7 + 3 == 10)
print()
```

## 예 4

```python
score1 = 90
score2 = 'A'

# 복수의 조건이 모두 참일 경우에 실행
if score1 >= 90 and score2 == 'A':
    print('Pass')
else:
    print('Fail')
    
print()
```

## 예 5

```python
id1 = 'vip'
id2 = 'admin'
grade = 'platinum'

if id1 == 'vip' or id2 == 'admin':
    print('관리자 입장') 
    
if id2 == 'admin' and grade == 'platinum':
    print('최상위 관리자')
    
print()
```

## 예 6
### 다중 조건문

```python
num = 90

if num >= 90:
    print('Grade : A')
elif num >= 80:  # else if를 파이썬에서는 elif 로 사용
    print('Grade : B')
elif num >= 70:
    print('Grade : C')
else:
    print('과락')
    
print()
```
    
## 예 7 
### 중첩 조건문

```python
grade = 'A'
total = 88

if grade == 'A':
    if total >= 90:
        print('장학금 100%')
    elif total >= 80:
        print('장학금 80%')
    else:
        print('장학금 50%')
else:
    print('장학금 없음')
    
print()    
```

## 예 8
### in, not in

```python
q = [10, 20, 30] # 리스트
w = {70, 80, 90, 10} # 집합
e = {"name": "Lee", "city": "Seoul", "grade" : "A"} # 딕셔너리
r = (10, 12, 14) # 튜플

print(15 in q)
print(90 in w)
print(12 not in r)
print("name" in e)
print("Seoul" in e.values()) # "Seoul"은 딕셔너리의 값이기 때문에 values()함수를 사용하여야 한다.
```