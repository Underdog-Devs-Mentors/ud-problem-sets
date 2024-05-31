## Boggle solver

This is a retired coding question from Dropbox. I don’t know how often candidates would actually solve this completely during a 60-minute interview, so instead I’m going to break this into a couple of pieces with expectations for each.

### Part 1

Implement a recursive depth-first search that you fully understand and could reproduce in front of someone from scratch if you needed to.

Then, run your DFS implementation on some example graphs. This means being comfortable with how to represent a graph with nodes and edges in your preferred interview language.

This will become the foundation for the Boggle solver.

#### Example inputs and outputs

Grid:

```
BE
TQ
```

Valid words: `{'BET'}`

### Part 2

Review how to play Boggle. Here is an example online version.

The goal of the game when played with humans is to find as many words as you can in a grid of 16 letters, in a limited amount of time. Words can only be made from connected letters — i.e. from a given letter you can only use the letters directly adjacent, including diagonally. You can’t reuse letters, and words must be at least 3 letters long.

#### Example inputs and outputs

Grid:

```
ZQQZ
ZAEZ
ZUDZ
ZQQZ
```

Valid words: `{'ZUZ', 'ZED', 'ADZ', 'QUAD', 'EAU', 'DAE', 'DUE', 'ZEA', 'QUA', 'ADZE', 'AUE', 'ZZZ'}`

### Part 3

Implement a Boggle solver. This is the part that you can treat like a time-boxed interview if you’d like. You will likely want to break this into the follow steps:

1. Stub out a function that takes as input a grid (e.g. a 2 x 2 or 4 x 4 matrix of letters) and returns all of the words that can be made from that grid.
2. Write a function to create a graph from the grid. [Goal: complete this sub-part in 30 minutes]
   1. Refer back to your graph representations from Part I.
   2. Test that you get the correct graph back from a grid.
3. Set up a data structure containing all words in the dictionary, with efficient lookup. [Goal: complete this sub-part in < 10 minutes (you probably already have this implemented if you’ve completed the prior problems in this problem set)]
4. Use depth-first search to find all of the words in the grid. [Goal: complete this sub-part in 60 minutes]
   1. You’ll need to run DFS starting from every letter.
   2. You don’t need any fancy data structures to solve a 4x4 grid quickly.
   3. You’ll need a way of confirming if a path through the grid makes a valid word.
   4. You might find it helpful (both as a light efficiency optimization and for easier debugging) to stop pursuing paths in the grid that cannot possibly lead to a valid word, i.e. that path is not a valid prefix for any word in the dictionary.

#### Example inputs and outputs

```
MSEF
RATD
LONE
KAFB
```

Valid words: `{'FONDEST', 'TOR', 'RANTED', 'OAF', 'FETES’ … 486 words in all}`

## Word pattern

This is a retired 60-minute coding question from Dropbox. A good goal would be to be able to finish Part 1 within the 60 minutes, and then to come up with a plan for Part 2 even if you don’t have time to implement it fully.

### Part 1

Write a function that takes as arguments two strings: `pattern` and `input`. Return whether or not the words in `input` match the pattern of the characters in `pattern`.

Example 1:

| `pattern: 'abba'`            |
| ---------------------------- |
| `input: 'red blue blue red'` |
| `result: True`               |

Example 2:

| `pattern: 'abcabc'`                      |
| ---------------------------------------- |
| `Input: 'red blue green red blue green'` |
| `result: True`                           |

Example 3:

| `pattern: 'abba'`             |
| ----------------------------- |
| `Input: 'red blue green red'` |
| `result: False`               |

### Part 2

Write a function that takes as arguments two strings: `pattern` and `input`. Return whether or not `input` can be broken into words to match the pattern of the characters in `pattern`.

(In other words, this is the same problem as part 1, but `input` doesn’t contain spaces, so you’ll need to determine if it is possible to split up the input into words in a way that matches `pattern`. You will likely want to use recursion.)

Example 1:

| `pattern: 'abcba'`             |
| ------------------------------ |
| `input: 'redbluegreenbluered'` |
| `result: True`                 |

Example 2:

| `pattern: 'aba'`                                                               |
| ------------------------------------------------------------------------------ |
| `Input: 'xxyyyxx'`                                                             |
| `result: True`, with multiple solutions:<br><br>- x, xyyyx, x<br>- xx, yyy, xx |

Example 3:

| `pattern: 'abba'`          |
| -------------------------- |
| `Input: 'redbluegreenred'` |
| `result: False`            |
