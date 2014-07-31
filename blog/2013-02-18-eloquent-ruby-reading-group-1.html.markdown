---
title: Eloquent Ruby Reading Group 1
date: 2013-02-18 08:41 -07:00
tags:
---

Eloquent Ruby PART I: The Basics

The first section of Eloquent Ruby has been great and I wish I had started it earlier. By this time in class, we had been tasked to write create a _virtual_ database from 6 CSV documents, additionally the program should offer access and interaction between our database objects. 

The first chapters introduce the basics of ruby, and it seems like we should have read this book instead of the passionate programmer book. It covers basic things like code structure, operators, collections, strings, RegEx, symbols, objects, dynamic typing, and tests! At this point in the class, we needed to soak in every chapter because our hashes were ugly, tests were lacking, objects were confused, symbols were fuzzy, and our code was a mess. These conclusions stuck out in my mind:

__I loved reading how to _Write Code That Looks Like Ruby_. I like direction, and it gave me a sense of direction.__

__The most helpful section was the _collections_ because our project is collection heavy.__

It helped me save many lines of code where i didn’t realize i could do better:

```ruby
def single_merchant_invoices
  successful_invoices = []
  invoices.each do |invoice|
    if invoice.success?
      successful_invoices.push(invoice)
    end
  end
  successful_invoices
end
```

into 

```ruby
def single_merchant_invoices
  invoices.select(&:success?)
end
```

[Soloman](http://twitter.com/rubysolo) helped us turn this:

```ruby
def customers_with_pending_invoices
  customers = []
    invoices.each do |invoice|
     customers.push(invoice.customer) if invoice.pending?
    end
    customers
end
```
     
into

```ruby
def customers_with_pending_invoices
   invoices.select(&:pending?).map(&:customer)
end
 ```
###Send :)
I also enjoyed learning about `.send()`! Send is amazing because it allows you to call a method, but use the method name as a parameter of `.send()`.

`Merchant.most_revenue` could be written as `Merchant.send(:most_revenue)` or `Merchant.send(“most_revenue”)`
Below is a code example of how I used send in my project:

```ruby
def self.most_revenue(number=1)
  items = invoice_items(:revenue)
  sort_list(items,number)
end

def self.most_items(number=1)
  items = invoice_items(:quantity)
  sort_list(items,number)
end

def self.invoice_items(input)
  items = Hash.new(0)
  Invoice.paid_invoices.each do |invoice|
    invoice.invoice_items.each do |invoice_item|
      item = find_by_id(invoice_item.item_id)
      items[item] += invoice_item.send(input)     
    end
  end
  items
end
```


###Eval :(
I am more confused about eval, Steve helped it make sense, but i don’t understand the value of it. Also I couldn’t get any test examples to work in IRB. 

eval definition:
Evaluates the Ruby expression(s) in string. If binding is given, which must be a Binding object, the evaluation is performed in its context. If the optional _filename_ and _lineno_ parameters are present, they will be used when reporting syntax errors.
