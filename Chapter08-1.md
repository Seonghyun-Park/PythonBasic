# Chapter08-1
- 파이썬 내장(Built-in) 함수
- 자주 사용하는 함수 위주 실습
- 사용하다보면 자연스럽게 숙달
- str(), int(), tuple() 형변환 이미 학습

## abs( )
- 절댓값

```python
print(abs(-3))
```

![image](https://user-images.githubusercontent.com/121333241/217177122-4d74a884-d6de-4bae-ad98-84a49a7e69cc.png)

## pow( )
- 제곱값 반환

```python
print(pow(2, 10))
```

![image](https://user-images.githubusercontent.com/121333241/217177347-20030a0f-5d70-4937-a60d-604ca7768235.png)

## round
- 반올림

```python
print(round(6.5781, 2)) # 둘째자리에서 반올림
print(round(5.6)) # 두번째 인자가 없다면 첫째자리에서 바로 반올림한다.
```

![image](https://user-images.githubusercontent.com/121333241/217177466-5d25e864-103c-4b7a-b1a5-c89e8038da11.png)

# sum
- 반복가능한 객체(Iterable) 합 반환

```python
print(sum([6, 7, 8, 9, 10]))
print(sum(range(1, 101)))
```

![image](https://user-images.githubusercontent.com/121333241/217177587-5139b445-3749-4af4-bbb7-959387afd88e.png)

## iterable 요소 검사 (참, 거짓)

### all( ) 
- 모두 참이어야 참 (and)

```python
print(all([1, 2, 3])) 
print(all([1, 2, 0])) # 하나라도 거짓이면(0, ''...) False
```

![image](https://user-images.githubusercontent.com/121333241/217177728-93344d05-c905-4db3-9817-b517e0e3d4bc.png)

### any( )
- 하나라도 참이면 참 (or)

```python
print(any([1, 2, 0])) 
```

![image](https://user-images.githubusercontent.com/121333241/217177848-9db80f16-0da2-4c22-91aa-d2d23ac766b2.png)

## chr( ) : 아스키 -> 문자

```python
print(chr(67))
```

![image](https://user-images.githubusercontent.com/121333241/217177935-09bad358-229c-4a93-94a7-2f236c8af6da.png)

## ord : 문자 -> 아스키

```python
print(ord('C'))
```

![image](https://user-images.githubusercontent.com/121333241/217178010-2b48755c-ca1f-4dcf-93df-ccd55eb5f296.png)

## enumerate( )
- 인덱스 + Iterable 객체 생성

```python
for i, name in enumerate(['abc', 'bcd', 'efg']):
    print(i, name)
```

![image](https://user-images.githubusercontent.com/121333241/217178130-7e8286ea-994e-4f01-8e92-23cbd7b143be.png)

## range( )
- 반복가능한 객체(Iterable) 반환

```python
print(list(range(1, 10 ,2))) # 1부터 9까지 2씩 증가하면서 출력
print(list(range(0, -15 ,-1))) # 0부터 -14까지 -1씩 증가하면서 출력
```

![image](https://user-images.githubusercontent.com/121333241/217178252-4b13e5ac-6aa5-4e56-a27b-f101aaa13c19.png)

## filter( )
- 반복가능한 객체 요소를 지정한 함수 조건에 맞는 값 추출

```python
def conv_pos(x):
    return abs(x) > 2

print(list(filter(conv_pos, [1, -3, 2, 0, -5, 6]))) # 함수의 이름만 적으면 된다.
# 조건에 맞는 -3, -5, 6만 출력된다. 조건에 맞지 않는 1, 2, 0은 filtering 되어서 출력되지 않는다.
print(list(filter(lambda x: abs(x) > 2, [1, -3, 2, 0, -5, 6]))) # lambda식 사용
```

![image](https://user-images.githubusercontent.com/121333241/217178373-1dba6139-84e1-40c4-a9fd-fe9648c20bea.png)

## map( )
- 반복가능한 객체 요소를 지정한 함수 실행 후 추출

```python
def conv_abs(x):
    return abs(x)

print(list(map(conv_abs, [1, -3, 2, 0, -5, 6])))
# 함수를 거쳐서 나오는 값들을 모두 출력해준다.
print(list(map(lambda x: abs(x), [1, -3, 2, 0, -5, 6])))
```

![image](https://user-images.githubusercontent.com/121333241/217178516-25602e45-0c93-4094-8417-40a7f3cac066.png)

## id( )
- 객체의 주소값(레퍼런스) 반환

```python
print(id(int(5)))
print(id(4))
```

![image](https://user-images.githubusercontent.com/121333241/217178651-88c2378d-2264-45e1-906a-91ee5f2300ce.png)

## type( )
- 자료형 확인

```python
print(type(3))
print(type({}))
print(type({1, 2}))
print(type(()))
print(type([]))
```

![image](https://user-images.githubusercontent.com/121333241/217178789-53f889ae-5673-4884-a3e2-ef1678bf8279.png)

## len( ) 
- 요소의 길이 반환

```python
print(len('abcdefg'))
print(len([1, 2, 3, 4, 5, 6, 7]))
```

![image](https://user-images.githubusercontent.com/121333241/217179008-c7e6974e-e1f6-4e81-bdcf-a9132249c829.png)

## max( ), min( )
- 최대값, 최소값

```python
print(max([1, 2, 3]))
print(max('python study'))
print(min([1, 2, 3]))
print(min('python study')) # 공백을 가장 작은 값으로 인식한다.
```

![image](https://user-images.githubusercontent.com/121333241/217179110-bc4fe229-29d6-41d8-8fcf-69d194268f22.png)

## sorted( )
- 반복가능한 객체(Iterable - list, tuple, set, dictionary)를 정렬 후 반환

```python
print(sorted([6, 7, 4, 3, 1, 2]))
a = sorted([6, 7, 4, 3, 1, 2])
print(a)
print(sorted(['p', 'y', 't', 'h', 'o', 'n']))
```

![image](https://user-images.githubusercontent.com/121333241/217179234-a45b98b8-6a9d-484e-a320-93f752d9d9ca.png)

## zip( )
- 반복가능한 객체(Iterable)의 요소를 묶어서 반환

```python
print(list(zip([10, 20, 30], [40, 50, 60]))) # 같은 위치끼리 묶어서 반환
print(list(zip([10, 20, 30], [40, 50]))) # 짝이 맞는 것만 반환
print(type(list(zip([10, 20, 30], [40, 50, 60]))[0])) 
# tuple로 만들어서 짝을 맞춰 반환
```

![image](https://user-images.githubusercontent.com/121333241/217179389-b3bb6eca-84c4-4de7-9146-2cf95be6dbc4.png)
