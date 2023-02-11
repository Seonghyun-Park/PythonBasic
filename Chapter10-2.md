# Chapter10-2
- Hangman(행맨) 미니 게임 제작(2)
- 프로그램 완성 및 최종 테스트

```python
import time
import csv
import random
import winsound # 사운드 처리

# 처음 인사
name = input("What is your name? ")

print('Hi, ' + name, "Time to play hangman game!")

print()

time.sleep(1)

print("Start Loading...")
print()
time.sleep(0.5)

# csv 단어 리스트
words = []

# 문제 csv 파일 로드
with open('./resource/word_list.csv', 'r') as f:
    reader = csv.reader(f)
    # Header Skip
    next(reader)
    for c in reader:
        words.append(c)
        
# 리스트 섞기
random.shuffle(words)

q = random.choice(words)

# 정답 단어
word = q[0].strip()

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
        # 성공 사운드
        winsound.PlaySound('./sound/good.wav', winsound.SND_FILENAME)
        print('Congratulations! The Guesses is correct.')
        # while 구문 중단
        break
    print()
    
    # 추측 단어 문자 단위 입력
    print()
    print('Hint : {}'.format(q[1].strip()))
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
            # 실패 사운드
            winsound.PlaySound('./sound/bad.wav', winsound.SND_FILENAME)
            # 실패 메시지
            print("You hangman game failed. Bye!")
```

![image](https://user-images.githubusercontent.com/121333241/218035555-877c9390-720c-4362-bcec-723d9517d0af.png)

![image](https://user-images.githubusercontent.com/121333241/218035704-ff8db6d2-a29a-4386-8916-9480c902071f.png)
