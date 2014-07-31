---
title: gSchool Day1 improv, and Installing Ruby 1.9.3
date:
tags:
---

_Today was my first day of [gschool](http://www.gschool.it) and it was a ton of team building by the [improv effect](http://www.improveffect.com/). It was a blast._

###### After class, I opened my new Macbook Air and got started on setting up the development environment. I was using [tutorials.jumpstartlab.com/setup](http://tutorials.jumpstartlab.com/setup) but had to go through some steps that were missing from the setup page.######

Below are the steps i went through:

1) Xcode from the apple 'appstore'. just search for 'xcode' there is only one option i could find. 

2) __(missing from instructions)__ After installing xcode, visit the xcode preferences and then over to downloads and install the _command line tools_

3) Install homebrew 

    ruby -e "$(curl -fsSkL raw.github.com/mxcl/homebrew/go)"

4) install git: 

    brew install git

5) Install RVM: 

    bash -s stable &lt; &lt; (curl -L http://bit.ly/r52UYO)
    source ~/.bash_profile

6) At this step the instructions said to enter:

     rvm install 1.9.3 --with-gcc=clang

but that did not work for me. I received error:

    Error running 'make', please read /Users/blairanderson/.rvm/log/ruby-1.9.3-p374/make.log


_If you did not see an error, skip to the next step._

Since this step did not work for me, i found [this set of instructions on stackoverflow](http://stackoverflow.com/a/14467463/1536309)

From this page i entered:

    rvm get head
    rvm requirements run

It might ask you for your password, for me it did not. 

After that type: 

    rvm install 1.9.3 --with-opt-dir=`brew --prefix readline` --without-tcl --without-tk

this command worked for me. After these run #7
    
7) set ruby 1.9.3 to your default:

    rvm use 1.9.3 --default