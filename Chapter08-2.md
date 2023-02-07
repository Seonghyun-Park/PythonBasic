# Chapter08-2
- 파이썬 외장 (External) 함수
- 실제 프로그램 개발 중 자주 사용
- 종류 : sys, pickle, shutil, time, random 등 


## sys.

## 예제 1 - argv

```python
import sys
print(sys.argv)
```

## 예제 2 - exit( )
- 강제 종료 - 위험한 코드

```python
# sys.exit()
```

## 예제 3 - path
- 파이썬 패키지 위치

```python
print(sys.path) # 현재 모든 패키지들의 위치를 알려준다.
print()
```
---

## pickle.
- 객체 파일 읽기, 쓰기
- 파이썬에서 사용할 수 있는 어떤 객체(class, dictionary, list, tuple)를 저장장치에 쓰고 읽을 때 사용하는 것

## 예제 4 - dump( )
- 쓰기

```python
import pickle

f = open("test.obj", "wb") # 파일을 연다.
obj = {1: 'python', 2: 'study', 3: 'basic'}
pickle.dump(obj, f) # 파일(f)에 obj를 쓴다.(dump)
f.close() # 파일을 닫는다.
print()
```

## 예제 5 - load( )
- 읽기

```python
f = open('test.obj', 'rb') # 파일을 연다.
data = pickle.load(f) # f를 연결해서 읽어온다.(load)
print(data, type(data))
f.close() # 파일을 닫는다.
print()
```
---

## os 
- 환경 변수, 디렉토리(파일) 처리 관련, 운영체제 작업 관련
- mkdir(폴더 생성), rmdir(폴더가 비어있으면 삭제), rename(이름 바꾸기)

## 예제 6 - environ( )

```python
import os

print(os.environ) # 운영체제에 대한 정보
print()
print(os.environ["USERNAME"])
```

## 예제 7 - getcwd( )
- 현재 경로

```python
print(os.getcwd())
print()
```
---

## time.
- 시간 관련 처리

## 예제 8 - time( )

```python
import time

print(time.time())
```

## 예제 9 - localtime( )
- 형태 변환

```python
print(time.localtime(time.time()))
```

## 예제 10 - ctime( )
- 간단 표현

```python
print(time.ctime())
```

## 예제 11 - strftime( )
- 형식 표현 - 원하는 방식으로 표현

```python
print(time.strftime('%Y-%m-%d %H:%M:%S', time.localtime(time.time())))
```

## 예제 12 - sleep( )
- 시간 간격 발생

```python
for i in range(5):
    print(i)
    time.sleep(1) # 1초 간격으로 출력된다.(1초를 쉰다.)
```    
---

## random.
- 난수 생성

## 예제 13 - random( )

```python
import random

print(random.random()) # 0 ~ 1 실수
```

## 예제 14 - randint( ), randrange( )

```python
print(random.randint(1, 45)) # 1 ~ 45 사이의 정수값을 랜덤으로 가져온다.
print(random.randrange(1, 45)) # 1 ~ 44(45-1) 사이의 정수값을 랜덤으로 가져온다.
```

## 예제 15 - shuffle( )
- 섞기

```python
d = [1, 2, 3, 4, 5]
random.shuffle(d)
print(d)
```

## 예제 16 - choice( )
- 무작위 선택

```python
c = random.choice(d)
print(c)
```
---

## webbrowser
- 본인 os의 웹 브라우저 실행

## 예제 17 - open( ), open_new( )

```python
import webbrowser

webbrowser.open("http://google.com")
webbrowser.open_new("http://google.com") # 새로운 창으로 열린다.
```