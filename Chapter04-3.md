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

![image](https://user-images.githubusercontent.com/121333241/215326391-d6a18092-00ba-4ee9-94ad-66611e35430f.png)

## 예제 2

```python
a = ['foo', 'bar', 'baz']

while a:
    print(a.pop())
```    

![image](https://user-images.githubusercontent.com/121333241/215326423-69304629-2c74-4fcf-b02a-f117f3cfba89.png)

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

![image](https://user-images.githubusercontent.com/121333241/215326435-3cf853f6-aa95-478c-90b0-9ad373c685ee.png)

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

![image](https://user-images.githubusercontent.com/121333241/215326446-1ecf99d2-9c40-4e20-82e7-75e5a4089a53.png)

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

![image](https://user-images.githubusercontent.com/121333241/215326475-b2b14c0c-f412-4ab7-994b-82a8c5263faa.png)

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

![image](https://user-images.githubusercontent.com/121333241/215326492-9aecf5fb-32d9-4929-af1e-9c5eda9cdd49.png)

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

![image](https://user-images.githubusercontent.com/121333241/215326504-f8e96cee-cda3-4a5a-be4b-fcd0f45b5e5f.png)

## 예제 8

```python
a = ['foo', 'bar', 'baz']

while True: # True일 때이기 때문에 무한 실행
    if not a: # 만약 a가 아니라면 
        break # break
    print(a.pop())
```

![image](https://user-images.githubusercontent.com/121333241/215326512-1b7736c1-f651-4b5c-9503-ef254d9c56d3.png)

## 무한 반복 조심

```python
# while True:
#     print('Foo')
```
