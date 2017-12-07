---
title: "An Introduction to Combinatronics"
categories:
  - Maths
---

# What is Combinatorics?

Please consider the following problems:

*  How many possible sudoku puzzles are there?
*  Do 37 Londoners exist with the same number of hairs on their head?
*  In a lottery where 6 balls are selected from 49, how often do two winning balls have consecutive numbers?
*  In how many ways can we give change for £1 using only 10p, 20p, and 50p pieces?
*  How many ways are there of rearranging the letters in the word “ABRACADABRA”?


What do you notice about these problems?

First of all, unlike many mathematical problems that involve much abstract and technical language, they’re all easy to understand – even though some of them turn out to be frustratingly difficult to solve. This is one of the main delights of the subject.

Secondly, although these problems may appear diverse and unrelated, they mainly involve selecting, arranging, and counting objects of various types. In particular, many of them have the forms. Does such-and-such exist? If so, how can we construct it, and how many of them are there? And which one is the ‘best’?

The subject of combinatorial analysis or combinatorics (pronounced com-bin-a-tor-ics) is concerned with such questions. We may loosely describe it as the branch of mathematics concerned with selecting, arranging, constructing, classifying, and counting or listing things.

# Product Rule

If there is a sequence of K events with n1 ... nk possible outcomes, then the total number of outcomes for the sequence of K events is n1 x n2 x ... nk

It will be best to show this through an example.

## Example 1
In Kent, license plates are made up of two letters followed by 3 digits. How many possible license plates are there?

Well, the first letter has 26 possible letters and so does the second letter. The first digit has 10 possible choices for the first digit, 10 for the second and 10 for the third.

Therefore there is a total combination of:
26^2 * 10^3 = 676,000

# Disjoint Events

Two events are said to be disjoint if they cannot happen at the same time.

# The Sum Rule

If A and B are disjoint events and there are N possible outcomes for A and X possible outcomes for B then there are N + X possible outcomes for the event "**Either** A or B"

## Example 1

How many 3 digit numbers begin with 3 or 2?
It's best to get used to this notation. {0..9} means 0 through to 9, which is 10 numbers.
Anyway, back to the question.

We represent the first number, starting with a 3 as

3{0..9}{0..9}

So there is 1 * 10 * 10 for the first possible number.

For the second number starting with a 2, it is:

2{0..9}{0..9}

Which is 1 * 10 * 10 for the second possible number.

Then to find out how many 3 digit numbers begin with a 3 or 2 we do

(10 * 10) + (10*10) = 100 + 100 = 200 possible 3 digit numbers.


## Example 2

I want to take two pieces of fruit with me for lunch. I have three bananas, four apples and two pears.
How many ways can I select two pieces of fruit of different types?

We can split this question up into three parts:

Banana or Pear = 3 * 2 = 6
Banana or Apple = 3 * 4 = 12
Apple or Pear = 4 * 2 = 8

Note: Banana or pear = 3 * 2 is because there are 3 bananas and 2 pears.

then we just add them all together
6 + 12 + 8 = 26

# Set-Theoretic Interpretation

If A and B are disjoint events (that is, the union of A and B is equal to the empty set) then |A∪B| = |A| + |B|

# Fun problems to solve

## Problem 1

A computer password is a string of 8 charecters where each charecter is an uppercase or digit. Each password must contain at least one digit. How many different passwords are there?

So there are 8 charecters
``` _ _ _ _ _ _ _ _ ```

And each one is either an uppercase character or digit. We will make a variable to shorten it.
X = {A..Z or 0..9}
So there is 26 uppercase letters and 10 digits and we want to know what |{A..Z or 0..9}| is so using the above formula we could just do |A| + |B| which is just 26 + 10 = 36 possible outcomes for every charecter in the password.

But, there is a problem. There exists passwords which do not have numbers in them, at all. Becuase of this, we need to take them out of the data set. 

So, there are 36^8 possible password permutations. We know the alphabet is 26 letters long, so therefore there must be 26^8 passwords which only contain letters (pigeon hole principle). Now we need to take away.

36^8 - 26^8 = 2612282842880.

## Hacking Apple's Passwords

A more fun and useful problem. Apple's default password settings are one character has to be upper case, there has to be numbers and it has to be at least 7 characters long.


That means there is 26 * 2 possibilities for any given character in the password, so 52 possible outcomes and then add 10 as it could be a digit, 52^7 = 1028071702528

But we can guess some things. Firstly, the typical user will have a capital letter at the start of their password and most often they will only use lowercase after that. The lowercase charecters will consist of {a..b or 0..9} as it has to include a number somewhere.

{A..B}xxxxxx

So that's 26 + 10 = 36, therefore the password is now 26^1 * 36^6 = 56596340736.

Buttt we can guess more information. The user's password will start with a capital letter, contain only lower-case letters in it and end with a number. Do you have a password like this? Well, after this you might want to change it...

So, the format is:

{A..B}xxxxx{0..9}

Where x = {a..b}

Okay, so work this out one at a time.

26^1 * 26^5 * 10^1 = 3089157760.

The possibillities of passwords decreased by 300% by knowing some simple things about their password.

But wait, we can guess some more.

The password will likely be a word, followed by a number.

According to [this](wordfinder.yourdictionary.com/letter-words/6) there are 15,000 words that are 6 letters long.

So we know that the first section will be 15,000 and then it's followed by a random number, 0 to 9. So we have 15,000 * 10 = 150000.

A lot less than what was originally guessed. Knowing some basic information about a user, you can cut down the time it takes to hack their password by 3/4ths.

# Subtraction Rule

