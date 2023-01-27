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

## 튜플 변환 (set -> tuple)

```python
t = tuple(b)
print('t -', type(t), t)
print('t -', t[0],t[1:3])
print()
```

## 리스트 변환(set -> list)

```python
l = list(c)
l2 = list(e)

print('l -', type(l), l)
print('l2 -', type(l2), l2)
```

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

### 합집합

```python
print('s1 | s2 :', s1 | s2)
print('s1 | s2 :', s1.union(s2))
print()
```

### 차집합

```python
print('s1 - s2 :', s1 - s2)
print('s1 - s2 :', s1.difference(s2))
print()
```

### 중복 원소 확인

```python
print('s1 & s2 :', s1.isdisjoint(s2)) # disjoint: 중복되지 않냐?
# 교집합이 있으면 False, 없으면 True
print()
```

### 부분 집합 확인

```python
print('subsuet :', s1.issubset(s2)) # s1이 s2의 부분집합인가?
print('superset :', s1.issuperset(s2)) # s1 집합이 s2를 포함하는가?
print()
```

## 추가 & 제거

```python
s1 = set([1, 2, 3, 4])
```

### 추가

```python
s1.add(5)
print('s1 -', s1)
```

### 제거 1

```python
s1.remove(2)
print('s1 -', s1)
# s1.remove(7) -> 집합에 없는 원소이기 때문에 에러가 발생한다. 
```

### 제거 2

```python
s1.discard(3)
print('s1 -', s1)
# s1.discard(7) -> 집합에 없는 원소이지만 에러가 발생하지 않는다. 
# -> 에러가 발생하지 않아서 원소 하나를 지울 때 remove보다 좋다.
```

### 제거 3

```python
s1.clear() # 전체 원소 삭제
print('s1 -', s1)
```