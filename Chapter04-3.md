# Chapter04-3
- 파이썬 반복문 
- while 실습

```python
# while <expr>:
#   <statement(s)>
```

## 예제 1

```python
n = 5
while n > 0: # n > 0 조건이 만족할 때까지 반복 
    print(n)
    n = n-1
print()
```
    
## 예제 2

```python
a = ['foo', 'bar', 'baz']

while a:
    print(a.pop())
```    

## 예제 3
- if 중첩, break, continue

```python
n = 5
while n > 0:
    n -= 1
    if n == 2:
        break
    print(n)
print('Loop Ended.')
print()
```

## 예제 4

```python
m = 5
while m > 0:
    m -= 1
    if m == 2:
        continue
    print(m)
print('Loop Ended.')
print()
```

## 예제 5

```python
i = 1

while i <= 10:
    print('i:', i)
    if i == 6:
        break
    i += 1
print()
```

## 예제 6
- while - else 구문

```python
n = 10
while n > 0:
    n -= 1
    print(n)
    if n == 5:
        break
else:
    print('else out')
print()
```

## 예제 7

```python
a = ['foo', 'bar', 'baz', 'qux']
s = 'kim'

i = 0
while i < len(a):
    if a[i] == s:
        break
    i += 1
else:
    print(s, 'not found in list.')
print()
```

## 예제 8

```python
a = ['foo', 'bar', 'baz']

while True: # True일 때이기 때문에 무한 실행
    if not a: # 만약 a가 아니라면 
        break # break
    print(a.pop())
```

## 무한 반복 조심
```python
# while True:
#     print('Foo')
```