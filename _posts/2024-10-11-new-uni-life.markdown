---
layout: single
title: New to uni... new life...
subtitle: Fun stuff right
date: 2024-10-11
categories: maths life
header:
    teaser: /assets/images/thumbnails/dot-cover.jpg

toc: false
---

Settling into the UK and Europe's \#1[^1] university for a pretty fun course...

## Imperial
Now, aside from their massive rebrand, Imperial is an astonishing university from my perspective. It's the only one in the country that focusses on **real subjects**. Take that Oxbridge (just kidding 😂), but to be fair we do need more STEM exlusive unis around here... 

My accommodation is a bit far away, but in fairness it wasn't really sustainable for me, as a student, to live in Central London.

I won't get too much into it here, but freshers' has also been quite an experience.

## JMC
For those of you wondering, my course is known here as JMC.

*Why JMC?*

> Honestly, I couldn't tell you exactly why I chose it, except for the fact that I'm alright at maths and programming appeals to me.

Now for the really big question...

*Why on earth do people call it 'JMC'?*

> Joint Mathematics and Computing. Someone probably decided to emphasise the 'joint' aspect and it just stuck I suppose.

> On a side note, I also seem to have stumbled into a Computing Entrance Scholarship, which is nice.

### Modules
I study quite a few modules (and annoyingly, for each module they're worth fewer degree credits compared to just doing either one of the respective disciplines alone despite virtually identical exams) including:
- Computing Practical 1
- Intro to Uni Maths Parts I & II
- Logic and Reasoning
- Linear Algebra and Groups
- Analysis
- Calculus and Applications
- Graphs and Algorithms

Several of these, I am really looking forward to!

Something I've heard though is that the workload is considerable, especially when compared to any other undergrad course here.

This is a big cause of excitement for me, though perhaps it shouldn't be...

### Beyond learning
Yep, so much opportunity here! Plus the social life is really really good!!!!!!!!

Just ignore anyone who says anything else. The vibes here are great :)

Academics and socials together, awesome uni and I would really implore anyone who realistically can to apply!

### So far in maths
As I'm now about halfway through IUM, I can say honestly that it's a real step up from A level. The pace is on another level and is so much more individually led.

I quite like it this way in all honesty.

The content itself is also really different (even from STEP) - everything is very much from the ground up, and we've spent the last few lectures going over propositional logic, functions, and binary relations.

While sounding intimidating, these topics are something you grow into.

And from Monday, we're going to build up the natural numbers using the `Peano axioms`. Look into these if you're at A level and interested! It's cool stuff.

### The computer science part
Haskell (a functional language) is what we're doing at the moment - basically learning about all the functional ideas from the ground up.

I won't go much into it as it's probably beyond the scope of this post, but (for fun) here's an example function in Haskell for sorting jumbled lists:
```
quicksort :: [Int] -> [Int]
quicksort [ ] = [ ]
quicksort (x : xs) = quicksort [ n | n <- xs, n <= x ]
                     ++ [ x ]
                     ++ quicksort [ n | n <- xs, n > x]
```
Key features of Haskell include:
- Type signatures (but can be implicit)
- Pattern matching and guards (though I didn't use any guards here)
- Recursion and list comprehensions for any kind of "looping"
- It is an **expression**-based language

The other main programming paradigm that you're probably used to is known as "imperative".

It may also surprise you to hear that languages you know and love have functional aspects to them, such as Python and the Javascript family, even if not strictly functional languages.

*A quick history lesson*
> The two main programming paradigms, imperative and functional originated with Turing and Church respectively. For Turing, from Turing machines, and Church lambda calculus. In fact the two are identical at a fundamental level, but very different ideas used in actual use.

On a side note, the lecturer for this, Jamie, is absolutely great! He explains stuff well and answers questions without leaving much room for doubt. 

### Over and out
Well I'll leave it there for now. Thanks for reading, and although I have less time these days, I will try to leave the occasional post up here.

[^1]: [As per the QS World University Rankings 2025](https://www.topuniversities.com/world-university-rankings)