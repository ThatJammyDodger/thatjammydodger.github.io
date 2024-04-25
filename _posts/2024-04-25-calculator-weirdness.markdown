---
layout: single
title: Calculator weirdness
subtitle: What is going on here?
date: 2024-04-23
categories: maths
header:
    teaser: /assets/images/thumbnails/latex-cover.jpg

toc: true
toc_label: "Thoughts"
toc_icon: "bars"
---
What is going on here? Join me as I try to figure out these odd happenings...

## What is it
This is all based on a question I came up against in an A level maths past paper. In all honesty, quite a routine question but one thing did intrigue me.

### Question

$$
\small\begin{equation}
\text{(i)} \hspace{0.5cm} \text{Use the substitution }x=u^2\text{ to find the exact value of }
\newline \int_0^4\frac{1}{2+\sqrt{x}}\text{d}x.
\end{equation}
$$

### Solving
We will use the substitution \\(u=x^2\\) such that the new limits are \\(u=2\\) and \\(u=0\\), with \\(\text{d}x = 2u \text{ d}u\\).

$$
\small\begin{align*}
\int_0^4\frac{1}{2+\sqrt{x}}\text{d}x &= \int_0^2\frac{2u}{2+\sqrt{u^2}}\text{d}u
\\ \\ &= 2\int_0^2\frac{u}{2+u}\text{d}u
\\\\ &= 2\int_0^2 1- \frac{2}{2+u}\text{d}u
\\\\ &= 2\left[u-2\ln|2+u|\right]^2_0
\\\\ &= 4-4\ln(2)
\\\\ &\approx 1.22741127776...
\end{align*}
$$

### What's weird?
At this point you may be thinking that this is all very straightforward, and you'd be right - it is. So what intrigues me?

Well, it's the what the calculator said when I went to check my answer.

You see, I trust my CASIO, and it has always respected that trust. However, on this occassion I felt let down somewhat :(. It has a handy feature allowing direct numeric evaluation of an integral which is pretty good for checking an answer on a piece of work. However, in this case, it came up with an answer that was wrong at the 10th significant figure (\\(1.227411277\\) instead). Hardly a major problem, I know, but crushing nonetheless.

Note that I refer to the CASIO fx-991EX in the above. I then retried it on my newer CASIO, the fx-991CW, and all went well, reaching the correct answer?!

Here are the results of my _very exhaustive_ testing:
![integral calculated](\assets\images\in_posts\calculator_post_apr_24\IMG_5965.jpg){:width="50%"}

^^ Direct integral evaluation, old vs new

![integral calculated](\assets\images\in_posts\calculator_post_apr_24\IMG_5966.jpg){:width="50%"}

^^ Integral result evaluation (same on both, correct)

Hopefully that explains my queasiness on this topic.

For the heck of it, I also tried a direct integral evaluation on my sister's old IB spec calculator (a TI-83 Plus designed in the '90s):
![integral calculated](\assets\images\in_posts\calculator_post_apr_24\IMG_5967.jpg){:width="50%"}

As you can see, the TI was just wildly wrong, correct to just 4sf :(.

### Trying to explain this stuff
Now let me just preface this by saying that I do not really know how the calculator does stuff, but the least I can do is provide a hypothesis. Any calculator experts or maths freelancers out there, please get in touch so I can fix this section (contact details on the homepage).

Calculators give the ln values presumably using some sort of expansion that has been reliable (and virtually uniform across models) for a long time, possibly something like [CORDIC](https://en.wikipedia.org/wiki/CORDIC). So that's why I think the correct value across all of them was given for \\(4-4\ln2\\).

Unfortunately, integrals are trickier. It is likely that the calculators use something like Simpson's or the trapizium rule to get their values (perhaps something a bit more proprietary/better too). Furthermore, the algorithms used for this should improve from generation to generation. Comparing how correct each calculator was by year of release gives:
1.  10 significant figures - 2022 (CASIO fx-991CW)
2.  9 significant figures - 2015 (CASIO fx-991EX)
3.  4 significant figures - 1999 (TI-83 Plus)

I suppose that sort of gives us our answer then, though I did hope that we could trust the integration feature on the calculators up to the number of sig figs given. I mean, if it knows there's a pretty high degree of error, it wouldn't hurt to just omit those last few digits then, would it??

## Conclusion
And there we have it, an overanalysis of something an ordinary person would have dismissed within seconds.

I'm pretty sure it comes down to how the integration approximations differ from calculator to calculator, both in terms of speed and accuracy, but it is undeniably useful even if marginally erroneous. Any further input from a potential reader would be nice to hear though!

Crediting the original question that brought this to the front of my mind: OCR H240/03 June 2018 Q5 (ii).

If you've read this far, thanks and check out some of my other mathsy bits like that thing with the scalar product or cubic equations.