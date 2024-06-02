# Data problems

## Countries

Use the `countries.txt` file to answer the following questions.

### For loops and if conditions

- [ ] What are all of the countries that have “United” in the name?
- [ ] What countries both begin and end with a vowel?
- [ ] What country names are > 50% vowels?

### Setting up storage to use during a for loop, including counters and arrays

- [ ] What is the shortest country name? Make sure your solution can handle ties.
- [ ] What countries use only one vowel in their name (the vowel can be used multiple times) - For example, if the word “BEEKEEPER” were a country, it would be an answer, because it only uses “E”.
- [ ] There is at least one country name that contains another country name. Find all of these cases.

## Baby names

### More for loops, if conditions, and storage

- [ ] What is the shortest baby name in the top 40 baby names for 2020?
- [ ] What are the longest baby names in the top 40 baby names for 2020? Make sure you can handle if there’s a tie.

### Nested for loops

- [ ] There is at least one baby name from the top 40 baby names for 2020 that, when spelled backwards, is a valid Scrabble word. Find and print all such names.
- [ ] Solve this two ways: first with an array to hold the Scrabble words, and then with a dictionary (or set) to hold the Scrabble words. Use timer functions to measure how long it takes to complete this work under each implementation. Why is the time different?
- [ ] What are all of the names that were top 40 baby names in both 1880 and 2020?

## More wordplay questions

The sections after this section (“NBA Finals”, “Top Movies”, “Billboard Top 100”) are focused on using bigger datasets to practice breaking down and solving larger problems, including making choices about what data structures to use, coming up with an algorithm to implement, and writing functions to help organize your implementation.

Before you move on to those sections, we recommend confirming that you are comfortable independently breaking down, implementing, and debugging the questions below. If you aren’t, work with your mentor on more Wordplay, Countries, and Baby Names-sized questions until you are consistently able to solve them independently.

### Revisiting for loops, if conditions, and using lists as storage

- [ ] What are all of the words that have only “U”s for vowels?
- [ ] What are all of the words that have only “E”s for vowels and are at least 15 letters long?
- [ ] What are all of the words that start with “PRO”, end in “ING”, and are exactly 11 letters long?
- [ ] What are all of the words that can be made from only the letters in “RSTLNE”? Not all of those letters need to be used, and letters can be repeated.
- [ ] What is the longest word that can be made from only the letters in “RSTLNE”? Not all of those letters need to be used, and letters can be repeated. Make sure your solution can handle ties.
- [ ] What is the longest word that can be made without the letters in “AEIOSHRTN” (in other words, without the most common letters)? Make sure your solution can handle ties.
- [ ] Let’s assign letters the following points: - W = 12 - Z = 15 - E = -17 - All other letters = 1
- [ ] What are all of the words with at least 50 points?

### Functions

- [ ] Write a function that takes a string `substring` as an argument and returns an array of all of the words that contain that substring (the substring can appear anywhere in the word).
- [ ] Write a function that takes a string `prefix` as an argument and returns an array of all of the words that start with that prefix (the prefix has to be at the beginning of the word).
- [ ] Write a function that takes a string `prefix` as the first argument, a string `suffix` as the second argument, and an integer `length` as the third argument. It should return an array of all of the words that start with that prefix, end with that suffix, and are that length.
- [ ] Write a function that takes a string `word` as an argument and returns a count of all of the “A”s in that string.
- [ ] Write a function that takes a string `word` as the first argument, a string `letter` as the second argument, and returns a count of how many times `letter` occurs in `word`.
- [ ] Write a function that takes a string `phrase` and returns a dictionary containing counts of how many times every character appears in `phrase`.

# Other problems

## Rotation cipher

Write a program that encrypts a given message using a rotation cipher, rotating by the amount given (`N`).

A rotation cipher is a character based cipher where each character receives a “shift” / “rotation” by a given N letters in an alphabet. In other words, any single letter is replaced by a different single letter that is located further (exactly `N` letters further) in the alphabet, wrapping from the end to the start.

For example `rotationcipher(1, 'hello')` would result in 'ifmmp' and `rotationcipher(1, 'Hello')` would result in 'Jgnnq'.

## Change calculator

Write a program that takes a positive number as an input and returns a list of the minimum number of dollars (up to $20 bills) and coins to make up that amount.

Example 1:

```
$ python3 change.py 0.41
1 quarter
1 dime
1 nickel
1 penny
```

Example 2:

```
$ python3 change.py 22.50
1 $20 bill
2 $1 bills
2 quarters
```

## (challenge) Substitution cipher

Write a program that encrypts a given message using a substitution cipher, where a letter is replaced by another letter using the key-value pair given. The user should input their substitution by providing a list of all 26 letters as a single string, followed by the string they’d like to encrypt. Make sure to check to make sure the substitution is valid, letting the user know what letters were used multiple times or were missing if their substitution was invalid.

Example 1:

```
$ python3 substitution.py YTNSHKVEFXRBAUQZCLWDMIPGJO HELLO
EHBBQ
```

# 2D arrays

## Find the number of 0s

Write a program to find the number of zeros in 2D matrix. For example: `const arr = [[0,1,1],[0,1,0],[1,0,0]];`.

(challenge) Allow any number of nesting of arrays to be used.

## Find the most repeated number

Given a two dimensional array of numbers, find the number that is repeated the most times using for loops.

## Pattern creation

Write a program to construct the following pattern using loops.

```
*
* *
* * *
* * * *
* * * * *
* * * *
* * *
* *
*
```

## Minesweeper

Given a 2D array of strings with equal rows and columns, output a 2D array that has either an "X" if there was an "X" in the cell originally or the count of all adjacent Xs to that cell.

For example, given:

```
[
  [" ", " ", "X", " "],
  [" ", "X", " ", " "],
  [" ", " ", "X", "X"],
  ["X", " ", " ", " "],
]
```

The result should be:

```
[
  [  1,   2, "X",   1],
  [  1, "X",   4,   3],
  [  2,   3, "X", "X"],
  ["X",   2,   2,   2],
]
```

## Sum of adjacent cells

Given a 2D array of numbers with equal rows and columns, output a 2D array that has the sum of all 9 adjacent cells, including itself.

For example, given:

```
[
  [0, 0, 1, 0],
  [0, 1, 2, 0],
  [3, 0, 0, 1],
  [0, 0, 1, 0],
]
```

The result should be:

```
[
  [1, 4, 4, 3],
  [4, 7, 5, 4],
  [4, 7, 5, 4],
  [3, 4, 2, 2],
]
```
