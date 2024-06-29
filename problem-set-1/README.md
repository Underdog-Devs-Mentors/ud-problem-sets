# Basic loop problems

## Multiplication

Write a function to find the product (multiplication) of two given numbers only using addition. For example, `multiple(2, 5)` should result in 10.

## Modulo

Write a function that calculates the modulo (remainder - usually `%`) of a number divided by another number without using your language's modulo operator itself or your language's division (or multiplication) operator. For example, `mod(137, 10)` should result in 7 and `mod(15, 4)` should result in 3.

## Sum

Write a program to calculate the sum of the digits of the provided number using a loop. For example, `sumOfDigits(25)` should result in 7 and `sumOfDigits(624)` should result in 12.

## Divisibility

Write a program to find those numbers which are divisible by 7 and of 5, between 1500 and 2700 inclusive.

(challenge) Make this program generic to handle a range and any amount of numbers to check for divisibility be passed in instead of just 7 and 5. 

## Powers

Write a program to find the value of a given number raised to the power of a second given number using a loop. For example, `power(5, 2)` should result in 25.

## Factorials

Write a function to find the factorial value of any number using a loop. For example, given `4` return 24, given `5` return `120`.

## Min and max

Write a program that takes a list of numbers as its input. Then return the highest and lowest numbers that were given.

# Basic applications with user input

Sometimes you will need to prompt users for input. This is practice for that!

Don't worry too much about the interface - focus on the logic part. If you're not sure how to get user input using the language that you've chosen feel free to ask in the UnderdogDevs Slack or your mentor!

## Bill calculator

Write a program that calculates the total cost of a restaurant bill. It should act like the example below. For invalid items, let the user know it is not valid and don’t include it in the total.

```
Choose from the following menu to order. When finished ordering, submit an empty entry.

Menu:
Burger: $9.50
Vegan Burger: $11.00
Hot Dog: $5.00
Cheese Dog: $7.00
Fries: $5.00
Cheese Fries: $6.00
Cold Pressed Juice: $7.00
Cold Brew: $3.00
Water: $2.00
Soda: $2.00

Enter a food item: burger
Enter a food item: fries
Enter a food item: ice cream
Sorry, “ice cream” is not a valid option
Enter a food item: soda
Enter a food item:

Your total cost is: $16.50
```

## Hours worked

Write a program that prompts users for the number of weeks that they worked. Then prompt them for how many hours they worked each week. Then prompt them for whether they’d like the total number of hours worked or the average of the number of hours per week and return the result asked for.

Example 1:

```
Number of weeks to track: 3
Week 0 HW Hours: 3
Week 1 HW Hours: 7
Week 2 HW Hours: 10
Enter T for total hours, A for average hours per week: A
6.7 hours
```

Example 2:

```
$ python3 hours.py
Number of weeks taking CS50: 2
Week 0 HW Hours: 2
Week 1 HW Hours: 8
Enter T for total hours, A for average hours per week: T
10.0 hours
```

## 1337SP36K

Write a program that replaces all of the following letters with the corresponding numbers (ignoring case):

- `l` becomes `1`
- `a` becomes `6`
- `e` becomes `3`
- `i` becomes `1`
- `o` becomes `0`
- `t` becomes `7`

For example, `leetSpeaK` becomes `1337SP36K` and `hello WORLD` becomes `h3110 W0R1D`.

## Password validator

Write a program to check whether the provided string has at least one lower case letter, one upper case letter, one number and one symbol. It should let the user know what they are missing if they are missing something and let them know if it’s valid or if it’s invalid.

# Basic data parsing and handling applications

The purpose of these questions is to make sure you're comfortable reading and writing data to files from Python, in addition to parsing data of different formats and using different data formats intelligently to create better solutions.

## Housing data

Write a program to ingest the `home_data.csv` file and list the 10 least expensive houses along with their ZIP codes, condition, and living square feet.

## Olympics

Write a program to ingest the `olympics.csv` file and list the top 3 countries who have won the most summer olympic medals and the top 3 countries who have won the most winter olypmic medals.

## Movies data

Write a program to ingest the `movies.csv` file and list top rated movie in each genre.

## Narcos - show info

Write a program to ingest the `narcos.json` file and list the TV show name, the genres that it fits under, and the average show rating.

## Narcos - episode info

Write a program to ingest the `narcos.json` file and list each episodes' name, season, and rating, sorted by the highest to lowest rating.
