# Chapter03-6
- 집합(Set) 특징
- 집합(Set) 자료형(순서 X, 중복 X)

## 선언

```python
a = set()
b = set([1, 2, 3, 4, 4, 4]) # 중복된 데이터는 표시하지 않는다.
c = set([1, 4, 5, 6])
d = set([1, 2, 'Pen', 'Cap', 'Plate'])
e = {'foo', 'bar', 'baz', 'foo', 'qux'} # 키 없이 원소만 나열한다면 { }도 집합이다.
f = {42, 'foo', (1, 2, 3), 3.14159}
```
```python
print('a -', type(a), a)
print('b -', type(b), b)
print('c -', type(c), c)
print('d -', type(d), d)
print('e -', type(e), e)
print('f -', type(f), f)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215102911-667c244e-de9a-4e73-a9d8-d999c6f26515.png)

## 튜플 변환 (set -> tuple)

```python
t = tuple(b)
print('t -', type(t), t)
print('t -', t[0],t[1:3])
print()
```

![image](https://user-images.githubusercontent.com/121333241/215102964-d19cdadd-e4c0-4bc8-b91a-89c3bc7048a0.png)

## 리스트 변환(set -> list)

```python
l = list(c)
l2 = list(e)

print('l -', type(l), l)
print('l2 -', type(l2), l2)
```

![image](https://user-images.githubusercontent.com/121333241/215103025-ed6296f6-7c5d-4813-896e-4ce821dfdfe6.png)

## 길이

```python
print(len(a))
print(len(b))
print(len(c))
print(len(d))
print(len(e))
print(len(f))
print()
```

![image](https://user-images.githubusercontent.com/121333241/215103068-87e0dff0-922d-4564-ad1a-609f97ff6218.png)

## 집합 자료형 활용

```python
s1 = set([1, 2, 3, 4, 5, 6])
s2 = set([4, 5, 6, 7, 8, 9])
```

### 교집합

```python
print('s1 & s2 :', s1 & s2)
print('s1 & s2 :', s1.intersection(s2)) # intersection: 교차
print()
```

![image](https://user-images.githubusercontent.com/121333241/215103199-39cd6257-8940-4e86-a10f-4fbc4f324003.png)

### 합집합

```python
print('s1 | s2 :', s1 | s2)
print('s1 | s2 :', s1.union(s2))
print()
```

![image](https://user-images.githubusercontent.com/121333241/215103260-177aaba3-5b16-4c7f-aa17-9d354e82dfe7.png)

### 차집합

```python
print('s1 - s2 :', s1 - s2)
print('s1 - s2 :', s1.difference(s2))
print()
```

![image](https://user-images.githubusercontent.com/121333241/215103309-597f8bb5-a076-4568-aa7c-4a6354e07ab4.png)

### 중복 원소 확인

```python
print('s1 & s2 :', s1.isdisjoint(s2)) # disjoint: 중복되지 않냐?
# 교집합이 있으면 False, 없으면 True
print()
```

![image](https://user-images.githubusercontent.com/121333241/215103362-3e828934-e282-4adc-9fda-64746be9dd88.png)

### 부분 집합 확인

```python
print('subsuet :', s1.issubset(s2)) # s1이 s2의 부분집합인가?
print('superset :', s1.issuperset(s2)) # s1 집합이 s2를 포함하는가?
print()
```

![image](https://user-images.githubusercontent.com/121333241/215103392-71bc7b6a-2a9a-4315-978a-25ade7bdf234.png)

## 추가 & 제거

```python
s1 = set([1, 2, 3, 4])
```

### 추가

```python
s1.add(5)
print('s1 -', s1)
```

![image](https://user-images.githubusercontent.com/121333241/215103469-e47b4095-f742-49ec-b14b-b28bf0602aa8.png)

### 제거 1

```python
s1.remove(2)
print('s1 -', s1)
# s1.remove(7) -> 집합에 없는 원소이기 때문에 에러가 발생한다. 
```

![image](https://user-images.githubusercontent.com/121333241/215103512-d9a7bf59-ca4c-4f7e-8542-0979e213b7ca.png)

### 제거 2

```python
s1.discard(3)
print('s1 -', s1)
# s1.discard(7) -> 집합에 없는 원소이지만 에러가 발생하지 않는다. 
# -> 에러가 발생하지 않아서 원소 하나를 지울 때 remove보다 좋다.
```

![image](https://user-images.githubusercontent.com/121333241/215103559-dd0b1ee0-38b6-4d26-8dc5-01ec262b13cd.png)

### 제거 3

```python
s1.clear() # 전체 원소 삭제
print('s1 -', s1)
```

![image](https://user-images.githubusercontent.com/121333241/215103640-8bd8b548-e375-404a-9d3b-974329298ca3.png)
