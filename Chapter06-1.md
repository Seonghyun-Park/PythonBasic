# Chapter06-1
- 파이썬 클래스
- OOP(객체 지향 프로그래밍), Self, 인스턴스 매소드, 인스턴스 변수

## 클래스 & 인스턴스 차이 이해
- 클래스 변수 : 직접 접근 가능, 공유
- 인스턴스 변수 : 객체마다 별도 존재
- 네임스페이스 : 객체를 인스턴스화 할 때 저장된 공간

## 예제 1

```python
class Dog1: # object 상속
    # 클래스 속성
    species = 'firstdog' # 클래스 변수
    
    # 초기화 / 인스턴스 속성
    def __init__(self, name, age):
        self.name = name
        self.age = age

# 클래스 정보
print(Dog1)
```

![image](https://user-images.githubusercontent.com/121333241/216541914-c4e29929-deac-4995-b9b6-af9bf9b4f783.png)

### 인스턴스화
```python
a = Dog1("mikky", 2)
b = Dog1("baby", 3)
```

### 비교
```python
print(a==b, id(a), id(b))
print()
```

![image](https://user-images.githubusercontent.com/121333241/216541947-308ad84c-2869-4b99-8ba8-8a4642401039.png)

### 네임스페이스
```python
print('dog1', a.__dict__)
print('dog2', b.__dict__)
print()
```

![image](https://user-images.githubusercontent.com/121333241/216541973-d912aaab-50c1-45e1-8b52-e30f2abe6363.png)

### 인스턴스 속성 확인
```python
print('{} is {} and {} is {}'.format(a.name, a.age, b.name, b.age))
print()

if a.species == 'firstdog':
    print('{0} is a {1}'.format(a.name, a.species))
    
print(Dog1.species) # 클래스로 바로 접근 가능
print(a.species) # 인스턴스화 된 변수로도 접근이 가능
print(b.species) 
print()
```

![image](https://user-images.githubusercontent.com/121333241/216542040-79d634c3-6b7c-44eb-8ffe-31c3eee9ee1c.png)

## 예제 2
- self 이해

```python
class SelfTest:
    def func1(): # 클래스 메소드
        print('func1 called')
    def func2(self): # self가 붙은 것은 인스턴스 메소드
        print(id(self))
        print('func2 called')
        
f = SelfTest()

# print(dir(f))
print(id(f))

# f.func1() # 예외
f.func2() # 인스턴스로 호출
SelfTest.func1() # 클래스로 직접 호출 - 매개 변수가 아무것도 없기 때문
# SelfTest.func2() # 예외
SelfTest.func2(f) # 인스턴스를 넘겨준다.
print()
```

![image](https://user-images.githubusercontent.com/121333241/216542110-938d9a8c-0556-4ad6-8199-17829989bb67.png)

## 예제 3
- 클래스 변수, 인스턴스 변수

```python
class Warehouse:
    # 클래스 변수
    stock_num = 0 # 재고
    
    def __init__(self, name):
        # 인스턴스 변수
        self.name = name
        Warehouse.stock_num += 1
        
    def __del__(self):
        Warehouse.stock_num -= 1
        
user1 = Warehouse('Lee')
user2 = Warehouse('Cho')
print(Warehouse.stock_num) # 인스턴스화가 2번 이루어졌다.

print(user1.name)
print(user2.name)
print(user1.__dict__)
print(user2.__dict__)
print('before :', Warehouse.__dict__)
print('>>>>>', user1.stock_num)

del user1
print('after :', Warehouse.__dict__)
print()
```

![image](https://user-images.githubusercontent.com/121333241/216542512-282733e5-ba19-43df-969d-08a0d25176c6.png)

## 예제 4

```python
class Dog: # object 상속
    # 클래스 속성
    species = 'firstdog' # 클래스 변수
    
    # 초기화 / 인스턴스 속성
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def info(self):
        return '{} is {} years old'.format(self.name, self.age)
    
    def speak(self, sound):
        return '{} says {}!'.format(self.name, sound)


# 인스턴스 생성    
c = Dog('july', 4)
d = Dog('Marry', 10)

# 메소드 호출
print(c.info())
print(d.info())
print(c.speak('Wal Wal'))
print(d.speak('Mung Mung'))
```

![image](https://user-images.githubusercontent.com/121333241/216542202-143b9de1-8900-4173-960f-2f8222e4ac0c.png)

### :arrow_forward: 하나의 클래스를 이용해서 여러가지 종류로 인스턴스화 시키고 각각의 인스턴스는 자기만의 정보를 가지고 있다.
