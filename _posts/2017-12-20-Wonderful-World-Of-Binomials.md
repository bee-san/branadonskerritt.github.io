---
title: "Wonderful World of Bionomial Coefficients"
categories:
  - Maths
---

# What is a Binomial Coefficient?

First, let's start with a binomial.
A binomial is a _polynomial_ with two terms typically in the format \\( (x + y) \\).

A binomial coefficient is raising a binomial to the power of n, like so \\( (x + y)^n \\).

We all remember from school that \\( (a + b)^2 = a^2 + 2ab + b^2\\) but what if I was to ask for \\((a+b)^18 \\)? This is where the binomial formula comes in handy. 

# Binomial Therom

The Binomial Theorem is the expected method to use for finding binomial coefficients because it is how a computer would compute it.
The theorem is as follows:


$$ (x+y)^n = \sum_{k=0}^n {n \choose k} x^{n - k} y^k $$

Luckily for us, this formula is the same as another formula we've seen, according to [here](http://www.purplemath.com/modules/binomial.htm)

$$ (x+y)^n = \sum_{k=0}^n {n \choose k} = \frac{n!}{k!(n-k)!}$$

Yes, the combinations formula! 

Let's try an example.

## Example question

What is the coefficient of \\(x^6\\) in \\((1+x)^8\\)?

Simply plug this into the formula like so

$$ (x+y)^n = \sum_{k=6}^8 {8 \choose 6} = \frac{8!}{6!(8-6)!}$$


$$ \frac{8!}{6!(8-6)!} = \frac{8*7*6*5*4*3*2*1}{6*5*4*3*2*1 * 2*1}$$ 

$$ = \frac{8*7}{2*1}$$

$$ = \frac{56}{2} = 28$$

Something that may confuse people is, how do we work out what n and k are? Well, we have n objects overall and we want to choose k of them. 

# Pascal's Triangle

![Pascal's Triangle](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

Pascal's triangle is a triangle created by starting off with a 1, starting every line and ending every line with a 1 and adding the numbers above to make a new number; as seen in this gif.

No one could ever explain a maths topic as well as Numberphile, so here's a Numberphile video on it

<iframe width="560" height="315" src="https://www.youtube.com/embed/0iMtlus-afo" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

Here's the Pascal's Triangle we want.
![triangle](https://i.stack.imgur.com/C93ol.png)

Pascal's triangle always starts counting from 0, so to solve \\(8\choose 6\\) we simply count 8 rows down, then 6 across. So the row here is the line of the number 1's on the left hand side, and we start counting from 0. So the eigth row is the one that starts with 1, 8. Notice how the second inner column defines what row we're on. 

Now we count 6 across which is... 28. We just found the binomial coefficient using a super neat and easy to draw up triangle. Of course, the hardest part is adding together all the numbers and if the coefficient is large it may be easier to just use the Binomial theorem, but this method still exists and is useful if you've forgotten the binomial theorem.


# What is LaTeX?

LaTeX, as described on the website is:
>LaTeX is a high-quality typesetting system; it includes features designed for the production of technical and scientific documentation. >LaTeX is the de facto standard for the communication and publication of scientific documents. 

More importantly, LaTeX is not a word processor like Microsoft Word. Whereas Mircosoft Word is mainly about the appearence and look of the document, LaTeX encourages writers to not worry so much about the appearence of their document and more on the content.

LaTeX is the standard of creating professional and high quality documents in STEM fields or in academia. 

LaTeX was created by [Donald Knuth](https://en.wikipedia.org/wiki/Donald_knuth), one of the most famous computer scientists. After being disaappointed with the quality of his The Art of Programming series, he set out to create a typesetting system called Tex. Later on, LaTeX was born as a revival of Tex which allowed for a simpler approach to creating documents.

LaTeX is amazing at:
* Dealing with mathematical formulae
* [Bibliographies and references](https://www.sharelatex.com/learn/Bibliography_management_with_bibtex)
* Focuses on content
* Tables and illustrations

LaTeX is not so good at:
* Spellchecking
* Collaborative editing
* Compatiability
* Has a small barrier to entry, meaning new users may be scared off.

# Creating your first LaTeX document

Let's create a document and go over it in plain english.
```LaTeX
\documentclass{article}
\title{Freecodecamp and Medium}
\author{Brandon Skerritt}
\date{25th December 2017}
\begin{document}
   \maketitle
   Hello world!
\end{document}
```

So the document class is what the document is. In this case, this document is an article. An article much like this Medium article or a scientific paper. Another popular class is Beamer which is used for presentations.

The second part is the title of the document. Pretty self explanatory.
The part after that is the author's name.
After that is the date of the document.

You may begin to see that LaTeX uses tags, much like HTML. In fact, both of these are markup languages. You create a \begin{document} tag that contains the body and content of the document, much like the ```<body>``` tag in HTML.

The \maketitle tag makes the text into a title.

We get this as a [result](https://latexbase.com/d/1a925e91-60f4-4570-8511-580f422ee8c5)
```
$$
\documentclass{article}
\title{Freecodecamp and Medium}
\author{Brandon Skerritt}
\date{25th December 2017}
\begin{document}
   \maketitle
   Hello world!
\end{document}
$$
```
You've now made a LaTeX document, yay! Let's explore some more.

## Mathematical Formulae

Since mathematics is one of the main uses of LaTex, let's create some mathematics.
Let's say we have a therom, like the Binomial Therom. How do we create it in LaTeX?
$$ (x+y)^n = \sum_{k=0}^n {n \choose k} x^{n - k} y^k $$

Well


