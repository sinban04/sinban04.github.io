---
title: "Desktop Environment"
layout: post
date: 2019-10-07
#image: /assets/images/for-posts/cmake-logo.jpeg
image: https://www.flickr.com/photos/131411397@N02/28966754282
headerImage: true
tag:
- Operating System
- Desktop Environment
- Gnome desktop
- MS Windows
- Framework
category: blog
comments: true
author: injung hwang
---

First Draft: 2019-10-07

# Intro

There are many OS platforms such as Mac, Windows, Ubuntu, and so on.

When we say, operating system, then it usually means kernel for the general case.
If you do not have opportunity to think about the desktop,
you might think kernel is everything in the operating system world.
(Because kernel is cool, and all we have heard so far is Kernel!)

However, operating systems we are using today, actually do not have only kernel.
They have GUI and many useful stuffs with desktop environment.
Even though you are not using GUI, we need terminal for CLI with ssh daemon.

Android OS, we call it OS, is based on Linux kernel.
It did nothing to Linux kernel. Then what did Android do, and why we call it OS?

Things Android provides regardless of Linux kernel are frameworks and systems.
As it were, application framework, windowing system, IPC, and so on.

Without them, we need to make them anyway to use our computer properly.
We call it "Desktop Environment".

# Desktop Environment

Desktop environment is kinda collection of several frameworks.

When we make new operating system, we need to consider some stuffs.

## Kernel

At first, what kernel should we use?
You might think Linux kernel is the only available option,
(MS Windows does not open their kernel source code)
but it's not true.

Actually there are a freebsd kernel, and many other kernels.
Apple's MacOS is based on freebsd kernel.

There were many suggested kernel designs so far throughout many brilliant papers,
In short, there are two big streams: Monolithic kernel, and Microkernel.

Linux is the Monolithic kernel and Freebsd is the microkernel.
Kernel has kinda deep story, so if you wanna know the difference, see [here][1].

The structure and fundamental difference would be covered later.

## Windowing system

After we think about kernel, we need to think about **Windowing System**.

Windowing system takes charge of showing several windows on GUI.
Applications have their windows such as main window, dialog, menu
for the interaction with their user.

Each application has concerns on only its own windows.
They don't mind the others do what.
They only ask OS to show their own windows.

Then, windowing system collects several windows interacting with its customers (applications),
and then it decides how to make the final output image displayed with screen.

It does not only collect windows, but also sort them by their [z-order][2].
According to Wikipeidia,

> Z-order is an ordering of overlapping two-dimensional objects,
> such as windows in a stacking window manager, shapes in a vector graphics editor,
> or object in a 3D application.

There are many [windowing systems][3],
but the famous, major windowing system on Linux is **X Windows**, and **Wayland**.

[X Windows][4] is the traditional king of windowing system,
but it's old and inefficient for now.
(It seems that X Windows team are also improving their system these days.)

To overcome X Windows inefficient structure, Wayland rises from the surface these days.
If you wanna know what Wayland has made distinct from X windows, see [here][5].


## Application Framework

When we learn about the operating system, we usually liken Operating System to Government.
We need government to make our life convenient, but government is not a goal itself.
Government exists for the citizen. It's kinda overhead.

OS is same. We need OS, but it's not our goal.
What we wanna do with our computer is the application.

Therefore, OS need to think with its heart and soul about how to provide APIs.
"How can we make our application easy and convenient?".

This philosophy is the **application framework**.
With this application framework, application developers can make useful application.

In a real case, many OS platforms really care its application framework,
because it's the key to attract great, creative application developers to their platforms.
Subsequently, these applications attract the user and make the platform stronger.

GTK, QT, Chromium's, Android are the representative application frameworks.

## Inter-Process Communication (IPC)

In addition to application framework, OS has obliged to provide
ways the applications communicate.

Simple applications could run by one process,
but even for the simple chat application, multithreaded programming is necessary.
With multithreaded environment, of course,
synchronization and data exchange between them are indispensable.

The way they talk is IPC.
IPC could be done within single host computer, or done with other process in another network node.

Pipe is the simplest thing, and named pipe, socket follows.
Pipe is the fastest IPC, but it's one directional and too primitive.

D-Bus is one of the most famous IPC under POSIX environment.
Unlike IPCs mentioned right before, [D-Bus][6] provides several rich features.

There is **a trade-off between functionality and speed** in the IPC world.
Unix socket is much faster than D-Bus but its APIs are too primitive to use.
We need to write error handling code, and serialization code for rich features.
However, the more features, the slower it becomes.

Linux usually uses Unix domain socket for its main IPC in single host computer,
and network socket for the network communication.
MS Windows uses its named pipe (it's not same named pipe in Unix), and WinSock.


# Epilogue

Gnome, KDE, MS Windows, and MacOS are the representative desktop environment.

There are also more things to talk about related to desktop environment
such as init daemon, file system, and more.

I have dealt with some basic parts of operating system.
From now, when you think about the operating system, think more than just kernel.




[1]:https://stackoverflow.com/questions/4537850/what-is-difference-between-monolithic-and-micro-kernel
[2]:https://en.wikipedia.org/wiki/Z-order
[3]:https://en.wikipedia.org/wiki/Windowing_system
[4]:https://en.wikipedia.org/wiki/X_Window_System
[5]:https://wayland.freedesktop.org/architecture.html
[6]:https://dbus.freedesktop.org/
