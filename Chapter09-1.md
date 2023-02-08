# Chapter09-1
- 파일 읽기 및 쓰기
- 읽기(read) 모드: r, 쓰기(wirte) 모드: w, 추가(append) 모드: a, 텍스트 모드: t, 바이너리 모드: b
- 상대 경로('../(상위 폴더), ./(현재)'), 
- 절대 경로('C:\Dijango\example..') - 어떤 경로에서 작업을 하든지 간에 저장 장치의 루트경로부터 따진다. 

## 파일 읽기 (Read)

## 예제 1

```python
f = open('./resource/it_news.txt', 'r', encoding = 'UTF-8')

# 속성 확인
print(dir(f))

# 인코딩 확인
print(f.encoding)

# 파일 이름
print(f.name)

# 모드 확인
print(f.mode)
print()

# 내용 불러오기
cts = f.read()
print(cts)

# 반드시 close
f.close() # 중요!
```

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

## 파일 쓰기 (write)

## 예제 1

```python
with open('./resource/contents1.txt', 'w') as f:
    f.write('I love python\n')
```
    
## 예제 2

```python
with open('./resource/contents1.txt', 'a') as f: # a는 추가
    f.write('I love python2\n')
```

## 예제 3
- writelines : 리스트 -> 파일

```python
with open('./resource/contents2.txt', 'w') as f:
    list = ['Orange\n', 'Apple\n', 'Banana\n', 'Melon\n']
    f.writelines(list)
```
    
## 예제 4

```python
with open('./resource/contents3.txt', 'w') as f:
    print('Test Text Write!', file = f)
    print('Test Text Write!', file = f)
    print('Test Text Write!', file = f)
```