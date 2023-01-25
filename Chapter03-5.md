# Chapter03-5

- 파이썬 딕셔너리
- 범용적으로 가장 많이 사용
- 딕셔너리 자료형(순서 X, 키 중복 X, 수정 O, 삭제 O)

## 선언 { }

```python
a = {'name': 'Kim', 'phone' : '01033337777', 'birth' : '870514'} 
# { Key(어떤 자료형도 올 수 있다.) : 'Value(값)'}
b = {0: 'Hello Python'}
c = {'arr' : [1, 2, 3, 4]} # 키만 존재한다면 값에는 어떠한 자료형도 올 수 있다.
d = {
    'Name': 'Niceman',
    'City': 'Seoul',
    'Age': 33,
    'Grade': 'A',
    'Status': True
}
e = dict([
    ('Name', 'Niceman'),
    ('City', 'Seoul'),
    ('Age', 33),
    ('Grade', 'A'),
    ('Status', True)
])

f = dict(
    Name = 'Niceman',
    City = 'Seoul',
    Age = 33,
    Grade = 'A',
    Status = True
)

print('a -', type(a), a)
print('b -', type(b), b)
print('c -', type(c), c)
print('d -', type(d), d)
print('e -', type(e), e)
print('f -', type(f), f)
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572761-ab1c139e-7d0e-45fa-97f3-b36e50b8af58.png)

## 출력

```python
print('a -', a['name']) # 키가 존재하지 않으면 에러가 발생한다. 
print('a -', a.get('name1')) # 키가 존재하지 않으면 None으로 처리된다.
# get() 함수로 처리하는 것이 좀 더 안전하다.
print('b -', b[0])       
print('b -', b.get(0))
print('f -', f.get('City'))  
print('f -', f.get('Age')) 
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572858-51eddc33-26b2-4da1-a3e1-652d2a23c269.png)

## 딕셔너리 추가

```python
a['address'] = 'seoul'
print('a -', a)
a['rank'] = [1,2,3]
print('a -', a)
print()
```

![image](https://user-images.githubusercontent.com/121333241/214572927-9aca12fd-da0f-4ca2-88d2-bb9e4452eca2.png)

## 딕셔너리 길이 (키의 개수가 나온다.)

```python
print('a -', len(a))
print('b -', len(b))
print('c -', len(c))
print('f -', len(f))     
print()
```

![image](https://user-images.githubusercontent.com/121333241/214573036-8751d6d6-aa00-4ad8-ba82-d95f6e697b6e.png)

## dict_keys, dict_values, dict_items 

- 반복문(_iter_)에서 사용 가능

## dict_keys (key 값들만 가져온다.)

```python
print('a -', a.keys())            
print('b -', b.keys())
print('c -', c.keys())
print('f -', f.keys())    

print('a -', list(a.keys()))            
print('b -', list(b.keys()))
print()
```

![image](https://user-images.githubusercontent.com/121333241/214573107-c5bf4978-2c63-47eb-8ae3-2f476d0e4c2e.png)

## dict_values (value 값들만 가져온다.)

```python
print('a -', a.values())            
print('b -', b.values())
print('c -', c.values())

print('a -', list(a.values()))            
print('b -', list(b.values()))
print()
```

![image](https://user-images.githubusercontent.com/121333241/214573173-d46f0275-552b-4789-ba1c-50c07f3a72aa.png)

## dict_items (키와 value를 모두 가져온다.)

```python
print('a -', a.items())            
print('b -', b.items())
print('c -', c.items())

print('a -', list(a.items()))            
print('b -', list(b.items()))
print()
```

![image](https://user-images.githubusercontent.com/121333241/214573481-d9911d7e-b4d2-42db-aa69-9b66a01c08e1.png)

## pop 연산자

```python
print('a -', a.pop('name'))
print('a -', a)
print('c -', c.pop('arr'))
print('c -', c)
print()

print('f -', f.popitem()) # 아무거나 하나를 임의로 꺼낸다.
print('f -', f)
print('f -', f.popitem()) # 아무거나 하나를 임의로 꺼낸다.
print('f -', f)
print('f -', f.popitem()) # 아무거나 하나를 임의로 꺼낸다.
print('f -', f)
print()
```

![image](https://user-images.githubusercontent.com/121333241/214573605-5af58f72-7996-45ad-9da8-1d2f8a05e616.png)

## in 연산자 

```python
print('a -', 'birth' in a) # a에 'birth'라는 단어가 있으면 True, 없으면 False
print('d -', 'City' in d)
```

![image](https://user-images.githubusercontent.com/121333241/214573690-c296db9a-e6df-47fc-8aae-c6cc8c1a95b4.png)

## 수정

```python
a['test'] = 'test_dict'
print('a -', a)

a['address'] = 'dj'
print('a -', a)

a.update(birth = '910904')
print('a -', a)

temp = {'address':'Busan'}

a.update(temp)
print('a -', a)
```

![image](https://user-images.githubusercontent.com/121333241/214573761-0ebe5545-d7e1-4c65-b442-dcddddb4983a.png)
