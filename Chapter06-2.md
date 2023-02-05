# Chapter06-2
- 파이썬 모듈
- Module : 함수, 변수, 클래스 등 파이썬 구성 요소 등을 모아놓은 파일

```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    return x / y

def power(x, y):
    return x ** y
```

```python
# print('-' * 15)
# print('called inner!')
# print(add(5, 5))
# print(subtract(15, 5))
# print(multiply(5, 5))
# print(divide(10, 2))
# print(power(5, 3))
# print('-' * 15)
```

## __name__ 사용
- 현재(main) 파일에서 실행할 때만 실행되고 다른 파일에서 실행하면 실행되지 않는다.
- import할 때 불필요한 출력을 막기 위해서 
- 이해를 돕기 위한 테스트 부분

```python
if __name__ == "__main__": 
    print('-' * 15)
    print('called inner!')
    print(add(5, 5))
    print(subtract(15, 5))
    print(multiply(5, 5))
    print(divide(10, 2))
    print(power(5, 3))
    print('-' * 15)
```

![image](https://user-images.githubusercontent.com/121333241/216807778-69e91b64-3ce2-439f-bcde-fe4f87fab70c.png)

## 모듈 사용 실습

#### module_test.py

```python
import sys

print(sys.path) # 파이썬 엔진이 나오는 경로를 토대로 찾는다.

print(type(sys.path))

# # 모듈 경로 삽입
# sys.path.append('C:/math') # append를 통해서 확장
# print(sys.path)

# import test_module

# # 모듈 사용
# print(test_module.power(10, 3))

import Chapter06_02
print(Chapter06_02.add(10, 1000))
```

![image](https://user-images.githubusercontent.com/121333241/216807809-b15878fc-886f-4bd0-88eb-e145596cea4f.png)
