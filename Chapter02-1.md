# Chapter02-1

- 파이썬 완전 기초
- print 사용법
- 참조 : https://www.python-course.eu/python3_formatted_output.php

## 기본 출력

```python
print('Python Start!')
print("Python Start!")
print('''Python Start!''')
print("""Python Start!""")
print()
```

## seperator 옵션

- 사이에 뭐가 들어갈지 결정한다.

```python
print('P', 'Y', 'T', 'H', 'O', 'N', sep = '')
print('010', '7777', '1234', sep = '-')
print('python', 'google.com', sep = '@')
print()
```

## end 옵션
- 한 줄로 출력한다.

```python
print('Welcome to', end = ' ')
print('IT News', end = ' ')
print('Web Site')
print()
```

## file 옵션 
- 파일 출력 형태를 결정

```python
import sys
print('Learn Python', file = sys.stdout)
print()
```

## format 사용
- d(정수) : 3, s(문자열) : 'python', f(실수) : 3.141592

```python
print('%s %s' %('one', 'two')) # format을 정확하게 알고 있을 때
print('{} {}'.format('one', 'two')) # format함수가 내부적으로 처리
print('{1} {0}'.format('one', 'two')) # 인덱스가 0부터 시작하기 때문에 두번째인 {1}에 해당하는 two가 앞에 온다.
print()
```

## %s

```python
print('%10s' %('nice')) # 숫자가 오면 자릿수를 의미
print('{:>10}'.format('nice'))

print('%-10s' %('nice')) # 오른쪽 정렬
print('{:10}'.format('nice'))
 
print('{:_>10}'.format('nice')) # 빈자리를 원하는 기호로 채운다.
print('{:^10}'.format('nice')) # 중앙 정렬

print('%.5s' %('nice'))
print('%.5s' %('pythonstudy')) # 5글자까지만 출력한다.
print('{:10.5}'.format('pythonstudy')) # 10칸 중에 5개만 출력
print()
```

## %d

```python
print('%d %d' %(1,2))
print('{} {}'.format(1,2))

print('%4d' %(42))
print('{:4d}'.format(42))
print()
```

## %f

```python
print('%f' %3.14343434343434343) # %정수부.소수부f
print('{:f}'.format(3.14343434343434343))

print('%06.2f' %(3.141592653589793)) # 총 6자리 나머지는 0으로
print('{:06.2f}'.format(3.141592653589793))
print()
```
