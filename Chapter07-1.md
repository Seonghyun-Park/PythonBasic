# Chapter07-1
- 파이썬 예외처리의 이해
- 예외 종류
- SyntaxError, TypeError, NameError, IndexError, ValueError, KeyError...
- 문법적으로는 예외가 없지만, 코드 실행 프로세스(단계) 발생하는 예외도 중요
- 1. 예외는 반드시 처리
- 2. 로그(증거, 기록)는 반드시 남긴다. 
- 3. 예외는 던져진다.
- 4. 예외 무시

- 예외가 없는 것을 가정하고 프로그램 작성 -> 런타임 예외 발생 시 예외 처리 권장(EAEP)

## SyntaxError
- 문법이 맞지 않을 때 발생하는 오류

```python
print('error)
print('error'))
if True
    pass
```

## NameError
- 선언하지 않은, 없는 변수를 참조할 때 발생하는 오류

```python
a = 10
b = 15
print(c)
```

## ZeroDivisionError 
- 0으로 나눴을 때 발생하는 오류

```python
print(100 / 0)
```

## IndexError
- 원소가 맞지 않을 때 발생하는 오류

```python
x = [50, 70, 90]
print(x[4])
print(x.pop())
print(x.pop())
print(x.pop())
print(x.pop())
```

## KeyError
- 딕셔너리 구조에서 없는 key를 호출할 때 발생하는 오류

```python
dic = {'name' : 'Lee', 'Age' : 41, 'City' : 'Busan'}
print(dic['hobby'])
print(dic.get('hobby')) # get함수를 사용하는 것이 더 안전하다.
```

## AttributeError
- 모듈, 클래스에 있는 잘못된 속성 사용 예외

```python
import time
print(time.time2())
```

## ValueError
- 값이 존재하지 않을 때 발생하는 에러

```python
x = [10, 50, 90]
x.remove(50)
print(x)
x.remove(200)
```

## FileNotFoundError
- 파일이 존재하지 않을 때 발생하는 에러

```python
f = open('test.txt')
```

## TypeError
- 자료형에 맞지 않는 연산을 수행할 경우

```python
x = [1, 2]
y = (1, 2)
z = 'test'

print(x + y)
print(x + z)
print(y + z)

# 올바른 형 변환
print(x + list(y))
print(x + list(z))
```

# 예외 처리
- try - exception - else - finally
- try : 에러가 발생할 가능성이 있는 코드 실행
- except 에러명1: 여러개 가능
- except 에러명2:
- else : try 블록의 에러가 없을 경우 실행(try문에서 에러가 발생하지 않은 경우 else문 실행)
- finally : 항상 마지막에 실행

### 선언
```python
name = ['Kim', 'Lee', 'Park']
```

## 예제 1

```python
try:
    z = 'Kim' # 'Cho'
    x = name.index(z)
    print('{} Found it! {} in name'.format(z, x + 1))
except ValueError: # ValueError가 발생했을 때 
    print('Not Found it! - Occurred ValueError!')
else:
    print('OK! else.')
    
print()
```

## 예제 2

```python
try:
    z = 'Cho'
    x = name.index(z)
    print('{} Found it! {} in name'.format(z, x + 1))
except Exception: # 모든 예외를 처리 - 하지만 어떤 에러인지 정확히 알지 못한다.
    print('Not Found it! - Occurred Error!')
else:
    print('OK! else.')
    
print()
```

## 예제 3

```python
try:
    z = 'Cho'
    x = name.index(z)
    print('{} Found it! {} in name'.format(z, x + 1))
except Exception as e:
    print(e) # 에러의 내용을 출력할 때 사용
    print('Not Found it! - Occurred Error!')
else:
    print('OK! else.')
finally:
    print('Ok! finally!') # 에러가 발생하였어도 마지막에 무조건 실행
    
print()
```

## 예제 4
- 예외 발생 : raise
- raise 키워드로 예외 직접 발생
- 프로그램의 설계상 들어오면 안되는 값이 들어오거나 예외로 간주해야 하는 경우

```python
try:
    a = 'Park'
    if a == 'Kim':
        print('OK! Pass!')
    else:
        raise ValueError
except ValueError:
    print('Occured! Exception!')
else:
    print('Ok! else!')
```
