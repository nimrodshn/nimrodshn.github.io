+++
title = 'The number of binary strings on $n$ letters with no two consequitive ones'
date = 2025-12-02
draft = false
+++

This question is from a [lecture](https://www.youtube.com/watch?v=uynuxg0kRHo) by Prof. Gil Cohen that popped on my YT feed (To my discredit, I watch YT on my free time..).

__Question:__
"*How many binary strings on $n$ letters are there with no two consequitive ones?*"

__Observations:__
1. Naivly, For any $n$, if the number of 1s is strictly larger than $n/2$ than by the pigenhole principle we surely have two consequitive ones.
3. But ofcourse we can have consequitive 1s when the number of 1s is strictly lower than $\frac{n}{2}$. (e.g. 01100).

__Some simple examples:__
1. $n=1$, than we have 2 strings trivially.
2. $n=2$, than we have 3 strings - 10, 01, 00.
3. $n=3$, than we have 5 strings - 010, 101, 100, 001, 000.

These look like Fibonnachi's! (if we set $a_0=1$).

Why does this work? Lest take for example $n=3$: If the first digit is 0 we are free to choose from any of the legal strings of the case $n=2$ for the remaining digits.

Otherwise, the first digit is 1 so it must be followed by a *zero* and we use the rest of the legal strings for $n=1$. All in all we get $a_3=a_2+a_1=3+2=5$.

I suppose we can use the same reasoning to prove this claim by induction.