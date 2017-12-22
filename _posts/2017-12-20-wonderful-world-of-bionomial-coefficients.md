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

Luckily for us, Boris appeared to have forgot to mention that this formula is almost the same as another formula we've seen, according to [here](http://www.purplemath.com/modules/binomial.htm)

$$ (x+y)^n = \sum_{k=0}^n {n \choose k} = \frac{n!}{k!(n-k)!}$$





