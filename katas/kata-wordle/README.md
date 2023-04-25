# Wordle Kata

[Wordle](https://www.powerlanguage.co.uk/wordle/) is a web-based word game created and developed by Welsh software engineer Josh Wardle, and owned and published by The New York Times Company since 2022. (Source [Wikipedia](https://en.wikipedia.org/wiki/Wordle))

## Rules

Players have six attempts to guess a five-letter word, with feedback given for each guess indicating when letters match or occupy the correct position.

Possible feedback:

* Letter not in the word
* Letter in the word but wrong position
* Letter in the word and correct position

## Task

Your task is to create a Wordle clone by implementing the above rules.

## Example

The secret word is **PLATE**

Guess 1: CHOPS | Feedback: no, no, no, no, no
Guess 2: MEALY | Feedback: no, position, yes, position, no
Guess 3: SLATE | Feedback: no, yes, yes, yes, yes
Guess 4: SLATE | Feedback: yes, yes, yes, yes, yes

Note: you can represent the feedback anyway you see fit

## Extension

There is a *hard mode*, where guesses MUST use all feedback from previous guesses.
