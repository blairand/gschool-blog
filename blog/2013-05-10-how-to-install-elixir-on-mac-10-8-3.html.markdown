---
title: How to Install Elixir on Mac 10.8.3
date: 2013-05-10 13:01 -06:00
tags:
---

Today we met with Jose Valim and got to learn about Elixir. Its a functional programming language built by Jose on top of Erlang.

### Step 1.
To install Elixir, you must first have Erlang. [I recommend visiting this page and installing the package that meets the specs of your computer.](https://www.erlang-solutions.com/downloads/download-erlang-otp)

I have a 64bit MacBook Air, so I downloaded the matching package. 
I also used [this article to figure out if my mac was 64bit or 32bit.](http://support.apple.com/kb/ht3696)

### Step 2.

Install that shit.

### Step 3.

    Brew install elixir
    
### Step 4. 

check if erlang is installed by typing:

    $ erl
 
 You should see some output like this:
 
    Erlang R16B (erts-5.10.1) [source-05f1189] [64-bit] [smp:4:4] [asyncthreads:10] [hipe] [kernel-poll:false]
  
    Eshell V5.10.1  (abort with ^G)
    
 Go ahead and type control+c to exit. Now try to get into iex
 
     $ iex
     
 You should see output like this:
 
    Interactive Elixir (0.8.1) - press Ctrl+C to exit (type h() ENTER for help)
    
    iex(1)>
    
Now type 1 + 1 and hit return:

    iex(1)> 1 + 1

If it returns a 2, then you're running [Elixir](http://elixir-lang.org/)
