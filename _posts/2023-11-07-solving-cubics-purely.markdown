---
layout: single
title: Trying to find the general 'cubic equation'
date: 2023-11-24 20:20
categories: maths equations
last_modified_at: 2023-11-26
header:
    teaser: /assets/images/thumbnails/cubics-pexels-stock.jpg

toc: true
toc_label: "Cubic-ing"
toc_icon: "bars"
---
<script>
    MathJax = {
        chtml: { displayAlign: 'left' }
    };
</script>
Trust me, I've specially chosen the word *trying* in the title for a reason...

---
# Why?

Finding ways of reducing seemingly complicated functions into something that becomes easy to solve is one thing I enjoy in maths, that is, the process of generalisation.

A famous example of this is perhaps the quadratic formula, which states that for a given polynomial degree 2, <span>$$ax^2+bx+c=0$$</span>, the solutions are given by <span>$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}.$$</span>

In this article, despite being confused about why some stuff is happening, I'll have a go at finding a commensurate solution to the general cubic equation, <span>$$x^3+ax^2+bx+c=0.$$</span>

<br>

# Getting started
## Depressing the cubic

First we want to get rid of the term in \\(x^2\\) so that the equation's a bit easier to work with. We can use a sneaky binomial trick here to get a part of the \\(x^3\\) term to negate the \\(x^2\\) term and that'll give us a new cubic in a different variable (but solving for this and undoing the transformation still gets us the solutions).

So, let's use the transformation \\(\small{x=y-\frac{1}{3}a}\\):

$$
\small\begin{align}
&\left(y-\frac{1}{3}a\right)^3 + a\left(y-\frac{1}{3}a\right)^2 + b\left(y-\frac{1}{3}a\right) + c =0
\newline
\newline

&{y^3} + \small\left(a-a\right)y^2 + \left(\frac{1}{3}a^2-\frac{2}{3}a^2+b\right)y + \left(-\frac{1}{27}a^3 + \frac{1}{9}a^3 - \frac{1}{3}ab + c\right)=0
\newline
\newline

&{y^3} + \left(b-\frac{1}{3}a^2\right)y + \left(\frac{2}{27}a^3 - \frac{1}{3}ab + c\right)=0.

\end{align}
$$

Hence we have successfully transformed the general cubic into 'depressed cubic' form (without the \\(\small{x^2}\\) term). So now we have \\(\small{y^3+Ay+B=0}\\) where \\(\small{A=b-\frac{1}{3}a^2}\\) and \\(\small{B=\frac{2}{27}a^3 - \frac{1}{3}ab + c}\\), so are both constants, which is good.


## Reducing it further

This time we want to turn it into something we do know how to solve (maybe a quadratic...), so want to get rid of the linear term now too.

The substitution \\(y=u-\frac{A}{3u}\\) feels like it would work. Let's see:

$$
\small\begin{align*}

y^3+Ay+B &=0
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
\small\begin{align*}
u^3 &= \frac{-27B \pm \sqrt{27\left(27B^2 + 4A^3\right)}}{54}
\newline\newline

\implies u^3 &= -\frac{1}{2}B \pm \frac{\sqrt{3\left(27B^2 + 4A^3\right)}}{18}
\newline\newline

\implies u^3 &=  \frac{1}{18} \left( \pm \sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)
\newline\newline

\implies u &= \sqrt[3]{\frac{1}{18} \left( \pm \sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}
\end{align*}
$$

## Getting *all* the roots

But we also need to take roots of unity to find the other two solutions for \\(u\\) from this. Multiplying the above by \\(\small{e^{\frac{2i\pi}{3}}=-\frac{1}{2}+\frac{\sqrt{3}}{2}i}\\) and \\(\small{e^{\frac{4i\pi}{3}}=-\frac{1}{2}-\frac{\sqrt{3}}{2}i}\\) for the other two roots gives: 

$$
\small\begin{align*}

u &= \left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left( \pm \sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}
\newline\newline
u &= \left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left( \pm \sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}

\end{align*}
$$



For now, let's just take it for granted that each pair of values for \\(u\\) given by these new formulae return the same value of \\(y\\) regardless of the state of the \\(\pm\\) symbol (i.e., a total of 3 possibly different values). I've done a bit of playing around and this feels true, plus the proof is probably super complicated so I'm not going to even try it here. Maybe in future if I understand it and ever decide to return.

Anyway, now using this assumption we have exactly 3 values of \\(u\\) in terms of \\(A\\) and \\(B\\) only, that will eventually give us 3 values of our original \\(x\\). Substituting back into \\(y=u-\frac{A}{3u}\\) gives:

$$
\small\begin{align*}

y &= \left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)} - \frac{A}{3\left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}}\newline\newline
y &= \sqrt[3]{\left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)} - \frac{A}{3\left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}}\newline\newline
y &= \sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)} - \frac{A}{3\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}}

\end{align*}
$$

---
# General solution

Finally, all we now need to do is to make \\(x\\) the subject again and plug in all the previous expressions. Doing this, we eventually obtain (I *really* hope correctly):

\\(\small\textbf{The general solution to the general cubic equation: }  \\)
\\(\small{x^3+ax^2+bx+c=0}\\)

\\(\small\textnormal{Firstly, find these constants: }\\)
\\(\small{A=b-\frac{1}{3}a^2 \hspace{0.5cm}\textnormal{ and }\hspace{0.5cm} B=\frac{2}{27}a^3 - \frac{1}{3}ab + c }\\)

$$\scriptsize\begin{align*}
\implies x &= \left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)} - \frac{A}{3\left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}} -\frac{1}{3}a

\newline\newline
\implies x &= \left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)} - \frac{A}{3\left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}}-\frac{1}{3}a

\newline\newline
\implies x &= \sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)} - \frac{A}{3\sqrt[3]{\frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right)}}-\frac{1}{3}a

\newline\newline
\end{align*}$$


## Trying it out

Let's try it out on a few cubics then, one with 1 real root and one with 3 real roots.

$$
\small\begin{align*}

1.\hspace{0.5cm} & \textnormal{Find all }x\textnormal{ such that }x^3-9x^2+16x-14=0.
\\
\\ &\text{Solution using the equations derived above for the solutions of a cubic:}
\\& A=16-\frac{(-9)^2}{3}=-11
\\& B=\frac{2}{27}(-9)^3-\frac{1}{3}(-9)(16)-14 = -20
\\& \sqrt{27B^2+4A^3} = \sqrt{5476} = 74
\\& \frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right) = \frac{74\sqrt{3}+180}{18} =\frac{37}{9}\sqrt{3} + 10
\\& \sqrt[3]{\frac{37}{9}\sqrt{3} + 10} = \frac{1}{3}\left(6+\sqrt{3}\right)
\\\\& x = \sqrt[3]{\frac{37}{9}\sqrt{3} + 10} + \frac{11}{3\sqrt[3]{\frac{37}{9}\sqrt{3} + 10}} - \frac{1}{3}(-9)
\\&= \frac{1}{3}\left(\sqrt{3}+6\right) + \frac{11}{\sqrt{3}+6} +3
\\&=\frac{6+\sqrt{3}}{3} + \frac{6-\sqrt{3}}{3} + 3
\\&= 2+2+3 \implies x=7 \text{ is one root.}
\\\\&x=\frac{1}{3}\left(-\frac{1}{2}\pm\frac{\sqrt{3}}{2}i\right)\left(\sqrt{3}+6\right)+\frac{11}{\left(-\frac{1}{2}\pm\frac{\sqrt{3}}{2}i\right)\left(\sqrt{3}+6\right)} + 3
\\&= \frac{(-6-\sqrt{3})\pm(3+6\sqrt{3})i}{6} - \frac{11\pm11\sqrt{3}i}{2(\sqrt{3}+6)} +3
\\&= \frac{(-6-\sqrt{3})\pm(6\sqrt{3}+3)i}{6} - \frac{(6-\sqrt{3})\pm(6\sqrt{3}-3)i}{6} +3
\\&= 3+\frac{-12\pm6i}{6}
\\&= 3-2\pm i \implies x=1\pm i \text{ are the other two roots.}
\\\\& \text{Hence, the three roots of this equation are }
\\&x=7,\hspace{0.5cm} x=1+i, \hspace{0.5cm}x=1-i\hspace{1cm}\text{as required.}


\newline\newline\newline\newline
2.\hspace{0.5cm} & \textnormal{Find all }x\textnormal{ such that }x^3-3x^2-4x+12=0.
\\
\\&\text{Solution:}
\\&A=-4-\frac{(-3)^2}{3} = -7
\\&B=\frac{2}{27}(-3)^3-\frac{1}{3}(-3)(-4) +12 = 6
\\&\sqrt{27B^2+4A^3} = \sqrt{-400} = 20i
\\& \frac{1}{18} \left(\sqrt{3}\sqrt{27B^2 + 4A^3} - 9B \right) = \frac{20\sqrt{3}i-54}{18} = -3+\frac{10\sqrt{3}}{9}i=\frac{7\sqrt{21}}{9}e^{\left(\pi-\arctan\left({\frac{10}{9\sqrt{3}}}\right)\right)i}
\\& \sqrt[3]{\frac{7\sqrt{21}}{9}e^{\left(\pi-\arctan\left({\frac{10}{9\sqrt{3}}}\right)\right)i}} = \frac{\sqrt{21}}{3}e^{\frac{1}{3}\left(\pi-\arctan\left({\frac{10}{9\sqrt{3}}}\right)\right)i} \approx 1+1.154700538379i
\\& x=1+1.154700538379i+\frac{7}{3(1+1.154700538379i)}+1 = 3 \implies x=3 \text{ is one root.}
\\&\text{For another root:}
\\&x = \left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)(1+1.154700538379i) + \frac{7}{3\left(-\frac{1}{2}+\frac{\sqrt{3}}{2}i\right)(1+1.154700538379i)} + 1
\\&=-2 \implies x=-2 \text{ is another root.}
\\\\&\text{For the last root:}
\\&x = \left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)(1+1.154700538379i) + \frac{7}{3\left(-\frac{1}{2}-\frac{\sqrt{3}}{2}i\right)(1+1.154700538379i)} + 1
\\&=-2 \implies x=2 \text{ is the last one.}
\\\\& \text{Hence, the three roots of this equation are }
\\&x=3 \text{ and } x=\pm2\text{ as required.}
\end{align*}
$$


## Reflections

**Woohoo** 🥳

But just a few things:
- Yes, I definitely used WolframAlpha and my Casio to crunch some of the numbers which admittedly defeats the whole point.
- Sorry about capitulating and using approximated numbers near the end - the exact values got pretty nasty.
- I picked these equations to start with, knowing that the solutions would be nice numbers as something to look forward to.
- So cool in the last example how all those complex numbers in the expression led to totally real roots!

More generally, I concede that I got quite stuck on deriving this several times and considered giving up at times. Took longer than it should have for me to spot that I needed to take roots of unity for the two other solutions as well.

Other than that, pretty cool don't you think!

A rewarding, even if somewhat frustrating, experience on the whole.