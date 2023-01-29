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

![image](https://user-images.githubusercontent.com/121333241/215310496-0fefe0e1-f863-41da-ad0f-bfb08f060d65.png) ![image](https://user-images.githubusercontent.com/121333241/215310513-82ab21ee-3396-4bd7-8968-a35189a68aad.png) ![image](https://user-images.githubusercontent.com/121333241/215310528-dd66af4d-d56a-4f66-9b78-5e02903855fe.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310572-142807b0-e643-4278-a296-8c9b046002d2.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310583-6ebda35f-57bf-4f15-aa04-eee85ea1eb73.png)

## 예제 2 - 리스트

```python
lotto_numbers = [11, 19, 21, 28, 36, 37]

for n in lotto_numbers:
    print("Current number :", n)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215310592-f9758402-7a75-472c-a662-d8861bfc7e4b.png)

## 예제 3 - 문자열  

```python
word = 'Beautiful'

for s in word:
    print('word :', s)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215310602-0b2fd87b-5a3d-48b4-bda4-5dc553072a9f.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310618-8c4174d6-da5b-4e04-9758-969593a0d4cb.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310658-4bbd51e5-2a82-4c71-9c46-bbedc8871046.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310678-67e3c3b5-9fb0-477f-85ee-f0bc209cde8c.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310691-2c4b5561-ca39-419e-bcb8-78c0ef6356f6.png)

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

![image](https://user-images.githubusercontent.com/121333241/215310720-fc8682a1-7ba5-4735-a250-aefcc1765776.png)

## 구구단 출력

```python    
for i in range(2, 10):
    for j in range(1, 10):
        print('{:4d}'.format(i * j), end= ' ')
    print()
print()    
```

![image](https://user-images.githubusercontent.com/121333241/215310730-1565b803-165a-4b98-8311-05eb42221f81.png)

## 변환 예제

```python
name2 = 'Aceman'

print('Reversed', reversed(name2))
print('List', list(reversed(name2)))
print('Tuple', tuple(reversed(name2)))
print('Set', set(reversed(name2))) # 집합에는 순서가 없다. 
```

![image](https://user-images.githubusercontent.com/121333241/215310741-eee783ec-17c7-4753-a7ee-b151a065ac7f.png)
