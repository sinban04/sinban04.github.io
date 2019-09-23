---
title: "Build System, Meta-Build System and Compilers"
layout: post
date: 2019-09-23
image: /assets/images/for-posts/
headerImage: false
tag:
- Build system
- Meta build system
- Compiler
- Make
- CMake
category: blog
comments: true
author: injung hwang
---

First Draft: 2019-09-23

# Why all this stuffs?

Before reading this article, i wanna let you know this article is targeted at normal c, c++ environment,
which i'm familiar with.

Launching some new project, the first thing we need to consider is 'build system'.
When we try to compile 1,2 or 3 source codes, it's totally okay to compile with *gcc* commands.

However, the bigger the project becomes, the longer the command becomes.
Not only it's annoying, we can not write those commands every time.
At least, we wanna write a simple script containing such command.

## Build system

It's where "***Build System***" comes from. We need some system to handle this annoying stuffs.

In a nutshell, build system is the collection of scripts mentioning how to build the "*targets*",
which contains compiler commands.
We can skip the complex process of writing long long compiler commands with its compile options.

Make, Autotools, [Ninja][2], such things are the example of build system.
These days, there are really many build systems to make up the existing's weakness.
If you wanna know more about examples, see [here][1].

One of you might get wrong about *make*.
*Make* is not a compiler, but a just build system wrapping wordy gcc commands.

Nonetheless, still the problem exists.

Although build system could keep us from the complex compiler command,
it can not from **platform-dependency**.
If you are trying to make your project compilable on a specific platform, it doesn't matter.
But, the project we are making are, in many cases, targeting various platforms.

In addition, if you wanna change the compiler the build system uses,
you need to write new script for the build system.
Even worse, the new script is similar to the existing one.

## Meta-build system

Here comes "**Meta-Build System**".

Meta-build system provides platform-independent script
to generate build script depending on the platform.
The meta-build script could generate the target build script at runtime.

[*CMAKE*][3] is the most well-known, and there are many like [*GN*][4] (From google), and [*Waf*][5].

Most of you might have heard CMAKE from somewhere before.
Most projects use CMAKE as its meta-build system, and it's also my favorite.

Google have developed its own meta-build system called *GN*.

I have used *Waf* when i have worked on [*Ardupilot* project][6].

## Wny not 'Do on your own'?

Of course, you can do all the stuffs (build & meta-build system) with a single shell script.
However, it's very exhausting, and **not flexible**.
As a computer engineer, we always need to make our code flexible.


# Build Process

Usually, there are 3 steps of build: Meta-build, build, compile.

Some projects have no meta-build because its target platform is firmly fixed,
but most cases have three.

I give you an example with CMAKE.
You can generate build script with following commands

```
$ cmake -S. -Bbuild -G "target_build_system"
```
I have specified where the source code is, and where the build scripts are going to appear,
and what is the target build system.

If you are using CMAKE and Ninja build system, then
```
$ cmake -S. -Bbuild -G Ninja
$ Ninja -C build -j9
```
Then, the computer would begin compilation with Ninja build system.

If you compile with Visual Studio 2019 on MS Windows,
```
$ cmake -S. -Bbuild -G "Visual Studio 16 2019"
```

Then, the project and solution files come out at build/ directory.



[1]:https://linuxfr.org/users/julien_jorge/journaux/un-petit-tour-des-systemes-de-build
[2]:https://ninja-build.org/
[3]:https://cmake.org/
[4]:https://chromium.googlesource.com/chromium/src/tools/gn/+/48062805e19b4697c5fbd926dc649c78b6aaa138/README.md
[5]:https://waf.io/
[6]:http://ardupilot.org/
