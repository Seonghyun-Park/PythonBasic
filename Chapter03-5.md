# Chapter03-5
# 파이썬 딕셔너리
# 범용적으로 가장 많이 사용
# 딕셔너리 자료형(순서 X, 키 중복 X, 수정 O, 삭제 O)

# 선언 { }
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

# 출력
print('a -', a['name']) # 키가 존재하지 않으면 에러가 발생한다. 
print('a -', a.get('name1')) # 키가 존재하지 않으면 None으로 처리된다.
# get() 함수로 처리하는 것이 좀 더 안전하다.
print('b -', b[0])       
print('b -', b.get(0))
print('f -', f.get('City'))  
print('f -', f.get('Age')) 
print()

# 딕셔너리 추가
a['address'] = 'seoul'
print('a -', a)
a['rank'] = [1,2,3]
print('a -', a)
print()

# 딕셔너리 길이 (키의 개수가 나온다.)
print('a -', len(a))
print('b -', len(b))
print('c -', len(c))
print('f -', len(f))     
print()

# dict_keys, dict_values, dict_items : 반복문(_iter_)에서 사용 가능

# dict_keys (key 값들만 가져온다.)
print('a -', a.keys())            
print('b -', b.keys())
print('c -', c.keys())
print('f -', f.keys())    

print('a -', list(a.keys()))            
print('b -', list(b.keys()))

print()

# dict_values (value 값들만 가져온다.)
print('a -', a.values())            
print('b -', b.values())
print('c -', c.values())

print('a -', list(a.values()))            
print('b -', list(b.values()))

print()

# dict_items (키와 value를 모두 가져온다.)
print('a -', a.items())            
print('b -', b.items())
print('c -', c.items())

print('a -', list(a.items()))            
print('b -', list(b.items()))

print()

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

# in 연산자 
print('a -', 'birth' in a) # a에 'birth'라는 단어가 있으면 True, 없으면 False
print('d -', 'City' in d)

# 수정
a['test'] = 'test_dict'
print('a -', a)

a['address'] = 'dj'
print('a -', a)

a.update(birth = '910904')
print('a -', a)

temp = {'address':'Busan'}

a.update(temp)
print('a -', a)