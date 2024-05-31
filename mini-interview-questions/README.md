## Monster maker

This is an exercise in class and API design. For this exercise, please use the `animals.csv` file containing information on various animals.

Setup

- An `Animal` has the following properties:
  - Name
  - Number of legs
  - Sound that it makes
- A `Monster` is created from two different `Animals` with the same number of legs: one for the head and one for the body.
- A `Monster` has the following properties: - Name (the combination of the names of the head and body) - Number of legs - `Animal` head - `Animal` body - Sound that it makes (the combination of the sounds of its `Animal` head and body)
  Tasks

We are going to design some classes and functions to create and interact with `Monster`s. The below descriptions are using generic pseudocode — the class and function signatures will look different in the specific programming language you are using.

The class and function definitions below are not fully specified — you will need to make some decisions about how they should work to be useful to someone who would use your code in their own projects.

Please implement the following:

- An `Animal` class
  - Example constructor call: `Animal(name: "Octopus", numLegs: 8, sound: "Burble")`
- A `Monster` class, that creates a `Monster` from an `Animal` head and an `Animal` body
  - Example constructor call: `Monster(head: Animal(Octopus), body: Animal(Scorpion))`
    - `Monster.name` → `OctopusScorpion`
    - `Monster.sound` → `BurbleHiss`
  - Your code should ensure that we can only create a `Monster` with the head and body of two different `Animals`, who have the same number of legs.
- A function `createAllMonsters` that takes as input a number of legs and returns an array of all `Monsters` that can be made with that number of legs. A `Monster` with `Animal` A head and `Animal` B body is distinct from a `Monster` with `Animal` B head and `Animal` A body. Please use the animals.txt file linked at the beginning of this problem.
  - Example function call: `createAllMonsters(8)` → `[Monster(OctopusScorpion), Monster(ScorpionOctopus)]`
  - The crux of this function is: how do we produce all of the combinations of heads and bodies for animals with a given number of legs?
- A function `getRandomMonster` that takes as input a number of legs and returns a random Monster with that number of legs.
  - Example function call: `getRandomMonster(8)` → `Monster(OctopusScorpion)`
  - This function should call your `createAllMonsters` function

## `k` largest elements

Goal: solve this problem in < 30 minutes.

Write a function that takes as input two arguments:

1. An array of numbers
2. An integer `k`

and returns the `k` largest values from that array. The order of the elements in the returned array doesn’t matter.

Example

- Input array: `[5, 16, 7, 9, -1, 4, 3, 11, 2]`
- `k`: 3
- Result: `[16, 9, 11]`

## Pair sum

Goal: solve this problem in < 30 minutes.

Write a function that takes as input two arguments:

1. An array of numbers
2. An integer `k`

and returns an array with all of the pairs of numbers from that array that sum to `k`. You can’t use the same number twice. You can assume that there are no duplicate numbers in the array.

Example

- Input array: `[1, 9, 6, 3, 5, 4]`
- `k`: 10
- Result: `[[1, 9], [6, 4]]` // Note that `[5, 5]` is not in the solution
