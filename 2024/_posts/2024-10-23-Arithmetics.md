---
layout: post
math: true
title: A non-informal inquery on arithmetics
---
Arithmetic works on numbers, so it is good for us to define numbers that it will eventually works on. 

There are a few types of numbers that comprises in elementary mathematics:

## 1. Natural Numbers

Natural numbers are numbers, that by definition of being nature as can be presented clearly in reality (as far as the ancient time). They are sometimes called positive numbers, albeit the calling has a larger scope. Denoted as $\mathbb{N}$, the set of natural numbers contains all numbers of the type: $$\mathbb{N}=\{ 0,1,2,\dots,n \}$$
Of which $n$ is supposed to stretch to infinity. The notion of infinity will be talked about later. 
If we want to remove the element $0$, then: $$\mathbb{N}\setminus \{ 0 \}= \mathbb{N}^{*}=\{ 1,2,\dots,n \}$$
Often times, we also call natural numbers as discrete numbers, since their values are constant, that is, there are no continuous variations in-between. 

## 2. Integers
Integers are the expansion of natural numbers, including negative numbers, the reversal of positive numbers. 
The notation is $\mathbb{Z}$, and is defined as: $$\mathbb{Z}=\{ -n,\dots,-2,-1,0,1,2,\dots,n \}$$
As we can see, the integers can be said to contains the reflection of the natural numbers over a given axis of order. The notion of negative numbers in itself is difficult to explain, hence we will try to explain it elsewhere. 

Since we also have negative numbers, we need to understand also why we set it as $-n \to 0 \to n$. We define the basic unit base value being $1$. We set the central, beginning point at $0$. Then, since numbers are the quantification of objects, we can say that the magnitude of the quantity that values have can be extract using the absolute value operation, $||$. We have: $$a>0, \lvert a \rvert = a$$
then $$-a<0, \lvert -a \rvert =a$$
Geometrically, we are seeing the magnitude of the distance from $0$ to the given value, hence we do not want to contain the signs. 

Hence, we see that they stretch out to infinity on both sides, then the distance unsigned will stretch eventually to infinity. On a number line, of which is the representation of numbers according to a fixed "distance", signs is used to differentiate between directions of expansions. 

Now, we denote the set of positive integers as $\mathbb{Z}^{+}$, and negative numbers as $\mathbb{Z^{-}}$. Since $0$ is a special number, of which we will talk about later, it does not being to either of the two sets. The set of integers without the special member $0$ is denoted $\mathbb{Z}^{*}$ Hence: $$\mathbb{Z} = \{ \mathbb{Z}^{+}, 0, \mathbb{Z^{-}} \}=\{ \mathbb{Z}^{+},\mathbb{Z}^{*},\mathbb{Z}^{-} \}$$
Negative numbers and positive numbers interacts with each other accordingly to rules: 

$$\forall a\in \mathbb{Z^{+}}, b \in \mathbb{Z^{-}}\longrightarrow\begin{cases}  
-b \in \mathbb{Z^{+}}\\ 
-a \in \mathbb{Z^{-}}\\
\text{if } a > b, a + b > 0 \\
\text{if } a < b, a + b < 0 \\
a - b = a + (-b) \in \mathbb{Z^{+}}  \\
ab \in \mathbb{Z^{-}} \\
a\cdot (-b) \in \mathbb{Z^{+}}\\
(-a)\cdot b \in \mathbb{Z^{+}} \\

\end{cases}$$
From those property we also can see then $$(-a)\cdot (-b)\in \mathbb{Z^{-}}$$ and many more. 
As you can see, we did not define the division operation for $a$ and $b$. We will then proceed with the division operation for now, to complete the ruleset theorem.

We define the division $\displaystyle{\frac{a}{b}}$ as valid for our comparison in $\mathbb{Z}$ if $$\forall a\in \mathbb{Z},b \in \mathbb{Z}^{*}, \frac{a}{b} = k, k \in \mathbb{Z}\quad (1)$$
The general division, of which are under another bigger set, $\mathbb{R}$ are given a little bit different: $$\forall a,k,r\in \mathbb{R},b\in \mathbb{R}^{+}, \frac{a}{b} = k+\frac{r}{b}$$
Which means that $$a=kb+r$$
Then we have with $(1)$: $$\forall a\in \mathbb{Z},b \in \mathbb{Z}^{*}\longrightarrow\begin{cases}
\displaystyle{\frac{a}{b}} > 0 & \text{ if } a > 0, b > 0 \\
\displaystyle{\frac{a}{b}} < 0 & \text{ if } a > 0, b < 0\text{ or } a < 0, b > 0    \\
\end{cases}$$
This then can be switched in comparison to $-a$ or $-b$ accordingly. Also, we also have $b\neq 0$ under every circumstances. This is called division by zero problem, and per arithmetic or modern arithmetic, it is not allow, or undefined.

The way of division is very confusing, of course, because of the fact that some fractions cannot be introduced or calculated and yields result valid of the set of numbers that it is in, except in larger parts. 

# 3. Rational Numbers
A rational number is a number that can be represented, or created, derived, from the ratio or fraction of two numbers: $$R=\frac{a}{b}, \forall a,b\in \mathbb{Z}, b \neq 0$$
Hence, we would like to have a formal definition for such number. 

> [!def] Rational Number
> Given a number $A$. $A$ is called a **rational number** if it is represented by two others integer, $a,b$ such that: $$\boxed{A= \frac{a}{b}, \forall a,b\in \mathbb{Z}, b\neq 0}$$
> 

The condition here is that the second integer representing the rational number (as well as irrational, for those that we encounter later on) is that $b\neq 0$. This is to prevent a very special case of mathematics, of dividing to 0. 

Every rational number representation in fractional form is either reducible fraction, or in its most standard, irreducible fraction is preferred. The notion of irreducibility would be introduced later on, because it is worthwhile for a whole section of itself. 

By the virtue of it, we can see that rational numbers are bigger than integers. Denoted $\mathbb{Q}$, we have by the language of set theory, $\mathbb{Z}\subset \mathbb{Q}$. Fractional numbers by division brings us, for example, some interesting numbers: $$\frac{1}{2}=0.5$$
both of which are ratio of different form. One would ask why we can represent it as being, $0.5$ and where does this notion applies. We would like to see it for the decimal system that we captured - it is by nature, scalable. What is meant by scalable is by the fact that for a number, a discrete number in reality, for example of the basic case, $1$, it is formulated using the decimal system of $10$, which means: $$1=1\cdot10^{0}+\sum^{\infty}_{n=1}0\cdot 10^{n}$$
Hence, we can also extend this definition down to, by borrowing the notion of exponential, to the negative numbers. What does this means is related to the definition of ratio and percentage, though, so we would like to also explain that first for what has been done. 

For a number of any numbers, a ratio can be either, the comparison of some metric, or the division of such numbers. For example, within the confinement of rational numbers, a ratio between two numbers: $$\text{ratio}=\frac{a}{b}$$
meaning comparing the magnitude of $a$ to $b$. Suppose that $a=1,b=4$, then the ratio would be $$\frac{a}{b}=\frac{1}{4}$$ of which means that $b$ is 4 times bigger than $a$. Now, by definition, too, ratio is also the act of division - the operation of which is quite confusing to be defined specifically. Hence, we can say that the fraction is telling us for, the division of $1$ into $4$ parts. We will eventually, be able to separate it to $0.25$ for each part, then $$\frac{1}{4}=0.25$$
How are we able to do it? Well, has something to do with the definition of ratio, and why it is related to division. While you are trying to solve for, how much value that can a number $a$ be multiplied - or added by itself how many times can get, up to a value of $b$, the division operation is the reverse of such multiplication operation. It asks for how much, given $b$ and $a$, will I need to multiply $a$ with to gain $b$. Therefore, it serves for the reverse purpose. Division, conveniently, contains in itself the definition of also, ratio. In fact, given an operation of division: $$\frac{b}{a}=x$$ the number $x$ itself is called the ratio of the two numbers. 

Coming back to the topic of interest, we kind of see the thing here. There is one fact about division and its representation in exponential form is being able to be represented by using negative exponent. That means, $$10^{-1}=\frac{1}{10}$$ of which is clearly seen. Of course, this align well with the formal introduction of self-multiplication as positive exponent. Further detail would be discussed later on. 
___
We will now explore some interesting features when talking about rational numbers.
For two rational numbers to be equal, we say that: $$\frac{a}{b}=\frac{c}{d}\iff ad=bc$$
If both fraction are in canonical form, or being irreducible fractions, then $$\frac{a}{b}=\frac{c}{d}\iff \begin{cases}
a=c \\
b=d
\end{cases}$$
Ordering relationship between rational numbers can be formulated as follow: $$\frac{a}{b} < \frac{c}{d}\iff ad<bc$$
If either denominator is negative, and in which case either numerator being both negative, then each fraction with negative denominator/numerator must be converted to its positive form. That is, $$\frac{a}{-b}< \frac{c}{-d}\iff \frac{a}{b} > \frac{c}{d}$$
The above rule applies, for even numerator case. 
## 3.1 Mathematical Operation on $\mathbb{Q}$
### Addition
Two fraction can be added as follow: $$\frac{a}{b}+\frac{c}{d}=\frac{ad+bc}{bd}$$
If both fractions are in canonical form, the result is in canonical form iff $b$ and $d$ are coprime integers. (GCD of both of them is 1). 
### Subtraction
Defined as follow: 
$$\frac{a}{b}-\frac{c}{d}=\frac{ad-bc}{bd}$$
Similarly, If both fractions are in canonical form, the result is in canonical form iff $b$ and $d$ are coprime integers.
### Multiplication
The rule for it is as follow: $$\frac{a}{b}\cdot \frac{c}{d}=\frac{ad}{bd}$$
of which will results in a reducible fraction even if both fractions of the LHS is irreducible (or canonical). 



