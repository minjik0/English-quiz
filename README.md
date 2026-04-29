import random

sentences = [
    {"eng": "Hi! I'm a caterpillar.", "kor": "안녕! 나는 애벌레야."},
    {"eng": "I come out of an egg.", "kor": "나는 알에서 나와."},
    {"eng": "I like to eat fresh leaves.", "kor": "나는 신선한 잎을 먹는 걸 좋아해."},
    {"eng": "I crawl between leaves.", "kor": "나는 잎 사이를 기어 다녀."},
    {"eng": "I eat the leaves all day.", "kor": "나는 하루 종일 잎을 먹어."},
    {"eng": "Now I become a big caterpillar.", "kor": "이제 나는 큰 애벌레가 되었어."},
    {"eng": "It's time to have a long sleep.", "kor": "이제 긴 잠을 잘 시간이야."},
    {"eng": "I hang from the branch and make a cocoon.", "kor": "나는 나뭇가지에 매달려 고치를 만들어요."},
    {"eng": "My body changes while I sleep in the cocoon.", "kor": "나는 고치에서 자는 동안 몸이 변해."},
    {"eng": "After a few weeks, I'm ready to come out of the cocoon.", "kor": "몇 주 후, 나는 고치에서 나올 준비가 돼."},
    {"eng": "Look at me!", "kor": "나를 봐!"},
    {"eng": "Now I'm a butterfly.", "kor": "이제 나는 나비야."},
    {"eng": "I can fly!", "kor": "나는 날 수 있어!"}
]

score = 0

print("🧠 영어 문장 배열 퀴즈 (스토리 순서)\n")

for i, item in enumerate(sentences, 1):
    eng = item["eng"]
    kor = item["kor"]

    print(f"\n📖 문제 {i}/{len(sentences)}")  # 🔥 여기 추가됨
    print("🇰🇷 해석:", kor)

    words = eng.replace("'", " '").replace("!", " !").replace(".", " .").split()

    import random
    random.shuffle(words)

    print("🔀 단어:", " / ".join(words))

    user = input("올바른 영어 문장을 입력하세요: ")

    if user.strip().lower() == eng.lower():
        print("✅ 정답!\n")
        score += 1
    else:
        print("❌ 오답!")
        print("정답:", eng, "\n")

print(f"🎯 최종 점수: {score}/{len(sentences)}")
