---
title: HTML&CSS Section1
date: 2013-03-11 15:18 -06:00
tags:
---

Beyond learning pure ruby, we are shifting focus and adding web output to our ruby applications.

Since the web connects the largest set of people, its beneficial that we understand how to create and design web applications. 

We have started to read <http://htmlandcssbook.com> because our current projects take previous problems and require a web output. 

While reading section 1, I discovered _definition lists_. They allow you to create a list of words with their definitions indented.

Below is some code to show how we create a definition list.   

```erb
<dl>  
  <% @customer.each do |customer| %>        
    <dt>Name: </dt>
    <dd><%= customer.name%></dd>
             
    <dt>Age: </dt>
    <dd><%= customer.age%></dd>
                 
    <dt>Gender: </dt>
    <dd><%= customer.gender%></dd>
                 
    <dt>Day of Birth:</dt>
    <dd><%= customer.dob%></dd>
  <% end %>
</dl>
```
with output:

<dl>          
    <dt>Name: </dt>
    <dd>John Don</dd>
             
    <dt>Age: </dt>
    <dd>23</dd>
                 
    <dt>Gender: </dt>
    <dd>Male</dd>
                 
    <dt>Day of Birth:</dt>
    <dd>12th May 1986</dd>
</dl>

I know that a customer and their attributes are not appropriate usage of definition lists but it works. 

Most of this section was a refresher. Our previous project [TrafficSpy](http://trafficspy.herokuapp.com) required some HTML knowledge and I put [twitter bootstrap](http://blog.getbootstrap.com) to work creating a decent layout and lists. 
