import random

words = {
    "apple": "사과",
    "book": "책",
    "computer": "컴퓨터",
    "water": "물",
    "school": "학교"
}

score = 0
word_list = list(words.items())
random.shuffle(word_list)

for eng, kor in word_list:
    answer = input(f"{eng}의 뜻은? ")

    if answer == kor:
        print("정답!\n")
        score += 1
    else:
        print(f"오답! 정답은 {kor}\n")

print(f"총 점수: {score}/{len(words)}")
