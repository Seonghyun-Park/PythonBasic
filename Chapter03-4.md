# Chapter03-4

- 파이썬 튜플
- 리스트와 비교 중요
- 튜플 자료형(순서 O, 중복 O, 수정 X, 삭제 X) # 불변

## 선언 ( )

```python
a = () # 튜플 선언
b = (1,) # 원소가 하나일 때는 ,로 끝나야 한다.
c = (11, 12, 13, 14) # 두개 이상부터는 ,로 끝나지 않아도 된다.
d = (100, 1000, 'Ace', 'Base', 'Captain')
e = (100, 1000, ('Ace', 'Base', 'Captain')) # 튜플 안에 튜플 선언
```

## 인덱싱

```python
print('>>>>>>')
print('d -', d[1])
print('d -', d[0] + d[1] + d[1])
print('d -', d[-1])
print('e -', e[-1])
print('e -', e[-1][1])
print('e -', list(e[-1][1])) # list로 형 변환
print()
```

## 수정 X
- d[0] = 1500 -> 에러 발생

## 슬라이싱

```python
print('>>>>>>')
print('d -', d[0:3])
print('d -', d[2:])
print('e -', e[2][1:3])
print()
```

## 튜플 연산

```python
print('>>>>>>')
print('c + d', c + d)
print('c * 3', c * 3)
print()
```

## 튜플 함수

```python
a = (5, 2, 3, 1, 4)
print('a -', a)
print('a -', a.index(3)) # 숫자 3의 위치가 어딘지 확인
print('a -', a.count(2)) # 숫자 2가 몇 개 있는지 확인
print()
```

## 팩킹 & 언팩킹 (Packing & Unpacking)

### 팩킹 (하나로 묶는다.) (선언과 같은 의미)

```python
t = ('foo', 'bar', 'baz', 'qux') # 4개의 원소를 하나로 묶었다.

print(t)
print(t[0])
print(t[-1])
print()
```

### 언팩킹 1 (괄호가 벗겨진다.)

```python
(x1, x2, x3, x4) = t # 묶여 있던걸 푼다.
# t로 팩킹되어 있는 것을 풀어서 각각의 원소에 할당한다.

print(type(x1), type(x2), type(x3), type(x4))
print(x1, x2, x3, x4)
print()
```

## 팩킹 & 언팩킹

```python
t2 = 1, 2, 3 # 튜플을 선언할 때 괄호를 생략할 수 있다.
t3 = 4, # 팩킹
x1, x2, x3 = t2 # 언팩킹
x4, x5, x6 = 4, 5, 6 # 언팩킹(4, 5, 6을 x4, x5, x6에 각각 할당)

print(t2)
print(t3)
print(x1, x2, x3)
print(x4, x5, x6)
```