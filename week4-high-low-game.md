## Milestone 1 – Generate random numbers
The random.randint(a, b) helper returns an inclusive integer in [a, b], unlike range() which is exclusive of its stop value

```text
BEGIN GAME
    IMPORT random module
    PRINT banner

    player_num   ← random.randint(1, 100)   # visible to player
    computer_num ← random.randint(1, 100)   # hidden later
END
```

## Milestone 2 — Get user choice

```text
BEGIN GAME
    IMPORT random module
    PRINT banner
    player_num   ← random.randint(1, 100)   # visible to player
    computer_num ← random.randint(1, 100)   # hidden later
    
    PROMPT "Do you think your number is higher or lower than the computer's? "
    guess ← user input → trim spaces → to lower-case
END
```

## Milestone 3 — Decide who wins the round

```text
BEGIN GAME
    IMPORT random module
    PRINT banner
    player_num   ← random.randint(1, 100)   # visible to player
    computer_num ← random.randint(1, 100)   # hidden later
    
    PROMPT "Do you think your number is higher or lower than the computer's? "
    guess ← user input → trim spaces → to lower-case
    
    IF guess = "higher" AND player_num > computer_num THEN
        PRINT "You were right!"
        INCREMENT score
    ELSE IF guess = "lower" AND player_num < computer_num THEN
        PRINT "You were right!"
        INCREMENT score
    ELSE
        PRINT "Aww, that's incorrect."
    ENDIF

    PRINT "The computer's number was", computer_num
END
```

## Milestone 4 — Play multiple rounds

```text
SET NUM_ROUNDS ← desired number of rounds
SET score ← 0

PRINT banner

FOR round_num FROM 1 TO NUM_ROUNDS DO
    PRINT blank line
    PRINT "Round", round_num

    player_num   ← random.randint(1, 100)
    computer_num ← random.randint(1, 100)

    PRINT "Your number is", player_num
    guess ← prompt for "higher or lower?"

    IF (guess = "higher" AND player_num > computer_num) OR
       (guess = "lower"  AND player_num < computer_num) THEN
        PRINT "You were right!"
        INCREMENT score
    ELSE
        PRINT "Aww, that's incorrect."
    ENDIF

    PRINT "The computer's number was", computer_num
    PRINT "Your score is now", score
ENDFOR
```

# Milestone 5 — Final message

```text
…  # (loop from Milestone 4 finishes)
PRINT blank line
PRINT "Thanks for playing!"
END GAME
```

Tip: When translating to Python, replace ← with =, use colons (:) after if, else, for, etc., and indent consistently.
