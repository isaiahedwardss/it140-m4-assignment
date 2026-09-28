<!-- To see this file in a clean, formatted view, select ▼ in the upper-right corner of the editor pane, then select "Markdown Preview". -->

# Software Development Worksheet (SDW)

* **Course:** IT 140 - *Introduction to Scripting*
* **Activity:** Module Four Assignment
* **Program:** Higher/Lower Game

> Use this worksheet as optional working notes while you move through the **Analyze** and **Design** phases of the simplified Software Development Life Cycle (SDLC).
>
> Your notes do not need to be formal or polished. Keep answers brief and write them in your own words. The purpose of the SDW is to help you understand the requirements and plan your own graded pseudocode.
>
> Look for **TODO** prompts. Replace them with your own answers if you use this worksheet.
>
> **This worksheet is not a graded deliverable.** Do not submit it in D2L Brightspace unless your instructor specifically asks for it.

## How to Use This Worksheet

The worksheet uses the same pattern throughout:

* **Where to look** tells you where to find the information you need.
* **Prompt** tells you what to think about or answer.
* Your response goes immediately after the prompt.

The worksheet intentionally asks questions instead of supplying the completed Higher/Lower Game algorithm. Your graded `design/hilow_game.pseudo` should contain **your** design.

# Analyze Phase

## 1. Describe the Problem

**Where to look:** Module Four Assignment Guidelines and Rubric → Overview, Scenario, and Prompt.

**Prompt:** In one or two sentences, describe what the program needs to accomplish for Maria and Bella.

**Your notes:**

The program lets Bella play a higher/lower guessing game. It picks a random number between two numbers she enters and keeps asking her to guess until she gets the correct number. 

## 2. Identify Inputs and Outputs

**Where to look:** Guidelines and Rubric → Prompt; Higher/Lower Game Sample Output; SRS FR-1, FR-5, and FR-9.

**Prompt:** What information must come from the player, and what categories of information must the program communicate?

**Inputs:**

The lower bound and upper bound.
The player's guess.

**Outputs:**
The program tells the player if the guess is to low, too high, or correct. It also gives a message when the numbers entered are not valid. 

Do not choose exact message wording yet unless it helps you reason about the behavior.

## 3. Identify Validation Requirements

**Where to look:** Guidelines and Rubric → Prompt; SRS FR-2, FR-3, FR-6, and FR-7.

**Prompt:** Describe each input-validation rule in plain language and what should happen when the rule is not satisfied.

**Your notes:**

The lower bound must be less than the upper bound. If it is not, the program asks the user to enter the bounds again. 
The guess must be between the lower and upper bounds. If it is outside the range, the program asks the user to enter another guess. 

## 4. Identify Processing and Decisions

**Where to look:** Guidelines and Rubric → Prompt; SRS FR-4, FR-8, and FR-9.

**Prompt:** What value must the program generate, and what possible relationships between a valid guess and that value must the design distinguish?

**Your notes:**

The program generates a random number between the lower and upper bounds. 
The guess can be too low, to high, or the correct number. 

## 5. Identify Repeated Behavior

**Where to look:** Guidelines and Rubric → Prompt; SRS FR-3, FR-7, FR-10, and FR-11.

**Prompt:** What work can repeat? For each repeated part, what condition causes repetition and what condition lets the program continue or stop?

**Your notes:**
Keep asking for the lower and upper bounds until the lower bound is less than the upper bound. 
Keep asking asking for a guess until the guess is within the valid range. 
Keep asking for guesses and telling the player if the guess is too low or too high. Stop when the player guesses the correct number. 

## 6. Distinguish Requirements From Extra Features

**Where to look:** SRS → Out of Scope Unless Your Instructor Adds a Requirement.

**Prompt:** List one or two features you might be tempted to add that are not required by the assignment.

**Your notes:**
Keeping track of how many guesses the player makes.
Adding different dificulty levels. 

## 7. Analyze Checkpoint

Before moving to Design:

* [ ] I can explain the game's purpose in my own words.
* [ ] I identified the required player inputs.
* [ ] I identified the required categories of output.
* [ ] I can explain both validation requirements.
* [ ] I know when the random number is generated.
* [ ] I can explain the too-low, too-high, and correct outcomes.
* [ ] I can identify the repeated behaviors and their stopping conditions.
* [ ] I did not turn optional features into assignment requirements.

# Design Phase

## 8. Plan the Major Stages

**Where to look:** Your Analyze notes, SRS, and `design/hilow_game_sdd.md`.

**Prompt:** List the major stages of the game in order without writing the completed pseudocode here.

**Your notes:**

1. Ask the player for the lower and upper bounds.
2. Check that the lower bound is less than the upper bound.
3. Generate a random number between the two bounds.
4. Ask the player to guess a number and check if the guess is in range.
5. Tell the player if the guess is too low, too high, or correct, and keep playing until they guess correctly.


## 9. Plan Validation Before Detailed Pseudocode

**Where to look:** Your Analyze notes and SDD → Validation and Decision Branching.

**Prompt:** For each validation requirement, explain what information is checked and how the program can eventually receive acceptable input.

**Your notes:**

* Bounds-validation plan: Check that the lower bound is less than the upper bound. If it is not, ask the player to enter the bounds again.

* Guess-validation plan: Check that the guess is between the lower and upper bounds. If it is not, ask the player to enter another guess.

## 10. Plan Repetition

**Where to look:** Your Analyze notes and SDD → Repetition and Stopping Conditions.

For each repeated section, answer:

* What condition is checked?
* What happens during one repetition?
* What information can change?
* What stops the repetition?

**Your notes:**

The program will repeat asking for the bounds until the lower bound is less than the upper bound. After the random number is generated, the program will keep asking for guesses. If the guess is outside the range, the player will be asked for another guess. If the guess is too low or too high, the game will continue. The guessing loop stops when the player guesses the correct number.

## 11. Plan Decision Branching

**Where to look:** SRS FR-8 and FR-9.

**Prompt:** What outcomes must the valid-guess comparison distinguish, and what should happen after each outcome?

**Your notes:**

The program needs to check three possible results. If the guess is lower than the random number, it tells the player the guess is too low. If the guess is higher, it tells the player the guess is too high. If the guess matches the random number, it tells the player they got it right and ends the game.

## 12. Requirements-to-Design Traceability

After drafting `design/hilow_game.pseudo`, locate where your design addresses each requirement group.

| Requirement group | Where it appears in your pseudocode |
| --- | --- |
| Bounds input and validation | Steps 1-2 |
| Random-number generation | Step 3 |
| Guess input and validation | Step 4 |
| Too-low / too-high / correct decisions | Step 5 |
| Repetition until correct | Steps 2, 4, and 5 |
| Required outputs | Steps 2 and 5 |

If a required behavior has no corresponding design step, revise the pseudocode.

## 13. Trace a Behavior by Hand

**Where to look:** SRS → Behavior Verification Cases and the official Sample Output.

Choose one scenario that includes repetition or validation. Follow your pseudocode one statement at a time.

**Scenario:** The player enters an invalid upper bound and then makes a few guesses before getting the correct number.

**Trace notes:**

The program first asks for the lower and upper bounds. If the upper bound is not greater than the lower bound, it asks for the bounds again. Once the bounds are valid, the program generates a random number. The player enters a guess. If the guess is too low or too high, the program gives a message and asks for another guess. The program keeps doing this until the guess matches the random number.

## 14. Rubric Review

### Logical Steps — 35%

* [ ] My design logically outlines the complete required program.
* [ ] Another programmer could follow the order of the steps.
* [ ] I represented all required functionality.

### Input/Output — 30%

* [ ] I represented both bound inputs.
* [ ] I represented guess input.
* [ ] I represented required feedback and success output.

### Program Flow — 35%

* [ ] I used decision branching for the valid-guess outcomes.
* [ ] I used loops for required repeated behavior.
* [ ] Each loop has an understandable stopping condition.
* [ ] Indentation shows which statements belong inside branches and loops.

## 15. Design Checkpoint

* [ ] Valid bounds are established before the target number is generated.
* [ ] Invalid bounds can lead to new bound input.
* [ ] A guess is validated against the selected range.
* [ ] An invalid guess can lead to another guess.
* [ ] Too-low and too-high valid guesses allow play to continue.
* [ ] A correct guess ends the guessing process.
* [ ] No starter `TODO:` prompts remain in the graded pseudocode.

## 16. Ready to Submit

Before submission:

* [ ] I reviewed the current Module Four Assignment Guidelines and Rubric.
* [ ] I reviewed the official Higher/Lower Game Sample Output.
* [ ] I traced multiple required behaviors through my pseudocode.
* [ ] I saved the graded file as `design/hilow_game.pseudo`.
* [ ] I understand that only the `.pseudo` file is required for submission.

# Optional Construct and Test Notes

Complete the remaining sections only if you choose the optional Python practice after your graded pseudocode is ready.

## 17. Construct Notes — Optional

Open [`src/README.md`](src/README.md) and translate **your own completed pseudocode** into `src/hilow_game.py`.

| Design idea | Python concept you used |
| --- | --- |
| User input | TODO |
| Bounds validation | TODO |
| Random number | TODO |
| Guess validation | TODO |
| Decision branching | TODO |
| Repetition | TODO |
| Output | TODO |

## 18. Test Notes — Optional

Open [`tests/README.md`](tests/README.md).

| Scenario | Expected behavior | Actual behavior | Pass? |
| --- | --- | --- | :---: |
| TODO | TODO | TODO | TODO |
| TODO | TODO | TODO | TODO |
| TODO | TODO | TODO | TODO |

If testing exposes a design problem, revise the graded pseudocode first and then update the optional Python implementation.
