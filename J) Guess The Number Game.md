# Chapter 10: Guess The Number Game

<br>
<br>

### Rules:
- The computer secretly picks a random number between 1 and 100. You don’t know what it is — your job is to figure it out by guessing.
- You type in a number you think might be correct — say, 45.
- It tells you if your guess is:
    - **Too low** → meaning the secret number is higher than what you guessed.
    - **Too high** → meaning the secret number is lower than what you guessed.
    - **Correct** → 🎉 You win!
- Based on the feedback, you adjust your next guess:
    -  If it said “too low,” you try a higher number.
    -  If it said “too high,” you try a lower number.
- This continues until you guess the number correctly. And also it will show you the number of attempts.

### Now Let's Code the Game:
```bash
import random
cor_num = random.randint(1,100)

num_attemp = 1
guess = int(input(f"{num_attemp} |  Guess a number(1-100):"))

while guess!=cor_num:
    if guess<cor_num:
        num_attemp+=1
        guess = int(input(f"{num_attemp} |  Too low! Guess higher:"))        
    elif guess>cor_num:
        num_attemp+=1
        guess = int(input(f"{num_attemp} |  Too high! Guess lower:"))
                
if guess==cor_num:
    print("")
    print(f"🎉 You have guessed correctly in {num_attemp} attempts!")
```
