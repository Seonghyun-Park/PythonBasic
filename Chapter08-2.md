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

![image](https://user-images.githubusercontent.com/121333241/217247161-b7dda2f0-116a-4add-921c-a660592e9fa9.png)

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

![image](https://user-images.githubusercontent.com/121333241/217247276-88097028-7520-4404-9fe4-6d6e2d9da267.png)

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

![image](https://user-images.githubusercontent.com/121333241/217247545-328ee5d8-7388-49d8-90d7-11c28a34601c.png)

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

![image](https://user-images.githubusercontent.com/121333241/217247667-9cfe6f9e-2471-4485-b2da-dab8f055aaa8.png)
![image](https://user-images.githubusercontent.com/121333241/217247740-732df932-0774-476e-97f3-80fc93c1a444.png)

## 예제 7 - getcwd( )
- 현재 경로

```python
print(os.getcwd())
print()
```

![image](https://user-images.githubusercontent.com/121333241/217247791-d044b663-4be8-4136-82f7-49f6e87aa8fb.png)

---

## time.
- 시간 관련 처리

## 예제 8 - time( )

```python
import time

print(time.time())
```

![image](https://user-images.githubusercontent.com/121333241/217247858-f4faf35e-b40f-4732-ba45-9a5bc9673717.png)

## 예제 9 - localtime( )
- 형태 변환

```python
print(time.localtime(time.time()))
```

![image](https://user-images.githubusercontent.com/121333241/217248010-d5d472f9-4b5f-464a-a3dc-4b12c2614320.png)

## 예제 10 - ctime( )
- 간단 표현

```python
print(time.ctime())
```

![image](https://user-images.githubusercontent.com/121333241/217248069-e3d7cf6f-6f1f-4a56-8c82-78f13f470a6c.png)

## 예제 11 - strftime( )
- 형식 표현 - 원하는 방식으로 표현

```python
print(time.strftime('%Y-%m-%d %H:%M:%S', time.localtime(time.time())))
```

![image](https://user-images.githubusercontent.com/121333241/217248121-3c3d146d-4e5e-4b0c-8bb4-b6dbf2b1563e.png)

## 예제 12 - sleep( )
- 시간 간격 발생

```python
for i in range(5):
    print(i)
    time.sleep(1) # 1초 간격으로 출력된다.(1초를 쉰다.)
```  

![image](https://user-images.githubusercontent.com/121333241/217248472-1bbdec55-fcda-4c08-842f-e15f8a554f14.png)

---

## random.
- 난수 생성

## 예제 13 - random( )

```python
import random

print(random.random()) # 0 ~ 1 실수
```

![image](https://user-images.githubusercontent.com/121333241/217248211-44996c5e-c64a-4f17-ac40-37ddf8da3f4d.png)

## 예제 14 - randint( ), randrange( )

```python
print(random.randint(1, 45)) # 1 ~ 45 사이의 정수값을 랜덤으로 가져온다.
print(random.randrange(1, 45)) # 1 ~ 44(45-1) 사이의 정수값을 랜덤으로 가져온다.
```

![image](https://user-images.githubusercontent.com/121333241/217248243-04ab6681-fbbe-4b2a-9202-b10ce3c2d2ed.png)

## 예제 15 - shuffle( )
- 섞기

```python
d = [1, 2, 3, 4, 5]
random.shuffle(d)
print(d)
```

![image](https://user-images.githubusercontent.com/121333241/217248274-695d5bfe-cb65-4c00-b6c2-a1a60803dc73.png)

## 예제 16 - choice( )
- 무작위 선택

```python
c = random.choice(d)
print(c)
```

![image](https://user-images.githubusercontent.com/121333241/217248344-3e32d9df-2c97-4dec-b1a2-1b631cb6c0a8.png)

---

## webbrowser
- 본인 os의 웹 브라우저 실행

## 예제 17 - open( ), open_new( )

```python
import webbrowser

webbrowser.open("http://google.com")
webbrowser.open_new("http://google.com") # 새로운 창으로 열린다.
```

![image](https://user-images.githubusercontent.com/121333241/217248937-80825303-f806-4693-ad78-454615b9b33c.png)
