# Chapter03-2
- 파이썬 기초 자료형
- 문자형 (중요!)

## 문자열 생성

```python
str1 = "I am Python"
str2 = 'Python'
str3 = """How are you?"""
str4 = '''Thank you!'''

print(type(str1), type(str2), type(str3), type(str4))
print(len(str1), len(str2), len(str3), len(str4)) # 공백을 포함한 문자열의 길이
print()
```

## 빈 문자열

```python
str1_t1 = ''
str2_t2 = str()

print(type(str1_t1), len(str1_t1))
print(type(str2_t2), len(str2_t2))
print()
```

# 이스케이프 문자 사용

```python
"""
참고 : Escape 코드

\n : 개행
\t : 탭
\\ : 문자
\' : 문자
\" : 문자
\000 : 널 문자
...
"""
```
### I'm Boy

```python
print("I'm Boy")
print('I\'m Boy') # \ 뒤의 문자가 그대로 출력
print()

print('a \t b') # tab칸 만큼 띄운다.
print('a \n b') # 줄바꿈
print('a \"\" b') # "" 출력
print()

escape_str1 = "Do you have a \"retro games\"?"
print(escape_str1)
escape_str2 = 'What\'s on TV?'
print(escape_str2)
print()
```

## 탭, 줄바꿈

```python
t_s1 = "Click \t Start!"
t_s2 = "New Line \n Check!"

print(t_s1)
print(t_s2)
print()
```

## Raw String (\(역슬래시)를 신경쓰지 않고 그대로 표시)

```python
raw_s = r'D:\python\test' # r'' 형태로 사용
print(raw_s)
print()
```

## 멀티라인 입력

- 역슬래시 사용

```python
multi_str = \
'''
String
Multi line
Test
'''
print(multi_str)
```

## 문자열 연산

```python
str_o1 = "python"
str_o2 = "Apple"
str_o3 = "How are you doing"
str_04 = "Seoul Daejeon Busan Jinju"

print(str_o1 * 3) # 3번 반복
print(str_o1 + str_o2) # 문자열 자체를 더해서 출력
print('y' in str_o1) # str_o1에 'y'라는 단어가 있나요?
print('n' in str_o1)
print('P' not in str_o2) # str_o2에 'P'라는 단어가 없나요?
print()
```

## 문자열 형 변환

```python
print(str(66), type(str(66))) # 문자 66을 의미
print(str(10.1))
print(str(True), type(str(True)))
print()
```

## 문자열 함수(upper, isalnum, startswith, count, endwith, isalpha...)

```python
print("Capitalize: ", str_o1.capitalize()) # 첫 글자를 대문자로 변경
print("endwith?: ", str_o2.endswith("e")) # 마지막 문자가 무엇으로 끝나는지 확인
print("replace: ", str_o1.replace("thon", " Good")) # 앞 부분을 찾아서 뒷 부분으로 바꾼다.
print("sorted: ", sorted(str_o1)) # 정렬 함수
print("split: ", str_04.split(' ')) # 특정 단어를 분리
print()
```

## 반복(시퀀스: 순서가 있는 배열 형태)

```python
im_str = "Good Boy!"
print(dir(im_str)) # __iter__
```

### 출력

```python
for i in im_str:
    print(i)
print()
```    
    
## 슬라이싱    

```python
str_sl = "Nice Python"
```

## 슬라이싱 연습

```python
print(str_sl[0:3]) # 0번 인덱스부터 2(3-1)번 인덱스까지 출력 (0, 1, 2)
print(str_sl[5:]) # 5번 인덱스부터 마지막까지 출력 [5:11]
print(str_sl[:len(str_sl)]) # str_sl[:11] - 처음부터 전체길이만큼 출력(11-1)
print(str_sl[:len(str_sl)-1]) # str_sl[:10] 9번(10-1)인덱스까지 출력
print(str_sl[1:9:2]) # 1번부터 8번까지 2칸씩 뛰면서 출력
print()
print(str_sl[-5:]) # '-'부호(음수)는 오른쪽에서부터 읽는다. (오른쪽 제일 끝이 -1)
print(str_sl[1:-2]) # 1번부터 -3(-2-1)번까지 출력 
print(str_sl[::2]) # 처음부터 끝까지 2칸씩 출력
print(str_sl[::-1]) # 오른쪽에서부터 출력(역으로 출력)
print()
```

## 아스키 코드 (또는 유니코드)

```python
a = 'z'

print(ord(a)) # z의 아스키코드 값
print(chr(122)) # 아스키코드 122의 문자
```