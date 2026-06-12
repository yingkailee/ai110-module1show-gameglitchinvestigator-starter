# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
  Nice UI with hint provided with each guess with a Developer Debug section and settings on the left.
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
  The hints are the opposite of what are expected when comparing the guess and secret, New Game doesn't reset the history or the game, a little confused on why Attempts: in Developer Debug Info starts as 1 in fresh site but 0 with new game.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| Guess 0 when secret is 10 | Go HIGHER! | Go LOWER! | none |
| Guess 100 when secret is 10 | Go LOWER! | Go HIGHER! | none |
| New Game button pressed | Game over popup is removed, able to see new hints from guessings | Popup remains, unable to submit more guesses and history isn't impacted | none |
| Any guess is submitted | Attempts left: count lowers | Attempts left: count stays the same | none |


---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used Claude Code and I got code suggestions that I could accept and then edit if necessary.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
It suggested switching around the messages for go higher and go lower. I verified this by replaying the game and later working on the test cases.
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
When asking it to debug New Game issues it failed to see that in the Debug Info panel it didn't start out at Attempts:0 and instead it started at Attempts:1, the first guess doesn't go in the history either.
Also, when I asked it to fix the history updating immediately after each guess it for some reason just deleted the code for debug info.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
Revisited the UI to try to recreate the bug and verify correct behavior
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
I ran the tests given for check_guess. One thing was that it had to be edited to properly unpack the return type of tuple, one thing would be to consider moving away from tuple return type though I'm unsure what's the Python standard for this.
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
