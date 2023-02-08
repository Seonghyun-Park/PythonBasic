# Chapter09-1
- 파일 읽기 및 쓰기
- 읽기(read) 모드: r, 쓰기(wirte) 모드: w, 추가(append) 모드: a, 텍스트 모드: t, 바이너리 모드: b
- 상대 경로('../(상위 폴더), ./(현재)'), 
- 절대 경로('C:\Dijango\example..') - 어떤 경로에서 작업을 하든지 간에 저장 장치의 루트경로부터 따진다. 

## 파일 읽기 (Read)

## 예제 1

```python
f = open('./resource/it_news.txt', 'r', encoding = 'UTF-8')
```

### 속성 확인
```python
print(dir(f))
```

![image](https://user-images.githubusercontent.com/121333241/217520483-ad3dc2cd-3be7-4476-b37d-98117d95fb52.png)

### 인코딩 확인
```python
print(f.encoding)
```

![image](https://user-images.githubusercontent.com/121333241/217520579-53584cf6-b825-41c6-9f93-c860dac23a45.png)

### 파일 이름
```python
print(f.name)
```

![image](https://user-images.githubusercontent.com/121333241/217520893-cbd3adf7-2e15-40e2-a7bd-ad20380b77e1.png)

### 모드 확인
```python
print(f.mode)
print()
```

![image](https://user-images.githubusercontent.com/121333241/217520999-b60dabcd-4da9-42e3-b847-bbe15d24309b.png)

### 내용 불러오기
```python
cts = f.read()
print(cts)

# 반드시 close
f.close() # 중요!
```

![image](https://user-images.githubusercontent.com/121333241/217521131-acfcf3fc-f925-4d21-9c5a-dcef714e5fa4.png)

## 예제 2

```python
with open('./resource/it_news.txt', 'r', encoding = 'UTF-8') as f:
    c = f.read()
    print(c)
    print(iter(c))
    print(list(c))
    # with문 내부적으로 파일을 닫는다.
print()
```

![image](https://user-images.githubusercontent.com/121333241/217521371-5fe9dba8-9e48-41f3-85bf-0dd3eb484d79.png)
![image](https://user-images.githubusercontent.com/121333241/217521404-870a3554-0c92-4cc7-bfdf-182ecc0b2481.png)
![image](https://user-images.githubusercontent.com/121333241/217521508-e4802059-b748-4b9c-9a6d-3a580b6f4f3f.png)

## 예제 3
- read( ): 전체 읽기, read(10): 10 Byte

```python
with open('./resource/it_news.txt', 'r', encoding = 'UTF-8') as f:
    c = f.read(20) # 20 Byte를 읽어온다.
    print(c)
    c = f.read(20)
    print(c) # 커서가 내부적으로 동작을 해서 뒷 부분부터 읽어온다.
    f.seek(0,0)
    c = f.read(20)
    print(c)
```

![image](https://user-images.githubusercontent.com/121333241/217521603-2fefffa7-b875-4c8c-b114-c328514f9a48.png)

## 예제 4
- readline( ): 한 줄 씩 읽기

```python
with open('./resource/it_news.txt', 'r', encoding = 'UTF-8') as f:
    line = f.readline()
    print(line)
    line = f.readline()
    print(line)

print()
```

![image](https://user-images.githubusercontent.com/121333241/217521777-03901e1d-cdf1-4f46-8008-26337ddb0e59.png)

## 예제 5
- readlines( ): 전체를 읽은 후 라인 단위 리스트로 저장

```python
with open('./resource/it_news.txt', 'r', encoding = 'UTF-8') as f:
    cts = f.readlines()
    print(cts)
    print()
    for c in cts:
        print(c, end='')

print()
```

![image](https://user-images.githubusercontent.com/121333241/217522593-041febf9-16e2-4f1d-b3c3-2ccd9276c025.png)

## 파일 쓰기 (write)

## 예제 1

```python
with open('./resource/contents1.txt', 'w') as f:
    f.write('I love python\n')
```

![image](https://user-images.githubusercontent.com/121333241/217522238-7c1a3e29-ec66-4288-baf4-7cd2f7d731de.png)

## 예제 2

```python
with open('./resource/contents1.txt', 'a') as f: # a는 추가
    f.write('I love python2\n')
```

![image](https://user-images.githubusercontent.com/121333241/217522139-26a8dc71-0ab1-4252-85f3-35c3037b3c04.png)

## 예제 3
- writelines : 리스트 -> 파일

```python
with open('./resource/contents2.txt', 'w') as f:
    list = ['Orange\n', 'Apple\n', 'Banana\n', 'Melon\n']
    f.writelines(list)
```

![image](https://user-images.githubusercontent.com/121333241/217522285-1f26c74f-fc63-4990-877c-3f3a209b14a8.png)

## 예제 4

```python
with open('./resource/contents3.txt', 'w') as f:
    print('Test Text Write!', file = f)
    print('Test Text Write!', file = f)
    print('Test Text Write!', file = f)
```

![image](https://user-images.githubusercontent.com/121333241/217522336-1794387a-5ab8-4b64-b628-cfeb06c77964.png)
