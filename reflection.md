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

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

|       Input       |    Expected Behavior  |      Actual Behavior      | Console Output / Error |
|-------------------|-----------------------|---------------------------|------------------------|
| Guess >/< Secret  | "Too High / Low" Hint |    Opposite hint shown    |          None          |
|    Not a Number   |   Decrease Attempts   | Creates negative attempts |          None          |
|   Initial State   |   Attempts Accurate   |     Counter off by one    |          None          |
|      New Game     |  Secret within range  |     Secret out of range   |          None          |
--------------------------------------------------------------------------------------------------

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
