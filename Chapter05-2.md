# Chapter05-2
- 파이썬 사용자 입력
- Input 사용법
- 기본 타입(str)

## 예제 1

```python
name = input("Enter Your Name: ")
grade = input("Enter Your Grade: ")
company = input("Enter Your Company name: ")

print(name, grade, company)
```

![image](https://user-images.githubusercontent.com/121333241/216244119-c2ae2be8-3961-45bc-b431-c523b4fa5021.png)

## 예제 2

```python
number = input("Enter number : ")
name = input("Enter name : ")

print("type of number", type(number), number * 3) 
print("type of name", type(name))
```

![image](https://user-images.githubusercontent.com/121333241/216244186-fe39a522-2eab-47a5-9bc0-617db7c58a63.png)

- -> input은 기본 타입이 str형이기 때문에 정수를 입력하여도 문자로 인식하여 5가 3번 반복된다.

## 예제 3(계산)

```python
first_number = int(input("Enter number1 : ")) # 형변환을 해주어야 숫자로 인식한다.
second_number = int(input("Enter number2 : "))

total = first_number + second_number
print("first_number + second_number : ", total)
```

![image](https://user-images.githubusercontent.com/121333241/216244234-bcac44aa-9526-40e4-9bc1-319dd40f9857.png)

## 예제 4

```python
float_number = float(input("Enter a float number : "))

print("input float : ", float_number)
print("input type : ", type(float_number))
```

![image](https://user-images.githubusercontent.com/121333241/216244386-86fb6209-78d1-428a-9e9c-7260f05bf266.png)

## 예제 5

```python
print("FirstName - {0}, LastName - {1}".format(input("Enter first name : "), input("Enter second name : ")))                                       
```

![image](https://user-images.githubusercontent.com/121333241/216244422-fd48d1ad-8d2c-4b05-a0f2-1ed6ec4bf3ce.png)
