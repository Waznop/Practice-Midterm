# Practice Midterm

**THIS IS THE PRACTICE MIDTERM. IT DOES NOT COUNT FOR POINTS.**

**The following words will be on the top of the real midterm:**

Read all instructions before you begin.
* This exam is open-notes. You may look at your notes, a textbook, the course materials, or any other online resource.
* You may NOT ask anyone for help. You must complete the exam entirely on your own. Asking for help or answers from others counts as cheating and will result in getting a 0 on the entire midterm.
* If an emergency occurs during the exam, you must notify the instructors by email as soon as possible.

## Programming section

This section has a total of 60 points. The written section which is entirely on Gradescope has a total of 40 points.

For the programming section, each of the 3 questions gives you a maximum of 30 points. **We will only count your best 2 out of 3 questions**. This means that you can get 60/60 by only completing 2 questions. This also means that you can't get over 60/60 even if you attempt all 3 questions. Submit your code to `Practice Midterm - Programming` on Gradescope.

## Question 1: fib.cpp

[Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number) are numbers that satisfy the following rules:
* The first Fibonacci number is 0.
* The second Fibonacci number is 1.
* All subsequent Fibonacci numbers are the sum of the previous two.
  * For example, the 3rd Fibonacci number is 0 + 1 = 1.
  * The 4th Fibonacci number is 1 + 1 = 2.
  * The 5th Fibonacci number is 1 + 2 = 3.
  * The 6th Fibonacci number is 2 + 3 = 5.
  * The 7th Fibonacci number is 3 + 5 = 8.

### Program requirements

Write the `fib.cpp` program to do the following:

1. Ask the user `"How many Fibonacci numbers would you like? (0-40)"` (+ newline) and store the answer.
    * You can assume the answer will be valid (int between 0 and 40).
1. Print out that many Fibonacci numbers, one per line, starting from the first one (0).

### Example expected output

Input: 3
```
$ ./a.out
How many Fibonacci numbers would you like? (0-40)
3
0
1
1
```

Input: 7
```
$ ./a.out
How many Fibonacci numbers would you like? (0-40)
7
0
1
1
2
3
5
8
```


## Question 2: cherry.cpp

The [National Cherry Blossom Festival](https://nationalcherryblossomfestival.org/) is an event that occurs every year during the cherry blossom season. For the purpose of this question, we'll assume it always starts on March 20 and ends on April 17.

### Program requirements

Write the `cherry.cpp` program to do the following:

1. Ask the user `"What's the date in YYYY-MM-DD format? (eg. 2021-10-04)"` (+ newline) and store the answer.
    * You can assume the answer will be valid (correct YYYY-MM-DD format).
1. If the date is between March 20 and April 17, compute how many days it's been since the festival started and store it in a variable `day_num`.
    * Then, print `"It's day <day_num> of the National Cherry Blossom Festival!"` (+ newline).
    * Eg. March 20 would be day 1, April 1 would be day 13.
1. Otherwise, print `"Aw, you missed the National Cherry Blossom Festival..."` (+ newline).

**Hint**: You can convert a string to an int by using `stoi`.

```
string num_str = "023";
int num = stoi(num_str);  // the value of num is 23
```

### Example expected output

Input: 1996-03-20
```
$ ./a.out
What's the date in YYYY-MM-DD format? (eg. 2021-10-04)
1996-03-20
It's day 1 of the National Cherry Blossom Festival!
```

Input: 2000-04-01
```
$ ./a.out
What's the date in YYYY-MM-DD format? (eg. 2021-10-04)
2000-04-01
It's day 13 of the National Cherry Blossom Festival!
```

Input: 2021-10-04
```
$ ./a.out
What's the date in YYYY-MM-DD format? (eg. 2021-10-04)
2021-10-04
Aw, you missed the National Cherry Blossom Festival...
```

## Question 3: game.cpp

[Blackjack](https://en.wikipedia.org/wiki/Blackjack) is a very popular casino game. We will implement a simpler version of it for this question. Here are the rules:

* You start with a total of 0.
* You can `"hit"` as many times as you want to add a random number between 1 and 11 to your total.
* You can `"stay"` to stop.

Your goal is to get as close to a total of 21 as possible without exceeding it.
* If you get 21, you win.
* If you exceed 21, you lose.
* If you `"stay"` before hitting 21, consider that a highscore to beat for next time.

### Program requirements

Write the `game.cpp` program to do the following:

1. Ask the user `"Input a seed for random number generation."` (+ newline) and set the answer as the random seed.
    * This has already been done for you.
1. Declare a variable `total` and set it to 0.
1. Print `"You have a total of <total>"` (+ newline).
1. Ask the user `"Would you like to hit or stay?"` (+ newline) and store the answer.
    * You can assume the answer will be valid (`"hit"` or `"stay"`).
1. If the user chooses `"hit"`, add a random number between 1 and 11 to `total`.
    * You can do so with `total += rand() % 11 + 1;`.
    * If the `total` is now 21, print `"You win with a total of <total>."` (+ newline).
    * If the `total` now exceeds 21, print `"You busted with a total of <total>."` (+ newline).
    * Otherwise, go back to step 3.
1. If the user chooses `"stay"`, print `"You stayed with a total of <total>."` (+ newline).

**Hint**: You can get a refresher on how `rand()` works [here](https://docs.google.com/presentation/d/1PCJ6hKaE1KeppcHSm-Edk-5EYa794QbemHxwkIXHJQk/edit#slide=id.gf1056ba6d1_0_4).

### Example expected output

Input: 0 hit stay
```
$ ./a.out
Input a seed for random number generation.
0
You have a total of 0.
Would you like to hit or stay?
hit
You have a total of 7.
Would you like to hit or stay?
stay
You stayed with a total of 7.
```

Input: 1 hit hit hit
```
$ ./a.out
Input a seed for random number generation.
1 
You have a total of 0.
Would you like to hit or stay?
hit
You have a total of 7.
Would you like to hit or stay?
hit
You have a total of 18.
Would you like to hit or stay?
hit
You busted with a total of 25.
```

Input: 99 hit hit hit hit hit
```
./a.out
Input a seed for random number generation.
99
You have a total of 0.
Would you like to hit or stay?
hit
You have a total of 4.
Would you like to hit or stay?
hit
You have a total of 7.
Would you like to hit or stay?
hit
You have a total of 15.
Would you like to hit or stay?
hit
You have a total of 18.
Would you like to hit or stay?
hit
You win with a total of 21.
```

## Rubric

* (60 points) Programming
  * (30 points each) best 2 of `fib.cpp`, `cherry.cpp` and `game.cpp`
    * 1 point for writing code that compiles
    * 1 point for removing all TODOs
    * 1 point for inscribing your name
    * 3 points for complying to coding style rules
    * 24 points for the program behaving properly
* (40 points) Written – see Gradescope for point breakdowns
