---
title: "Wonderful World of Bionomial Coefficients"
categories:
  - Maths
---

# What is a Binomial Coefficient?

First, let's start with a binomial.
A binomial is a _polynomial_ with two terms typically in the format \\( (x + y) \\).

A binomial coefficient is raising a binomial to the power of n, like so \\( (x + y)^n \\)

# Binomial Therom

The Binomial Theorem is the expected method to use for finding binomial coefficients because it is how a computer would compute it.
The theorem is as follows:
$$ (x+y)^n = \sum_{k=0}^n {n \choose k} x^{n - k} y^k $$

Luckily for us, this formula is almost the same as another formula we've seen, according to [here](http://www.purplemath.com/modules/binomial.htm)

$$ (x+y)^n = \sum_{k=0}^n {n \choose k} = \frac{n!}{k!(n-k)!}$$

Yes, the combinations formula! 

Let's try an example.

## Example question

What is the coefficient of \\(x^6\\) in \\((1+x)^8\\)?

Simply plug this into the formula like so

$$ (x+y)^n = \sum_{k=8}^6 {8 \choose 6} = \frac{8!}{6!(8-6)!}$$

Note that whatever we want to find is the bottom number and the total number is on top.
40320 

$$ \frac{8!}{6!(8-6)!} = \frac{8*7*6*5*4*3*2*1}{6*5*4*3*2*1 * 2*1}$$ 

$$ = \frac{8*7}{2*1}$$

$$ = \frac{56}{2} = 28$$


# Pascal's Triangle

![Pascal's Triangle](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

Pascal's triangle is a triangle created by starting off with a 1, starting every line and ending every line with a 1 and adding the numbers above to make a new number; as seen in this gif.

No one could ever explain a maths topic as well as Numberphile, so here's a Numberphile video on it
https://www.youtube.com/watch?v=0iMtlus-afo
