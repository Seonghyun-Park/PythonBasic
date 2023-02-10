# Chapter10-1
- Hangman(행맨) 미니 게임 제작(1)
- 기본 프로그램 제작 및 테스트

```python
import time

# 처음 인사
name = input("What is your name? ") # 이름 입력

print('Hi, ' + name, "Time to play hangman game!")

print()

time.sleep(1) # 1초 쉰다.

print("Start Loading...")
print()
time.sleep(0.5)

# 정답 단어
word = "secret"

# 추측 단어
guesses = ''

# 기회
turns = 10

# 핵심 While Loop
# 찬스 카운트가 남아있을 경우
while turns > 0:
    # 실패 횟수
    failed = 0
    # print(guesses) # 단어 누적 확인
    
    # 정답 단어 반복
    for char in word:
        # 정답 단어 내에 추측 문자가 포함되어 있는 경우
        if char in guesses: # 처음 실행할 때는 guesses가 공백이기 때문에 실행되지 않는다.
            # 추측 단어 출력
            print(char, end=' ') # 맞은 단어 출력
        else:
            # 틀린 경우 대시로 처리
            print("_", end=' ') 
            failed += 1 # 한 글자도 못 맞춘 상태이기 때문에 글자 수 만큼 밑줄이 출력된다.
    # 단어 추측이 성공한 경우
    if failed == 0:
        print()
        print()
        print('Congratulations! The Guesses is correct.')
        # while 구문 중단
        break
    print()
    
    # 추측 단어 문자 단위 입력
    print()
    guess = input("guess a character: ")
    
    # 단어 더하기
    guesses += guess # 단어 누적
    
    # 정답 단어에 추측한 문자가 포함되어 있지 않으면
    if guess not in word:
        # 기회 횟수 감소
        turns -= 1
        # 오류 메시지
        print("Oops! Wrong")
        # 남은 기회 출력
        print("You have ", turns, "more guesses!")
        
        if turns == 0:
            # 실패 메시지
            print("You hangman game failed. Bye!")
```

![image](https://user-images.githubusercontent.com/121333241/218035004-c3e602d3-5f23-479f-83a4-e61860aa8f23.png)

![image](https://user-images.githubusercontent.com/121333241/218035144-ddd090d2-0833-453b-bd71-34f3d9841cd6.png)
