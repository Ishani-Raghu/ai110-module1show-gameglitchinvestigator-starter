# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?
| Guess of 1 | Should tell me to guess higher because 1 is very low | Told me to go lower instead | None |

- What did the game look like the first time you ran it?
The first time I ran the game, it looked like a simple Streamlit guessing game where I had to guess a number between 1 and 100. However, I immediately noticed that the game behavior did not match the instructions. The hints were confusing because the game told me to go lower even when I typed 1, which should have been too low. I also noticed that invalid guesses like -100 were accepted even though the game said guesses should be between 1 and 100.

At least two concrete bugs I noticed were that the hints seemed backwards and the game accepted invalid numbers outside the allowed range. Another issue was that the attempts and score display seemed inconsistent, because the page showed attempts left as 0 while the developer debug info showed attempts as 8. The score also became negative, which made the scoring system feel broken or unclear.- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-1      Since 1 is very low, the game should say the guess is too low or tell me to guess higher.
The game told me to go lower instead.

-100
The game should reject the input because guesses should be between 1 and 100.
The game accepted the invalid guess and continued updating the game.
None

Multiple incorrect guesses
Score should update in a clear and reasonable way.
The score became negative and seemed to behave unpredictably.
None



---

## 2. How did you use AI as a teammate?-Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)? - chat gpt
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used ChatGPT to help me set up the project, troubleshoot issues with VS Code, and understand how to run the Streamlit application. I also used AI to help identify bugs and organize my observations into the reflection document.

One example of an AI suggestion that was correct was when ChatGPT suggested testing very low and very high guesses to identify whether the game's hint logic was working properly. I verified this by entering a guess of 1 and observing that the game incorrectly told me to guess lower, confirming that the hint logic was broken.

One example of an AI suggestion that was initially misleading was assuming that the game was already running correctly after Streamlit launched. Although the application opened successfully, I still had to manually test the game to discover several bugs. I verified this by interacting with the game and documenting the incorrect behavior in my bug log.



---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

decided a bug was fixed only after I could reproduce the original problem and then verify that the corrected code no longer showed the same behavior. I tested changes both by running the Streamlit application and by checking whether the game responded correctly to different inputs.

One manual test I ran was entering a very low number such as 1. Before the fix, the game incorrectly told me to guess lower. After updating the logic, the game correctly identified that the guess was too low and prompted the user to guess higher.

AI helped me understand how to create tests by suggesting specific inputs that would expose bugs. It also helped me think about edge cases, such as invalid inputs outside the allowed range and how those inputs should be handled.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
I learned that Streamlit reruns the script every time the user interacts with the application. Because of this behavior, important information such as the score, secret number, and remaining attempts must be stored in session state. Session state acts like memory for the application and allows information to persist between reruns. Without session state, the game would reset every time the user entered a guess.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
One strategy I want to reuse in future projects is documenting bugs before trying to fix them. Writing down the expected behavior and actual behavior made it easier to understand what was wrong and verify whether a fix worked.ext time I work with AI on a coding task, I would ask more focused questions about individual bugs instead of trying to solve multiple issues at once. This would make it easier to evaluate the quality of the AI's suggestions.

This project showed me that AI-generated code is useful for getting started, but it should not be trusted without testing. I learned that developers still need to verify behavior, debug problems, and use their own judgment when reviewing AI-generated solutions.
