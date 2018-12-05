---
layout: post
title: Static vs. Extern keyword
tags: [extern, static, c, c++]
excerpt_separator: <!--more-->
---

## Intro

One of the most confusing and forgettable concepts is the concept of **"extern"** and **"static"** keyword.

It could be applied only to me, but I'm just leaving some notes for the others who would get confused like me.
There are many long, wordy explanation and description about this, but i couldn't know them in my bones.

## Extern vs. Static

The core concept of extern and static is **"do you wanna export the target?"**.

The main difference between export and static is the *visibility*.
In a nut shell, if you wanna make the target **visible**, the right option is "extern".
On the other hand, if you wanna make **invisible**, it's "static".

Why i call 'target', not 'variable' is that the concept could be applied not only to the variables,
but also functions.

### Static keyword

Let me give you explanation of static keyword first.
It would be easier to understand the concepts & difference of static and extern keyword.

When we see the word 'static', we expect the antonym would be 'dynamic'.
However, it's not. It's extern.
With the opposite meaning of static, we can get the right understanding.

Here, it means 'fixed', or 'local'. The target with static keyword has the local feature.
The 


### Extern keyword

Extern keyword makes the target global.
As the word means literally, the target with 'extern' keyword become global and visible to other files.














[comment]:<img src="{{ site.baseurl }}/assets/img/pexels/desk-messy.jpeg" style="max-width: 100%; height:auto;">

[1]:https://stackoverflow.com/questions/3684450/what-is-the-difference-between-static-and-extern-in-c
[]:http://www.answers.com/Q/What_is_the_difference_between_static_and_local_declaration
[]:
[]:
