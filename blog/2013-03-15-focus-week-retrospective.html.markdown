---
title: Focus Week Retrospective
date: 2013-03-15 09:04 -06:00
tags:
---

This week has been fun. My group was turned loose to restart and extend an early project. We were familiar with the problems so it took about two days to finish instead of two weeks on the first pass. The best part is that we got to thoroughly test our code, and extend it with some get_const and send. I don’t know if it would be considered meta-programming, but it felt like it. 

fun code example 1:

```ruby
def find(params)
  attribute = params.keys.first
  self.send("find_by_#{attribute}",params[attribute.to_sym])
end

def find_all(params)
  attribute = params.keys.first
  self.send("find_all_by_#{attribute}",params[attribute.to_sym])
end
```
fun code example 2:

```ruby
def self.route(table,function,params={})
  @table = camel_case(take_off_s(table))
  @function = function.to_sym
  get_response(params)
end

def self.get_response(params)
  if params == {}
    SalesEngineWeb.const_get(@table).send(@function)
  else
    SalesEngineWeb.const_get(@table).send(@function,params)
  end
end
```

Beyond coding, I finally get to give my lightning talk about arduino. Jeff decided to dedicate the entire day to arduino topics and luckily i get to introduce ruby+arduino to the class of rubyists. 
