# Chapter09-2
- CSV 파일 읽기 및 쓰기
- CSV : MEME - text/csv

## 예제 1

```python
import csv

with open('./resource/test1.csv', 'r') as f:
    reader = csv.reader(f) # csv는 기본적으로 콤마(,)로 가져온다.
    # next(reader) # Header Skip(제일 첫째 줄은 생략한다.)
    
    # 객체 확인
    print(reader)
    
    # 타입 확인
    print(type(reader))
    
    # 속성 확인
    print(dir(reader)) # __iter__
    print()
    
    for c in reader:
        # print(c)
        
        # 타입 확인(리스트)
        # print(type(c))
        # list to str
        print(' : '.join(c))
```

## 예제 2

```python
with open('./resource/test2.csv', 'r') as f:
    reader = csv.reader(f, delimiter = '|') # 지정한 특수기호로 csv의 내용을 가져온다.
    
    for c in reader:
        print(c)
```

## 예제 3

```python
with open('./resource/test1.csv', 'r') as f:
    reader = csv.DictReader(f)
    
    # 확인
    print(reader)
    print(type(reader))
    print(dir(reader))
    print()
    
    for c in reader:
        for k, v in c.items():
           print(k, v)
        print('----------------')
```    
    
## 예제 4

```python
w = [[1,2,3],[4,5,6],[7,8,9],[10,11,12],[13,14,15],[16,17,18],[19,20,21]]

with open('./resource/write1.csv', 'w', encoding='UTF-8') as f:
    print(dir(csv))
    wt = csv.writer(f)
    
    # dir 확인
    # print(dir(wt))
    # 타입 확인
    # print(type(wt))
    
    for v in w:
        wt.writerow(v)
```

## 예제 5

```python
with open('./resource/write2.csv', 'w', encoding='UTF-8') as f:
    # 필드명
    fields = ['One', 'Two', 'Three']
    
    # Dict writer
    wt = csv.DictWriter(f, fieldnames=fields)
    # Header Writer
    wt.writeheader()
    
    for v in w:
        wt.writerow({'One': v[0], 'Two': v[1], 'Three': v[2]})
```