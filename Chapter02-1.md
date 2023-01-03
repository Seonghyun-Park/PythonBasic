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
![image](https://user-images.githubusercontent.com/121333241/210305705-a6d31b62-db99-4a41-ae62-5d541f00bb9c.png)

## seperator 옵션

- 사이에 뭐가 들어갈지 결정한다.

```python
print('P', 'Y', 'T', 'H', 'O', 'N', sep = '')
print('010', '7777', '1234', sep = '-')
print('python', 'google.com', sep = '@')
print()
```
![image](https://user-images.githubusercontent.com/121333241/210305825-a27428d5-a46d-47e9-b64b-f9462931bfdb.png)

## end 옵션

- 한 줄로 출력한다.

```python
print('Welcome to', end = ' ')
print('IT News', end = ' ')
print('Web Site')
print()
```
![image](https://user-images.githubusercontent.com/121333241/210305899-14765286-9707-417f-b35e-212a8f452e9c.png)

## file 옵션 

- 파일 출력 형태를 결정

```python
import sys
print('Learn Python', file = sys.stdout)
print()
```
![image](https://user-images.githubusercontent.com/121333241/210305940-56afcc53-e53a-43e9-ae2e-389cb595cf04.png)


## format 사용

- d(정수) : 3, s(문자열) : 'python', f(실수) : 3.141592

```python
print('%s %s' %('one', 'two')) # format을 정확하게 알고 있을 때
print('{} {}'.format('one', 'two')) # format함수가 내부적으로 처리
print('{1} {0}'.format('one', 'two')) # 인덱스가 0부터 시작하기 때문에 두번째인 {1}에 해당하는 two가 앞에 온다.
print()
```
![image](https://user-images.githubusercontent.com/121333241/210306151-4fd4366e-7bf5-4c4e-a9d1-90b32b70f252.png)

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
![image](https://user-images.githubusercontent.com/121333241/210306235-46e109a3-5737-49e5-aa3e-87ff87fa3186.png)


## %d

```python
print('%d %d' %(1,2))
print('{} {}'.format(1,2))

print('%4d' %(42))
print('{:4d}'.format(42))
print()
```
![image](https://user-images.githubusercontent.com/121333241/210306257-1e20a135-cb53-4ff9-82dc-fab5ca82ad26.png)

## %f

```python
print('%f' %3.14343434343434343) # %정수부.소수부f
print('{:f}'.format(3.14343434343434343))

print('%06.2f' %(3.141592653589793)) # 총 6자리 나머지는 0으로
print('{:06.2f}'.format(3.141592653589793))
print()
```
![image](https://user-images.githubusercontent.com/121333241/210306287-a3202e7b-db80-4d73-9295-9f46d24e6a2a.png)
