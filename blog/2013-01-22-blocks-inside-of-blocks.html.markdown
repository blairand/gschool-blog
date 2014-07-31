---
title: Blocks inside of blocks...
date: 
tags:
---

I'm so damn excited to start gSchool on Monday that i had to just write out what i'm learning to make sure it stays in my brain. Also to practice markdown. 

Before starting we were to complete [the pragmatic studio ruby lessons](http://online.pragmaticstudio.com/courses/ruby/) and today the best thing i've learned about was blocks. 

Blocks let you perform a block of code on a set of data. 

for example with an array of numbers starting at 1 and going through 10:
` numbers = [1,2,3,4,5,6,7,8,9,10]` 

You can... 

Gather all numbers greater than 5:
`numbers.select { |n| n &gt; 5 } `

Gather all numbers less than 5:
`numbers.select { |n| n &lt; 5 } `

Select all numbers that are even:
`numbers.select { |n| n.even? }`

Reject all numbers that are even:
`numbers.reject { |n| n.even? }`

Create separate arrays of both evens and odds:
`numbers.partition { |n,m| n.even? }`

Reduce the array down to a single solution:
`numbers.reduce { |sum,n| sum + n }`

So far blocks seem to be a great way to process large amounts of data. 

If you know where I can practice making more blocks, please send the information my way.   I would love to see different examples and styles of solutions. 