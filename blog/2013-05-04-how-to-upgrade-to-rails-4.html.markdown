---
title: How to Upgrade to Rails 4
date: 2013-05-04 11:23 -06:00
tags:
---

With some motivation from my mentors and reading [this blog post](http://weblog.rubyonrails.org/2013/2/25/Rails-4-0-beta1/), I decided to experiment moving a project from rails 3.2.13 to rails 4.0.0 today. 

You cannot just update the gemfile, there are some config settings that need to be changed. Also i have not gotten this to work on heroku yet. 

### Install Rails 4 

```ruby
$gem install rails --version 4.0.0.beta1 --no-ri --no-rdoc
```

### Update Rails in Gemfile

Change from this:

```ruby
  source 'https://rubygems.org'

  gem 'rails', '3.2.13'
```

To This: 

```ruby
  source 'https://rubygems.org'

  gem 'rails', '4.0.0.beta1'
```

###Update simpleform: 

from:

```ruby
  gem 'simple_form'
```

to:

```ruby
  gem 'simple_form', '3.0.0.beta1'
```

### Remove Assets

Delete all this shit:

```ruby

  group :assets do
    gem 'sass-rails',   '~> 3.2.3'
    gem 'coffee-rails', '~> 3.2.1'
    gem 'uglifier', '>= 1.0.3'
  end

```

After this, you need to edit a couple lines in the config files

### updating config/environments/development.rb
delete:

```ruby
  config.whiny_nils = true
  config.active_record.auto_explain_threshold_in_seconds = 0.5
```
add:

```ruby
  config.eager_load = false
```


