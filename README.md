# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
- [ ] Detail which bugs you found.
- [ ] Explain what fixes you applied.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. A random number is generated within the range of the chosen difficulty. A certain amount of attempts is also allocated.
2. The user enters a guess above the secret number and is hinted to go lower. Vice-versa for a guess below the secret number.
3. The game does not accept non-numerical or decimal / fractional inputs.
4. The score is updated correctly after every guess.
5. The game ends when the correct number is guessed or if attempts run out.
6. A new game can be played and correctly resets all logic and guess history.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
============================================================ test session starts ============================================================
platform win32 -- Python 3.14.0, pytest-9.1.1, pluggy-1.6.0 -- C:\Python314\python.exe
cachedir: .pytest_cache
rootdir: C:\Users\chris\OneDrive\Desktop\AI-110_Project_1
plugins: anyio-4.13.0
collected 22 items                                                                                                                           

tests/test_game_logic.py::test_winning_guess PASSED                                                                                    [  4%]
tests/test_game_logic.py::test_guess_too_high PASSED                                                                                   [  9%]
tests/test_game_logic.py::test_guess_too_low PASSED                                                                                    [ 13%]
tests/test_game_logic.py::test_invalid_guess_is_rejected[] PASSED                                                                      [ 18%]
tests/test_game_logic.py::test_invalid_guess_is_rejected[   ] PASSED                                                                   [ 22%]
tests/test_game_logic.py::test_invalid_guess_is_rejected[hello] PASSED                                                                 [ 27%]
tests/test_game_logic.py::test_invalid_guess_is_rejected[3.5] PASSED                                                                   [ 31%]
tests/test_game_logic.py::test_invalid_guess_is_rejected[None] PASSED                                                                  [ 36%]
tests/test_game_logic.py::test_valid_integer_input_is_parsed[50-50] PASSED                                                             [ 40%]
tests/test_game_logic.py::test_valid_integer_input_is_parsed[ 25 -25] PASSED                                                           [ 45%]
tests/test_game_logic.py::test_valid_integer_input_is_parsed[0-0] PASSED                                                               [ 50%]
tests/test_game_logic.py::test_valid_integer_input_is_parsed[-5--5] PASSED                                                             [ 54%]
tests/test_game_logic.py::test_difficulty_ranges[Easy-expected_range0] PASSED                                                          [ 59%]
tests/test_game_logic.py::test_difficulty_ranges[Normal-expected_range1] PASSED                                                        [ 63%]
tests/test_game_logic.py::test_difficulty_ranges[Hard-expected_range2] PASSED                                                          [ 68%]
tests/test_game_logic.py::test_unknown_difficulty_uses_default_range PASSED                                                            [ 72%]
tests/test_game_logic.py::test_first_attempt_win_awards_100_points PASSED                                                              [ 77%]
tests/test_game_logic.py::test_later_win_awards_fewer_points PASSED                                                                    [ 81%]
tests/test_game_logic.py::test_win_score_never_falls_below_10 PASSED                                                                   [ 86%]
tests/test_game_logic.py::test_incorrect_guess_loses_5_points PASSED                                                                   [ 90%]
tests/test_game_logic.py::test_score_can_become_negative PASSED                                                                        [ 95%]
tests/test_game_logic.py::test_unknown_outcome_does_not_change_score PASSED                                                            [100%]

============================================================ 22 passed in 0.13s =============================================================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
