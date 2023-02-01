# Chapter05-1
- 파이썬 함수 및 중요성
- 파이썬 함수식 및 람다(Lambda)

## 함수 정의 방법

```python
# def function_name(parameter(인수)):
#     code
```

## 예제 1

```python
def first_func(w): # 함수 선언
    print("Hello, ", w)
    
word = "Goodboy"
first_func(word) # 함수 출력
print()
```

![image](https://user-images.githubusercontent.com/121333241/215991685-6fbfdd7b-f6de-4fa3-9868-1f843e7dffb2.png)

## 예제 2

```python
def return_func(w1):
    value = "Hello, " + str(w1)
    return value

x = return_func('Goodboy2')
print(x)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215991731-77dbda95-3c27-4dbb-a1d5-d541ebb9eea3.png)

## 다중 반환

```python
def func_mul(x):
    y1 = x * 10
    y2 = x * 20
    y3 = x * 30
    return y1, y2, y3 # 동시에 반환

x, y, z = func_mul(10)
print(x, y, z)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215991762-839dfe9d-b0a3-401b-80a6-3d6bc23a8d53.png)

## 튜플 리턴 

```python
def func_mul2(x):
    y1 = x * 10
    y2 = x * 20
    y3 = x * 30
    return (y1, y2, y3) # 튜플로 반환

q = func_mul2(20)
print(type(q), q, list(q)) # 튜플 타입, 팩킹되어서 튜플 형태로 출력된다.
print()
```

![image](https://user-images.githubusercontent.com/121333241/215991811-d076d869-be80-4a88-aab3-8bb3fdfb1300.png)

## 리스트 리턴 

```python
def func_mul3(x):
    y1 = x * 10
    y2 = x * 20
    y3 = x * 30
    return [y1, y2, y3] # 리스트로 반환

p = func_mul3(30)
print(type(p), p, set(p))
print()
```

![image](https://user-images.githubusercontent.com/121333241/215991872-1151b18f-3351-4343-aa52-49516223cdfa.png)

## 딕셔너리 리턴 

```python
def func_mul4(x):
    y1 = x * 10
    y2 = x * 20
    y3 = x * 30
    return {'v1': y1, 'v2': y2, 'v3': y3} # 딕셔너리로 반환

d = func_mul4(40)
print(type(d), d, d.get('v2'), d.items(), d.keys())
```

![image](https://user-images.githubusercontent.com/121333241/215993311-0511bc6a-fd14-44e3-a9f9-844e01b4d974.png) 
![image](https://user-images.githubusercontent.com/121333241/215993562-05227a06-6e7d-4089-b972-be675675a55a.png)


## *args(언팩킹)
- ' * ' 는 튜플 형태를 매개변수로 넘길 때 사용한다.
- 변수를 하나만 설정하여도 함수 내에서 풀어서 각각의 튜플 형태로 간주한다.

```python
def args_func(*args): # 매개변수 명 자유
    for i, v in enumerate(args):
        print('Result : {}'.format(i), v)
    print('-----')
     
args_func('Lee') # 튜플 형태로 매개변수 사용
args_func('Lee', 'Park')
args_func('Lee', 'Park', 'Kim')
print()
```

![image](https://user-images.githubusercontent.com/121333241/215992018-7741b5bb-bbfc-4b50-a6fe-0a2fb003125d.png)

## **kwargs(언팩킹)
- ** 는 딕셔너리 형태, key와 value인 것을 매개변수로 넘길 때 사용한다.

```python
def kwargs_func(**kwargs): # 매개변수 명 자유
    for v in kwargs.keys():
        print("{}".format(v), kwargs[v])
    print('-----')
    
kwargs_func(name1 = 'Lee') # 딕셔너리 형태(key와 value 형태)로 매개변수 사용 
kwargs_func(name1 = 'Lee', name2 = 'Park')
kwargs_func(name1 = 'Lee', name2 = 'Park', name3 = 'Cho')
print()
```

![image](https://user-images.githubusercontent.com/121333241/215992089-62b49690-2fea-4dc8-910b-0f9add51f03d.png)

## 전체 혼합

```python
def example(args_1, args_2, *args, **kwargs):
    print(args_1, args_2, args, kwargs)
    
example(10, 20, 'Lee', 'Kim', 'Park', 'Cho', age1 = 20, age2 = 30, age3 = 40)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215992143-3301161b-cb39-4c8b-8ffc-7c92843adaa8.png)

- 10과 20은 args_1과 args_2에 할당한 후 
- -> 그 이후에 하나의 변수로 설정된 것은 *가 하나만 있는 *args에 할당되어 튜플 형태로 출력되고
- -> 그 다음에 키와 밸류의 형태로 선언된 것은 **(별표 2개)로 이루어진 **kwargs에 할당되어 딕셔너리 형태로 출력된다.

## 중첩 함수
- 함수 안에 함수가 있는 형태

```python
def nested_func(num):        # 1
    def func_in_func(num):   # 4
        print(num)           # 5
    print("In func")         # 2
    func_in_func(num + 100)  # 3
    
nested_func(100)
# func_in_func(100) -> 실행 불가
print()
```

![image](https://user-images.githubusercontent.com/121333241/215992216-bac5b759-d004-48ef-a37b-cf38ca458e9f.png)

## 람다식 예제
- 메모리 절약, 가독성 향상, 코드 간결
- 함수는 객체 생성 -> 리소스(메모리) 할당
- 람다는 즉시 실행 함수 (Heap 초기화) -> 메모리 초기화
- 남발 시 가독성이 오히려 감소

```python
def mul_func(x, y):
     return x * y

 lambda x, y: x * y # 함수의 이름이 없다.
# x, y는 인수를 받는 부분, : x * y 는 리턴되는 부분
```

## 일반적인 함수 -> 할당

```python
def mul_func(x, y):
    return x * y

print(mul_func(10, 50))

mul_func_var = mul_func
print(mul_func_var(20, 50))
print()
```

![image](https://user-images.githubusercontent.com/121333241/215992289-9bcbf16d-02de-481a-b437-21a3af3b39d6.png)

## 람다 함수 -> 할당

```python
lambda_mul_func = lambda x,y: x * y
print(lambda_mul_func(50, 50))

def func_final(x, y, func):
    print(x * y * func(100, 100))
   
func_final(10, 20, lambda x, y: x * y)
print()
```

![image](https://user-images.githubusercontent.com/121333241/215992419-484f898b-b331-4a24-b20a-89eb5b66ecf5.png)

## Hint

```python
def tot_length1(word: str, num: int) -> int:
    return len(word) * num

print('hint exam1 : ', tot_length1("i love you", 10))

def tot_length2(word: str, num: int) -> None:
    print('hint exam2 : ', len(word) * num)

tot_length2("niceman", 10)
```

![image](https://user-images.githubusercontent.com/121333241/215992520-d8184f5a-76f8-406b-afe7-891acc4c7716.png)

### 프로그래밍 패러다임
---

### 명령형 프로그래밍: 무엇(What)을 할 것인지 나타내기보다 어떻게(How) 할 건지를 설명하는 방식

- 절차지향 프로그래밍: 수행되어야 할 순차적인 처리 과정을 포함하는 방식 (C, C++)
- 객체지향 프로그래밍: 객체들의 집합으로 프로그램의 상호작용을 표현 (C++, Java, C#)

### 선언형 프로그래밍: 어떻게 할건지(How)를 나타내기보다 무엇(What)을 할 건지를 설명하는 방식

- 함수형 프로그래밍: 순수 함수를 조합하고 소프트웨어를 만드는 방식 (클로저, 하스켈, 리스프)

