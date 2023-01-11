# Chapter03-3
- 파이썬 리스트
- 자료구조에서 중요
- 리스트 자료형 (순서 O, 중복 O, 수정 O, 삭제 O)

## 선언

```python
a = []
b = list()
c = [70, 75, 80, 85] # Len
d = [1000, 10000, 'Ace', 'Base', 'Captine']
e = [1000, 10000, ['Ace', 'Base', 'Captine']]
f = [21.42, 'footbar', 3, 4, False, 3.14159]
```

## 인덱싱 (내가 원하는 데이터를 꺼내오는 과정)

```python
print('>>>>>>')
print('d - ', type(d), d)
print('d - ', d[1])
print('d - ', d[0] + d[1] + d[1])
print('d - ', d[-1]) # - 부호는 오른쪽에서부터
print('e - ', e[-1][1]) # e의 -1번 인덱스는 리스트 -> 리스트의 1번 인덱스는 Base
print('e - ', list(e[-1][1]))
print()
```

## 슬라이싱

```python
print('>>>>>>')
print('d - ', d[0:3]) # 0부터 2(3-1)까지
print('d - ', d[2:]) # 2부터 끝까지
print('e - ', e[-1][1:3])
print()
```

## 리스트 연산

```python
print('>>>>>>')
print('c + d - ', c + d) # 리스트 + 리스트 = 리스트
print('c * 3 - ', c * 3) # 3번 반복
print("Test + c[0] - ", 'Test' + str(c[0]))
print()
```

## 값 비교

```python
print(c == c[:3] + c[3:])
print(c)
print(c[:3] + c[3:])
print()
```

# Identity(id)
- 파이썬의 효율성때문에 리스트 역시도 하나의 주소값을 공유한다.

```python
temp = c
print(temp, c)
print(id(temp))
print(id(c))
print()
```

## 리스트 수정, 삭제

```python
print('>>>>>>')
c[0] = 4 # 인덱스 번호로 접근해서 수정
print('c - ', c)
c[1:2] = ['a', 'b', 'c'] # [['a', 'b', 'c']]
print('c - ', c)
c[1] = ['a', 'b', 'c'] # 범위가 아니라 번호로 접근하면 리스트 형태로 들어간다.
print('c - ', c)
c[1:3] = [] # 1부터 2번 원소를 삭제
print('c - ', c)

del c[2] # 삭제
print('c - ', c)
print()
```

## 리스트 함수

```python
print('>>>>>>')
a = [5, 2, 3, 1, 4]
print('a - ', a)
```
### append( )
- 끝 부분에 데이터를 삽입할 때 쓰는 함수
```python
a.append(10) # 끝 부분에 데이터를 삽입할 때 쓰는 함수
print('a - ', a)
```

### sort( ) 
-  오름차순으로 정렬하는 함수
```python
a.sort() # 오름차순으로 정렬
print('a - ', a)
```
### reverse( )
- 역순으로 출력하는 함수
```python
a.reverse() # 역순으로 출력
print('a - ', a)
```

### index( )
- 해당 인덱스의 값을 가져오는 함수
```python
print('a - ', a.index(3), a[3]) # 인덱스를 가져오는 함수
```

### insert( )
- 원하는 위치에 삽입하는 함수
- insert(a, b) : a번째 위치에 b를 추가한다.
```python
a.insert(2,7) # 2번째 위치에 7추가 (원래 값들은 뒤로 밀린다.)
print('a - ', a)
a.reverse() # 역순으로 출력
print('a - ', a)
```

### remove( )
- 원하는 원소를 삭제하는 함수
```python
a.remove(10) # 원하는 원소 삭제
print('a - ', a)
# del a[6]
```

### pop( )
- 마지막에 있는 원소를 빼내는 함수
```python
print('a - ', a.pop()) # 마지막에 있는 원소를 가져온다.
print('a - ', a) # 마지막 원소는 꺼내진 채 나머지 원소들로 리스트를 다시 구성
print('a - ', a.pop()) 
print('a - ', a) 
```

### count( )
- 찾고자 하는 값이 몇 개 있는지 확인하는 함수
```python
print('a - ', a.count(4)) # 찾고자 하는 값이 몇개가 중복되어 있는지 확인 
```

### extend( )
- 확장하는 함수
```python
ex = [8, 9]
a.extend(ex)
print('a - ', a)
```

## 삭제
- remove, pop, del


## 반복문 활용
```python
while a:
    data = a.pop()
    print(data)
```