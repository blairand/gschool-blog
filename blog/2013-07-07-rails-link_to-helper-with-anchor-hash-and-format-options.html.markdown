---
title: rails link_to helper with anchor-hash and format options
date: 2013-07-07 19:55
tags:
---

__Rails link_to Helpers Worth Remembering__

1. Adding an anchor
2. Adding a format
3. link_to Blocks

---
#### Adding an Anchor
Recently on a chatroom app I wanted to force the user to choose a display-name or login. We wanted to use responsive CSS modals. Visit [http://www.runtalk.us/chats/demoday](http://www.runtalk.us/chats/demoday) to see the functionality, i'm fairly happy with it. The modal sits inside a hidden `<section>` element. To view the section you have to hit the url and include the id as an anchor. 

What was needed:

__Add the :anchor => "something" option to any url_helper to include #something to the end of the url__

for example ` link_to "home", root_path(anchor: "go-home")` would create `<a href="/#go-home">home</a>`

___
#### Adding a format
I wanted a feed endpoint that would properly resolve if the user does not hit the proper format. 

For a first iteration, when a user visits '/feed' or '/feed.rss', then they should get the same RSS formatted output.

__here is one solution:__


```ruby
 def feed
   request.format = "rss"
   @submissions = Submission.latest
   
   respond_to do |format|
     format.any {render rss: @submissions }
   end
 end
```
basically no matter what format comes in, its overwritten as rss and responds with .rss formatted text. 

I didn't like the added confusion of when you hit `/feed.json` or `/feed.csv` then it also responds with rss formatted body. 

__The solution i decided to go with:__

```ruby
  def feed
    @submissions = Submission.latest.limit(5)
    
    respond_to do |format|
      format.rss  { render rss: @submissions }
      format.html { redirect_to feed_path(format: :rss)}
    end
  end

```

What i learned: 
__Add :format => :something to any url_helper to include format .something to the end of the url__

for example `link_to 'posts', posts_path(format: :json)` would create `<a href="/posts.json">home</a>`


I would love to hear an opinion from a seasoned developer about this. Whether or not its a bad practice, or if I should do it one way vs another. 
___

#### link_to blocks
sometimes you need to fill a link with more text than expected. 

commonly when your content is dynamic or uses icons you'll see large link helpers like `link_to '<i class="icon-search icon-white">search me'.html_safe, posts_path, class: "too many classes", id: "woah"`

its usually hard to fit inside 80 characters but something helpful is passing a block into link to like this:

```ruby 
link_to posts_path, class: "too many classes", id: "woah" do
  '<i class="icon-search icon-white">search me'
end
```

sometimes its helpful, and sometimes its confusing. This mostly only happens when i'm using bootstrap buttons with icons.
