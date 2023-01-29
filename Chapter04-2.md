# Chapter04-2
- 파이썬 반복문
- for 실습
-  코딩의 핵심
```python
# for in <collection>
#    <Loop body>
```

## 출력

```python
for v1 in range(10): # 0 ~ 9
    print('v1 is :', v1) # v1은 for문에서 사용할 변수
    
print()

for v2 in range(1, 11): # 1 ~ 11
    print('v2 is :', v2)
    
print()

for v3 in range(1, 11, 2): # 1부터 10까지 2칸씩 건너뛰어 출력
    print('v3 is :', v3)
    
print()
```

## 1 ~ 1000 합

```python
sum1 = 0

for v in range(1, 1001):
    sum1 += v
print('1 ~ 1000 Sum :', sum1)

print('1 ~ 1000 Sum :', sum(range(1, 1001)))
print('1 ~ 1000 4의 배수의 합 :', sum(range(4, 1001, 4)))
print()
```

## Iterables 자료형 반복
- 문자열, 리스트, 튜플, 집합, 사전(딕셔너리)
- iterable 리턴 함수 : range, reverse, enumerate, filter, map, zip

## 예제 1 - 리스트

```python
names = ['Kim', 'Park', 'Cho', 'Lee', 'Choi', 'Yoo']

for n in names:
    print('You are :', n) # n은 for문에서 사용할 변수
print()
```
    
## 예제 2 - 리스트

```python
lotto_numbers = [11, 19, 21, 28, 36, 37]

for n in lotto_numbers:
    print("Current number :", n)
print()
```

## 예제 3 - 문자열  

```python
word = 'Beautiful'

for s in word:
    print('word :', s)
print()
```

## 예제 4 - 딕셔너리

```python
my_info = {
    "Name": "Lee",
    "Age": 33,
    "City": "Seoul"
}

for key in my_info:
    print('key :', key)

for v in my_info.values():
    print('values :', v)
print()
```

## 예제 5 - 반복문과 조건문

```python
name = 'FineAppLE'

for n in name:
    if n.isupper(): # 대문자라면
        print(n, end='') # 그대로 출력
    else: # 소문자라면
        print(n.upper(), end='') # 대문자로 출력
print()
```

## 예제 6 - break
- 즉시 for문을 탈출한다.

```python
numbers = [14, 3, 4, 7, 10, 24, 17, 2, 33, 15, 34, 36, 38]

for num in numbers:
    if num == 34:
        print('Found : 34!')
        break # break를 만나면 즉시 for문을 탈출한다.
    else:
        print('Not found :', num)
print()
```

## 예제 7 - continue
- 다시 조건을 검사하는 부분으로 이동한다.

```python
lt = ["1", 2, 5, True, 4.3, complex(4)]

for v in lt:
    if type(v) is bool: # 만약 자료형이 bool이라면
        continue # 생략하고 다음 조건을 실행한다.
    print('current type:', v, type(v))
print()
```

## for - else
- for문을 다 실행하였는데 결과가 없을 때 마지막에 else 사용

```python
numbers = [14, 3, 4, 7, 10, 24, 17, 2, 33, 15, 34, 36, 38]

for num in numbers:
    if num == 24:
        print("Found : 24")
        break
else:
    print('Not Found : 24')
print()
```

## 구구단 출력

```python    
for i in range(2, 10):
    for j in range(1, 10):
        print('{:4d}'.format(i * j), end= ' ')
    print()
print()    
```


## 변환 예제

```python
name2 = 'Aceman'

print('Reversed', reversed(name2))
print('List', list(reversed(name2)))
print('Tuple', tuple(reversed(name2)))
print('Set', set(reversed(name2))) # 집합에는 순서가 없다. 
```