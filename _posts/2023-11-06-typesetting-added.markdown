---
layout: single
title: Typsetting is here!
subtitle: (It didn't take a whole lot of effort to add to be honest)
date: 2023-11-05 21:25 +0000
categories: math, typesetting
---
After an entire two minute investigation into potential libraries, and based on nothing other than the library's sponsor list, this site's admin has decided to use <a href="http://www.mathjax.org/" target="_blank">MathJax</a> to implement mathematical typesetting around here.

I will be using this on future posts so that I can make my maths look professional even if iy isn't really. Upcoming features might include my take on the scalar product for vectors or using Tschirnhaus transformations to solve cubics. Or maybe some personal highlights from MAT 2023...

---

In any case, just to prove that I have done a thing, here is the quadratic formula for your entertainment:

<div>
$$ax^2+bx+c=0 \implies x=\frac{-b \pm \sqrt{b^2-4ac}}{2a}$$
</div>

:)

(Note to self: use "{<span>%</span> include math_jax.html <span>%</span>}" to add it to the pages where it is needed)

{% include math_jax.html %}