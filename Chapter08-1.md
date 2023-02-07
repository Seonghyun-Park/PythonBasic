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

## pow( )
- 제곱값 반환

```python
print(pow(2, 10))
```

## round
- 반올림

```python
print(round(6.5781, 2)) # 둘째자리에서 반올림
print(round(5.6)) # 두번째 인자가 없다면 첫째자리에서 바로 반올림한다.
```

# sum
- 반복가능한 객체(Iterable) 합 반환

```python
print(sum([6, 7, 8, 9, 10]))
print(sum(range(1, 101)))
```

## iterable 요소 검사 (참, 거짓)

### all( ) 
- 모두 참이어야 참 (and)

```python
print(all([1, 2, 3])) 
print(all([1, 2, 0])) # 하나라도 거짓이면(0, ''...) False
```

### any( )
- 하나라도 참이면 참 (or)

```python
print(any([1, 2, 0])) 
```

## chr( ) : 아스키 -> 문자

```python
print(chr(67))
```

## ord : 문자 -> 아스키

```python
print(ord('C'))
```

## enumerate( )
- 인덱스 + Iterable 객체 생성

```python
for i, name in enumerate(['abc', 'bcd', 'efg']):
    print(i, name)
```

## range( )
- 반복가능한 객체(Iterable) 반환

```python
print(list(range(1, 10 ,2))) # 1부터 9까지 2씩 증가하면서 출력
print(list(range(0, -15 ,-1))) # 0부터 -14까지 -1씩 증가하면서 출력
```

## filter( )
- 반복가능한 객체 요소를 지정한 함수 조건에 맞는 값 추출

```python
def conv_pos(x):
    return abs(x) > 2

print(list(filter(conv_pos, [1, -3, 2, 0, -5, 6]))) # 함수의 이름만 적으면 된다.
# 조건에 맞는 -3, -5, 6만 출력된다. 조건에 맞지 않는 1, 2, 0은 filtering 되어서 출력되지 않는다.
print(list(filter(lambda x: abs(x) > 2, [1, -3, 2, 0, -5, 6]))) # lambda식 사용
```

## map( )
- 반복가능한 객체 요소를 지정한 함수 실행 후 추출

```python
def conv_abs(x):
    return abs(x)

print(list(map(conv_abs, [1, -3, 2, 0, -5, 6])))
# 함수를 거쳐서 나오는 값들을 모두 출력해준다.
print(list(map(lambda x: abs(x), [1, -3, 2, 0, -5, 6])))
```

## id( )
- 객체의 주소값(레퍼런스) 반환

```python
print(id(int(5)))
print(id(4))
```

## type( )
- 자료형 확인

```python
print(type(3))
print(type({}))
print(type({1, 2}))
print(type(()))
print(type([]))
```

## len( ) 
- 요소의 길이 반환

```python
print(len('abcdefg'))
print(len([1, 2, 3, 4, 5, 6, 7]))
```

## max( ), min( )
- 최대값, 최소값

```python
print(max([1, 2, 3]))
print(max('python study'))
print(min([1, 2, 3]))
print(min('python study')) # 공백을 가장 작은 값으로 인식한다.
```

## sorted( )
- 반복가능한 객체(Iterable - list, tuple, set, dictionary)를 정렬 후 반환

```python
print(sorted([6, 7, 4, 3, 1, 2]))
a = sorted([6, 7, 4, 3, 1, 2])
print(a)
print(sorted(['p', 'y', 't', 'h', 'o', 'n']))
```

## zip( )
- 반복가능한 객체(Iterable)의 요소를 묶어서 반환

```python
print(list(zip([10, 20, 30], [40, 50, 60]))) # 같은 위치끼리 묶어서 반환
print(list(zip([10, 20, 30], [40, 50]))) # 짝이 맞는 것만 반환
print(type(list(zip([10, 20, 30], [40, 50, 60]))[0])) 
# tuple로 만들어서 짝을 맞춰 반환
```