# Chapter06-3
- 파이썬 패키지
- 패키지 작성 및 사용법
- 파이썬은 패키지로 분할된 개별적인 모듈로 구성
-  _ _ _init_ _ _.py : Python 3.3 부터는 없어도 패키지로 인식 -> 단, 하위 호환을 위해 작성 추천
- -> _ _ _all_ _ _ = ['module1'] : 선언이 되어 있어야 moulde1에 접근할 수 있다.
- 상대경로 : ..(부모 디렉토리),  .(현재 디렉토리) -> 모듈 내부에서만 사용

---
### sub.sub1.module1.py

```python
import sys
import inspect
# from ..sub1 import module1

# module1.py
def mod1_test1():
	print ("Module1 -> Test1")
	print("Path : ", inspect.getfile(inspect.currentframe()))

def mod1_test2():
	print ("Module1 -> Test2")
	print("Path : ", inspect.getfile(inspect.currentframe()))
```

### _ _ _init_ _ _.py

```python
__all__ = ['module1']
```
 
## 예제 1

```python
import sub.sub1.module1 # 같은 경로에 있을 때는 import로 찾아온다.
# sub 패키지 하위에 sub1 패키지 하위에 module1
# import는 패키지의 풀 네임을 다 적어줘야 한다.
import sub.sub2.module2

# 사용
sub.sub1.module1.mod1_test1()
sub.sub1.module1.mod1_test2()

sub.sub2.module2.mod2_test1()
sub.sub2.module2.mod2_test2()

print()
print()
print()
```

![image](https://user-images.githubusercontent.com/121333241/216821718-0673c082-59a4-43f4-ae04-6dbfe334d6d2.png)

## 예제 2
- from절을 사용하는 것이 코드를 작성할 때 편하다.

```python
from sub.sub1 import module1 
from sub.sub2 import module2 as m2 # alias
# from절을 통해서 선언을 하면 호출을 할 때 간단히 사용할 수 있다.

module1.mod1_test1()
module1.mod1_test2()

m2.mod2_test1()
m2.mod2_test2()

print()
print()
print()
```

![image](https://user-images.githubusercontent.com/121333241/216821737-baaa8eed-3a96-4866-b350-646c20afd695.png)

## 예제 3
- 모든 파일에 접근할 것이 아니라면 내가 필요로 하는 것만 사용하는 것이 좋다.

```python
from sub.sub1 import * # 별표를 import하면 하위에 있는 모든 파일 이름으로 접근할 수 있다.
from sub.sub2 import *

module1.mod1_test1()
module1.mod1_test2()

module2.mod2_test1()
module2.mod2_test2()

print()
print()
print()
```

![image](https://user-images.githubusercontent.com/121333241/216821766-ad03f1d1-d8c3-4c5f-b56a-f5c51807feac.png)

## 예제 4

```python
from sub.sub3 import module3 as m3

m3.mod3_test1()
m3.mod3_test2()
```

![image](https://user-images.githubusercontent.com/121333241/216821781-19866ba1-14e4-449c-b63a-357cd09e0187.png)
