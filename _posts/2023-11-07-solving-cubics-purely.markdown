---
layout: single
title: Trying to find the general 'cubic equation'
date: 2023-11-08 20:20
categories: maths equations
last_modified_at: 2023-11-08 20:45
---

Trust me, I've specially chosen the word *trying* in the title for a reason...

Finding ways of reducing seemingly complicated functions into something that becomes easy to solve is one thing I enjoy in maths, that is, the process of generalisation.

A famous example of this is perhaps the quadratic formula, which states that for a given polynomial degree 2, <span>$$ax^2+bx+c=0$$</span>, the solutions are given by <span>$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}.$$</span>

In this article, despite being confused about why some stuff is happening, I'll have a go at finding a commensurate solution to the general cubic equation, <span>$$x^3+ax^2+bx+c=0.$$</span>

---

First we want to get rid of the term in \\(x^2\\) so that the equation's a bit easier to work with. We can use a sneaky binomial trick here to get a part of the \\(x^3\\) term to negate the \\(x^2\\) term and that'll give us a new cubic in a different variable (but solving for this and undoing the transformation still gets us the solutions).

So, let's use the transformation \\(x=y-\frac{1}{3}a\\):

$$
\begin{align*}
\left(y-\frac{1}{3}a\right)^3 + a\left(y-\frac{1}{3}a\right)^2 + b\left(y-\frac{1}{3}a\right) + c &=0
\newline
\newline

y^3 + \left(a-a\right)y^2 + \left(\frac{1}{3}a^2-\frac{2}{3}a^2+b\right)y + \left(-\frac{1}{27}a^3 + \frac{1}{9}a^3 - \frac{1}{3}ab + c\right)&=0
\newline
\newline

\implies y^3 + \left(b-\frac{1}{3}a^2\right)y + \left(\frac{2}{27}a^3 - \frac{1}{3}ab + c\right)&=0.

\end{align*}
$$

Hence we have successfully transformed the general cubic into 'depressed cubic' form (without the \\(x^2\\) term). So now we have \\(y^3+Ay+B=0\\) where \\(A=b-\frac{1}{3}a^2\\) and \\(B=\frac{2}{27}a^3 - \frac{1}{3}ab + c\\), so are both constants, which is good.

---

This time we want to turn it into something we do know how to solve (maybe a quadratic...), so want to get rid of the linear term now too.

The substitution \\(y=u-\frac{A}{3u}\\) feels like it would work. Let's see:

$$
\begin{align*}

y^3+Ay+B&=0
\newline\newline

\left(u-\frac{A}{3u}\right)^3+A\left(u-\frac{A}{3u}\right)+B &= 0
\newline\newline

\left(  u^3-Au+\frac{1}{3u}A^2 - \frac{1}{27u^3}A^3 \right) + \left(Au - \frac{1}{3u}A^2\right) +B &=0
\newline\newline

u^3 - \frac{1}{27u^3}A^3 + B &= 0
\newline\newline

\implies 27u^6 + 27Bu^3 - A^3 &= 0
\end{align*}
$$

Which is just a quadratic in \\(u^3\\), and we can deal with that:

$$
\begin{align*}
u^3 &= \frac{-27B \pm \sqrt{27\left(27B^2 + 4A^3\right)}}{54}
\newline\newline

\implies u^3 &= -\frac{1}{2}B \pm \frac{\sqrt{3\left(27B^2 + 4A^3\right)}}{18}
\newline\newline

\implies u^3 &= -\frac{1}{2}B \pm \frac{\sqrt{27B^2 + 4A^3}}{6\sqrt{3}}
\newline\newline

\implies u &= \sqrt[3]{-\frac{1}{2}B \pm \frac{\sqrt{27B^2 + 4A^3}}{6\sqrt{3}}}
\end{align*}
$$

This is where I get *extremely* confused. For this depressed cubic, we've somehow gone totally wrong!! It doesn't work :(




