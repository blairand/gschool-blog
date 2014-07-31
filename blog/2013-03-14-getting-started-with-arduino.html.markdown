---
title: Getting Started with Arduino
date: 2013-03-14 17:46 -06:00
tags:
---

[link to presentation slides](https://docs.google.com/presentation/d/1Pga0nURs_gWLGFuuyeRFqi2UeD7qJKYQh8w5tp7MAyY/edit?usp=sharing)

[Starter Kit for Uno](http://www.amazon.com/gp/product/B0051QHPJM/ref=as_li_ss_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B0051QHPJM&linkCode=as2&tag=faccatitefin-20)


Getting Started

```ruby
gem install dino
```

Upload the Bootstrapper

* Open [the normal Arduino IDE](http://arduino.cc/en/Main/Software)
* Download the bootstrapper [src/du.ino](https://raw.github.com/austinbv/dino/master/src/du.ino)
* Open the file in the Arduino IDE
* Plug in your Arduino via USB
* Click the upload button (an arrow)

#### Verify Install

* Build the sample circuit [examples/led/led.png](https://raw.github.com/austinbv/dino/master/examples/led/led.png)
* From your terminal, execute `ruby example/led/led.rb`
* Observe your LED blinking continuously
