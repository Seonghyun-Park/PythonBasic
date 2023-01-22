# Chapter03-1

- 파이썬 기초 자료형
- 숫자형

## 파이썬 지원 자료형

```python
'''
int : 정수
float : 실수
complex : 복소수
bool : 불린
str : 문자열(시퀀스)
list : 리스트(시퀀스)
tuple : 튜플(시퀀스)
set : 집합
dict : 사전
'''
```

## 데이터 타입

```python
str1 = "Python"
bool = True
str2 = 'Anaconda'
float_v = 10.0 # 10 != 10.0
int_v = 7
list = [str1, str2]
dict = {
    "name": "Machine Learning,",
    "version": 2.0 # 2.0을 꺼내기 위해서는 version이라는 key가 필요하다.
}
tuple = (7, 8, 9) # = 7, 8, 9
set = {3, 5, 7}
```

## 데이터 타입 출력

```python
print(type(str1))
print(type(bool))
print(type(str2))
print(type(float_v))
print(type(int_v))
print(type(dict))
print(type(tuple))
print(type(set))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210560498-17a4c88b-f110-416b-bd0c-3bb071dd3193.png)

## 숫자형 연산자

```python
"""
+
-
*
/
// : 몫
% : 나머지
abs(x) : 절댓값
pow(x, y) : x ** y (x의 y제곱)
"""
```

## 정수 선언

```python
i = 77
i2 = 14
big_int = 77777777777777777777777777999999999999999999999999
```

## 정수 출력

```python
print(i)
print(i2)
print(big_int)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210560621-4846de03-8f50-47af-ba34-a547d253cd21.png)

## 실수 선언

```python
f = 0.9999
f2 = 3.141592
f3 = -3.9
f4 = 3 / 9
```

## 실수 출력

```python
print(f)
print(f2)
print(f3)
print(f4)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210560678-76e15869-4dc2-495d-83e6-f94e52c5f3ee.png)

## 연산 실습

```python
i1 = 39
i2 = 939
big_int1 = 77777777777778888888888888888
big_int2 = 32154895465483215321568865212
f1 = 1.234
f2 = 3.939
```

## +

```python
print(">>>>> +")
print("i1 + i2 : ", i1 + i2)
print("f1 + f2 : ", f1 + f2)
print("big_int1 + big_int2 : ", big_int1 + big_int2)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561156-e4fa5ccb-0e23-49e3-aed2-49b0df231d7d.png)

## -

```python
print(">>>>> -")
print("i1 - i2: ", i1 - i2) 
print("f1 - f2: ", f1 - f2)
print("big_int1 - big_int2: ", big_int1 - big_int2)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561414-fe616551-d424-4b49-b6eb-85c1edbb1c2a.png)

## *

```python
print(">>>>> *")
print("i1 * i2 : ", i1 * i2)
print("f1 * f2 : ", f1 * f2)
print("big_int1 * big_int2 : ", big_int1 * big_int2)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561476-cce0e80d-beaa-4e91-b48c-f44bee6d7c61.png)

## /

```python
print(">>>>> /")
print("i2 / i1: ", i2 / i1)
print("f2 / f1: ", f2 / f1)
print("big_int2 / big_int1: ", big_int2 / big_int1)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561743-47ffa4e5-a7f8-41ff-90d0-09493e963b6c.png)

## //

```python
print(">>>>> //")
print("i2 // i1: ", i2 // i1) 
print("f2 // f1: ", f2 // f1)
print("big_int2 // big_int1: ", big_int2 // big_int1)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561790-114cc8df-0226-4b6f-a5e4-62108bfab5e4.png)

## %

```python
print(">>>>> %")
print("i1 % i2 :", i1 % i2)
print("f1 % f2 :", f1 % f2)
print("big_int1 % big_int2 :", big_int1 % big_int2)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561844-6c223f54-00c4-43e5-9416-8f129006a5a8.png)

## **

```python
print(">>>>> **")
print("2 ** 3: ", 2 ** 3)
#print("i1 ** i2: ", i1 ** i2) 
print("f1 ** f2: ", f1 ** f2)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561896-dc6d3d74-2e53-42f1-a1fb-49895a7634d2.png)

## 형 변환 실습

```python
a = 3. # 3.0을 의미 (0 생략 가능)
b = 6
c = .7
d = 12.7
```

## 타입 출력

```python
print(type(a), type(b), type(c), type(d))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210561956-5b464269-8191-4979-be3d-660a65a811c5.png)

## 형 변환

```python
print(float(b)) # 정수형 -> 실수형
print(int(c)) 
print(int(d)) # 실수형 -> 정수형 (소수점의 자리는 없어진다.)
print(int(True)) # True : 1, False : 0
print(float(False))
print(complex(3))
print(complex('3')) # 문자형 -> 숫자형
print(complex(False))
print()
```

![image](https://user-images.githubusercontent.com/121333241/210562020-b979caef-e9b7-4ce7-8f46-4e12f97f8073.png)

## 수치 연산 함수

```python
print(abs(-7))
x, y = divmod(100, 8) # 나눈 후 몫과 나머지를 계산
print(x, y)
print(pow(5,3), 5**3)
print()
```

![image](https://user-images.githubusercontent.com/121333241/210562082-72045ae0-4cd0-4574-9e83-6d8be1064255.png)

## 외부 모듈

```python
import math

print(math.ceil(5.1)) # x 이상의 수 중에서 가장 작은 정수
print(math.pi)
```

![image](https://user-images.githubusercontent.com/121333241/210562143-bf643907-7b41-4842-a293-9796534d144c.png)
