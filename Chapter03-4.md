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

![image](https://user-images.githubusercontent.com/121333241/214571908-42fbecd6-95ce-4e18-a5cb-eb82a98ec251.png)

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

![image](https://user-images.githubusercontent.com/121333241/214572061-6a574989-cea6-451f-bad2-d1d05e8abbf7.png)

## 튜플 연산

```python
print('>>>>>>')
print('c + d', c + d)
print('c * 3', c * 3)
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572133-8bea8742-1304-434c-8bae-7c66a682acdb.png)

## 튜플 함수

```python
a = (5, 2, 3, 1, 4)
print('a -', a)
print('a -', a.index(3)) # 숫자 3의 위치가 어딘지 확인
print('a -', a.count(2)) # 숫자 2가 몇 개 있는지 확인
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572207-c032801d-b20a-4dfa-90e6-4c26e6c9124f.png)

## 팩킹 & 언팩킹 (Packing & Unpacking)

### 팩킹 (하나로 묶는다.) (선언과 같은 의미)

```python
t = ('foo', 'bar', 'baz', 'qux') # 4개의 원소를 하나로 묶었다.

print(t)
print(t[0])
print(t[-1])
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572289-2a303356-cbec-47d5-88db-aacef3c9bd41.png)

### 언팩킹 1 (괄호가 벗겨진다.)

```python
(x1, x2, x3, x4) = t # 묶여 있던걸 푼다.
# t로 팩킹되어 있는 것을 풀어서 각각의 원소에 할당한다.

print(type(x1), type(x2), type(x3), type(x4))
print(x1, x2, x3, x4)
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572374-ef73c724-ae6b-43ef-b8a2-ce44f36fb4e3.png)

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

![image](https://user-images.githubusercontent.com/121333241/214572437-87014aca-4062-4956-a111-629a5528119c.png)
