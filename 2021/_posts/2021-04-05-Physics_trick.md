---
layout: post
math: true
title: Physics trick.
category: 
    - physics
    - incomplete
---

While looking for mathematics videos, I stumbled upon a video, dubbed "S-Tier Acrobatic Calculus that Physicists do" of which I was pleasantly surprised by what is presented in the video. 

The video center around the derivation of the Taylor's expansion for $e^x$, of which we have the general form as $${\displaystyle e^{x}=1+x+{\frac {x^{2}}{2!}}+{\frac {x^{3}}{3!}}+{\frac {x^{4}}{4!}}+\cdots =\sum^{\infty}_{i=1} \frac{x^i}{i!}}$$

Here's how the video proceed to come up with the result (in a pretty carefree tone): 

> Let's say that I forgot the Taylor's expansion of $e^x$, but I remember that it is the only function whose derivative ${e^{x} }'$ and integral $\int e^x$ are both itself. Let's start with the integration form: $$e^x = \int e^x \: dx$$ as someone who is really good at calculus, I don't care about the lower bound of upper bound. In fact, I don't care about the $dx$, so let's remove it: $$e^x = \int e^x$$
> Much better. Now I can move everything to the left: $$e^{x}-\int e^{x} = 0 $$
> which I now have 1 minus integration sign, that is $$\left( 1-\int    \right) e^{x}=0$$
> and I am also free to left multiply the inverse: $$e^{x}=\left( 1-\int  \right)^{-1}\cdot 0$$
> Now, we notice that $$(1-x)^{-1}=\frac{1}{1-x}=1+x+x^{2}+x^{3}+\dots$$
> This looks familiar, doesn't it? "As someone with a physics background, I can't resist expanding anything that is expendable", then for our case $$\frac{1}{1-\int   } = 1 + \left( \int \right) + \left(\int\right)^{2}+\left(\int \right)^{3}+\dots$$
> This looks very promising. Let's start the calculation: $$e^{x}= \left(1+\int+\left(\int\right)^{2}+\left(\int\right)^{3}+\dots\right)\cdot 0$$
> The first term is zero. But the second term? Is it also zero? No, because we don't have $dx$. That means it is not the normal integral that takes zero as intergrand, it is the **operation integral** $$\int \left( 0  \right) $$ that applies on 0. So what's the result? It is easier to think from the opposite side. Its derivative is 0, therefore it is a constant. As someone with a physics background, that constant must be 1: $$e^{x}=0 + 1+ \left(+\left(\int\right)^{2}+\left(\int\right)^{3}+\dots\right)\cdot 0$$
> Similarly, I am looking for the value whose derivative is one: it's $x$. Continuing this, for example value whose derivative is $x$, I found that it is $\frac{x^{2}}{2!}$. Then this chain of logic continues: $$e^{x}=0+1+x+{\frac {x^{2}}{2!}}+{\frac {x^{3}}{3!}}+{\frac {x^{4}}{4!}}+\cdots$$ which recovers the Taylor's expansion of $e^{x}$. 

This seems to me, is between absurdity, but also logically reasonable. But what I found interesting is the remark of the OP: 
> At the end of the video, I want to make some clarifications. With proper definition everything I have done so far is legitimate. 

Which is quite interesting considering which foundation and definitions would make this possible. I do not have adequate knowledge to be able to figure this out. I also read a person said that 
> This actually has rigorous justifications if you work in an appropriate function space. For example, if you work in $L^{2}$ , the norm of the integral operator is less than one, so the expansion of the operator in the series is justified. 

In another person's words, he pointed it to operation theory, and the others about functional analysis and holomorphic functional calculus. However, I lack the knowledge to fully clarify these claims or explanation for myself. 

What is going on for this example, and what is the "appropriate and proper" definition and foundation for such derivation?