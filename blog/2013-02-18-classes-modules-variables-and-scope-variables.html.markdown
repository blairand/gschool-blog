---
title: Classes, Modules, Variables, and Scope, Variables
date: 2013-02-18 09:49 -07:00
tags:
---

[adapted from gschool0/130218](https://github.com/JumpstartLab/curriculum/blob/master/source/academy/sessions/gschool0/130218.markdown)

To get a ruby file into IRB type require, then type the filepath `require ‘.person’`
 
 When you create a `Person` class, it inherits from Object, which is a class that inherits from kernel, and again from BasicObject.

 inheritance passes all the behavior onto its child so any methods you created are passed on. But you only want to use inheritance if you actually plan to create 
 
`Person < Object < Kernel < BasicObject`
 
` p = Person.new`

for explicit inheritance: `Child < Person`

```ruby
  class Person
    attr_accessor :first_name
  
    def can_drive?
      true
    end
    
    def demo_self
      puts self
    end
  end

  class Child < Person  
  end
```


####Modules

Modules exist for a few different reasons. 

- First is to namespace your code. If your modules name is `ContactApp` and your class is called `Person` then it is namespaced as `ContactApp::Person`

- Second is to extend and/or include code into your classes. If you create methods in an external module, then you can include the methods as instance methods by typing `include Module`. If you `extend Module` then the methods are mixed in as class methods.  
    
    instance = include
    
    class = extend

####Gems

there are 4 ways to access gems. 

- you can push them to rubygems

- you can push them to github and install from github

- you can host a gem server and install from the server

- you can install and bundle from the direct path to the file
