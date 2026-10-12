# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
    The game loaded on "Normal" difficulty, but there was a UI inconsistency where the "Attempts allowed" on the left was 8, but the game
    showed "Attempts left: 7" in the main section. All the attepts correctly decrement if you guess wrong and hints do display if you want
    them too. If you guess right (using the "Developer Debug Info" dropdown), the congratulations screen appears with your score.

- List at least two concrete bugs you noticed at the start  
    1. The hints are displayed backwards (too low prompts a "lower" hint, and vice-versa).

    2. Inputting anything other than a number in the guess box breaks the logic and causes you to go into negative attempts.
      It correctly displays that the input is not a number, however.

    3. The first time playing on any difficulty, the "Attempts allowed" on the left side does not match the "Attempts left" section on
      the game itself. (Ex: On Easy, "Attempts allowed: 6," "Attempts left: 5"). Following games do correctly display the two.

    4. Secrets are not bounded to the limits set by their respective difficulty. (Ex: On Easy, the secret can be greater than 20).

    5. When a player's score is being calculated, too high of a guess could award points while a correct guess on the first attempt 
      will be based off attempt count and not guess.
    
    6. Game history is preserved between games.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

|       Input       |    Expected Behavior  |      Actual Behavior      | Console Output / Error |
|-------------------|-----------------------|---------------------------|------------------------|
| Guess >/< Secret  | "Too High / Low" Hint |    Opposite hint shown    |          None          |
|    Not a Number   |   Decrease Attempts   | Creates negative attempts |          None          |
|   Initial State   |   Attempts Accurate   |     Counter off by one    |          None          |
|      New Game     |  Secret within range  |     Secret out of range   |          None          |
| Score Calculation |  Correctly award and  |     Score is based off    |          None          |
|                   |    penalize guesses   |  attempts and not guesses |                        |
|    Game History   |  Refresh game history | Game data doesn't refresh |          None          |
--------------------------------------------------------------------------------------------------

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
    I used ChatGPT for this project. 

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
    The AI suggested that I reset my game history to an empty array whenever there was a new game. Before, every new game would save the 
    guesses of the previous one. The reason I accepted this suggestion was because I knew what the history error was, and the suggestion 
    I was given made sense considering what type of data the history was. When I applied the suggestion, the history was now correctly reset whenever a new game was played.

- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.
    The AI tried suggesting implementing a function in app.py. The reason I rejected this was because I was supposed to separate game logic
    from UI. The function itself was also unhelpful when trying to fix the bugs I had mentioned in the table and response above. Additionally
    I felt like the function complicated the game logic too much when it cae to the simple error it was trying to fix.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
    I decided whether a bug was really fixed by playing multiple rounds of my game with different inputs every time to see if the correct
    logic was not simply a one-off fix. Once I got the intended results, I double-checked my code to verify the correct fix and tested it
    one more time. When the correct behavior persisted, I considered the bug fixed.

- Describe at least one test you ran (manual or using pytest) and what it showed you about your code.
    I decided to test user input. The reason I tested this was because it was the biggest issue when it came to the game's logic. A 
    non-numerical input would break the game in unintended ways and was the source of a lot of the other bugs I saw. What this test 
    showed me about my code was that whenever I accept user input, I need to make sure that my code can handle all types of data and
    parse them correctly.

- Did AI help you design or understand any tests? How?
    AI helped me refine tests for the logic I rewrote. When using it, it helped me catch some edge-cases that I had missed on my first
    version of a test.

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
    Streamlit reruns mean that whenever you interact with something on the page, like clicking a button or changing a setting, the app runs its code again from the top. Session state is like the app’s memory, storing information such as your score, secret number, and attempts so that your progress is not lost during those reruns.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
    A habit I developed during this project that I want to reuse in the future is my frequent Git committing. I found that frequent 
    commits, no matter how small, helped me organize my code and helped me understand what it is that I did between commits. It also
    helped me revert some changes that I was unhappy with. Because my commits were so frequent, I did not lose much progress.

- What is one thing you would do differently next time you work with AI on a coding task?
    I would not do anything differently next time I work with AI on a coding task. I feel like I got a better understanding of programming
    by attempting the entire assignnment on my own, then using AI to verify if the things I did were correct. I feel like the balance of
    being able to complete the assignments on my own, paired with external validation makes me a stronger programmer.

- In one or two sentences, describe how this project changed the way you think about AI generated code.
    This project did not change the way I think about AI generated code. Most of the times I checked my work with AI, the code provided
    didn't change my core logic or functionality. A lot of the time, the code was either wrong, not applicable, or too verbose.