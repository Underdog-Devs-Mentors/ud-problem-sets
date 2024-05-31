## Prohibited strings

Write a function that takes two arguments, a list of prohibited strings and a username, and returns a boolean of whether or not the username contains any of the prohibited strings.

Some important details:

- The list of prohibited words will provide words in some casing, and we want to be case-insensitive in our checks. For example, if “darn” is a prohibited word, “darn”, “DARN” and “DaRn” are all prohibited.
- Sometimes people like to make usernames that substitute numbers for letters, to try to get around a prohibited word list. We also want to make those substitutions prohibited. The specific letter substitutions we need to check are:
  - A becomes 4
  - E becomes 3
  - I becomes 1
  - O becomes 0
  - For example, if “darn” is a prohibited word, “d4rn” is also a prohibited word. If “darn” and “heck” are prohibited words, the username “D4RN_y0u_T0_h3ck” contains prohibited words.

## Postfix notation calculator

### Setup

Most of us learn how to do math with operators in between numbers. For example:

`(((4 * 3) + 1) - 2) = 11`

You have an operator like `+ - * /`, and numbers (“operands”) on each side of the operator, and you apply the operator to those operands. If you have multiple expressions, you resolve them according to some order of operations (or forcing the order using parenthesis). This way of doing math uses infix notation — the operators are in between the operands.

There’s another way of doing math that uses postfix notation — the operators come after the operands. This is a cool way of doing math — you don’t need parenthesis or rules to describe the order of operations, so it’s easier to parse a math expression, and you can use a stack to manage the calculation (using the stack data structure in the real world!).

Let’s build a basic postfix notation calculator.

### What to implement

Write a function that takes as an argument a string containing a mathematical expression in postfix notation, using as available operators `+ - * /`. The function should return the result of evaluating that expression.

### Example algorithm

The postfix notation version of `(((4 * 3) + 1) - 2)` is:

`1 3 4 * + 2 -`

Here’s how the stack evolves while evaluating this expression:

| Token                        | Stack                                                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Before processing any tokens | [] // initially empty                                                                                         |
| 1                            | [1] // Push the operand onto the stack                                                                        |
| 3                            | [1, 3] // Push the operand onto the stack                                                                     |
| 4                            | [1, 3, 4] // Push the operand onto the stack                                                                  |
| \*                           | [1, 12] // Pop the last 2 operands off the stack, apply the operator, and push the result back onto the stack |
| +                            | [13] // Pop the last 2 operands off the stack, apply the operator, and push the result back onto the stack    |
| 2                            | [13, 2] // Push the operand onto the stack                                                                    |
| -                            | [11] // Pop the last 2 operands off the stack, apply the operator, and push the result back onto the stack    |

### Example inputs and outputs

| Input            | Output                                           |
| ---------------- | ------------------------------------------------ |
| “1 3 4 \* + 2 -" | 11                                               |
| “3 2 1 + + 2 /”  | 3                                                |
| “2 +”            | <raise an error, this is a malformed expression> |

### Once you have a working implementation:

- What edge cases would you need to handle to have a robust calculator?

## Count ships

Write a function that counts of the number of ships in a 2D grid.

- Input: an array of arrays of strings, representing a 2D grid. The strings are either a `"."` for open water, or an `"S"` for part of a ship. Connected `"S"`es are part of the same ship.
- Output: an integer that is the count of the number of ships in the grid.

Facts about ships:

- Ships are only horizontal or vertical, not diagonal.
- Ships have a width of one or more and a height of one or more.
- Ships never touch each other.

The input will always be a well-formed grid (all rows are the same length).

Example function calls

```
let ships = [
    [".", "S", ".", "S"],
    [".", ".", ".", "S"],
    ["S", "S", ".", "S"],
    [".", ".", ".", "S"]
]

countShips(ships) -> 3


let ships = [
    ["S", "S", ".", "S", "S", "S", ".", "."],
    ["S", "S", ".", "S", "S", "S", ".", "."],
    ["S", "S", ".", ".", ".", ".", "S", "S"]
]
countShips(ships) -> 3
```

## Balanced brackets

Given a string of different bracket types (parentheses, square brackets, and curly braces), write a function that returns whether or not the string is balanced.

The string is balanced if each opening bracket is followed by a corresponding close bracket, and all brackets between those open and close brackets are also balanced.

### Examples of balanced strings

- `{[()]}`
- `{}[]()`
- `[(){()}]`

### Examples of unbalanced strings

- `{[(])}` // Has a `]` before the `(` was closed with a `)`
- `{}][()` // Has a `]` without a preceding `[`
- `[(){()}` // Missing a closing `]`

### Example function calls

- `checkBrackets("{[()]}") → True`
- `checkBrackets("{}][()") → False`

## Scrabble solver

This was a real interview question at Dropbox. Candidates who passed the interview would typically successfully implement Part 1 and then articulate an algorithm for Part 2 within 60 minutes, but they might not have time to implement Part 2.

Part 1

Write code that:

- Accepts a string (e.g. as an argument to a function, or as a command-line argument). This string represents your Scrabble “rack”.
- Prints out the words that can be made from the characters in that input string, along with their Scrabble scores, one word per line, in descending score order

Example input and output:

```
$ python scrabble_cheater.py SPCQEIU  # Use any language you like.
17 piques
17 equips
16 quips
16 pique
16 equip
15 quip
…
```

Resources:

- Word list
- Letter scores

Key points:

- Letters cannot be reused. For example, if your Scrabble rack is “ABCD”, you can make the word “CAB” but not the word “DAD”, because you only have one “D”.
- Part 2

Extend the script to handle blank tiles. When reading the input, the character \_ can be used as a wildcard — it can represent any letter.

Wildcards do not count towards a word's score.

## Rot solver

Part I an example 60 minute interview question. It’s easy to get tripped up on the math — be systematic in your debugging and power through it! Part II is a bonus exercise.

Part I

(If you’ve heard of a rot13 letter substitution cipher, this question is a generalization of that cipher)

Write a function `rot` that:

- takes as arguments: an input string and an amount by which to shift the letters in the string
- returns: the input string, shifted by the shift amount

The function should preserve case — it should be able to handle both upper and lowercase letters — and it should not alter punctuation. The function should support negative numbers. The function should support large shift numbers.

Sample inputs and outputs:

```
rot("HELLO", 1) -> "IFMMP" # shift right by 1
rot("HELLO", 2) -> "JGNNQ" # shift right by 2
rot("HELLO", -1) -> "GDKKN" # shift left by 1
rot("HELLO", 27) -> "IFMMP" # shift right by 27, wrapping back to the beginning
rot("Hello, Rick", 1) -> "Ifmmp, Sjdl" # Preserve case and punctuation
rot(rot("Hello, Rick", 1), -1) -> "Hello, Rick"
```

Writing this function will require familiarity with converting between character and ordinals. For example, Python has the `ord` and `chr` functions, and JavaScript has the `charCodeAt` and `fromCharCode` String methods.

You may also find reviewing modular arithmetic (using `%`) to be helpful.

Part II

Using your `rot` function, write a function `decrypt` that takes a text encrypted using a shift substitution cipher of an unknown shift amount, and returns a tuple containing `(the shift used to encrypt the original string, the original string)`.

You will need a dictionary or word list. An input string needs to be long enough to unambiguously determine the the shift used, or there could be multiple valid shifts.

Sample inputs and outputs:

```
decrypt("Ju xbt uif cftu pg ujnft, ju xbt uif xpstu pg ujnft") -> ("It was the best of times, it was the worst of times", 1)
```
