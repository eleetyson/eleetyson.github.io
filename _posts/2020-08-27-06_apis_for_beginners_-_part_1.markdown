---
layout: post
title:      "06: APIs for beginners - part 1"
date:       2020-08-27 20:10:55 +0000
permalink:  06_apis_for_beginners_-_part_1
---


Manual URL validation is tricky. As is increasingly the case though, there's an API for that.

My Sinatra project, an app for sharing content recommendations, uses an API to verify all user-submitted links.

There are free resources for individually testing links, expensive ones for bulk website crawling, and even some [impressive attempts](https://mathiasbynens.be/demo/url-regex) to manually validate with the perfect regex. Given the degree of difficulty here, I chose to delegate.

This handy API ([link](https://rapidapi.com/logicione/api/url-expander1) if you're curious) is on Rapid API, a site dedicated to APIs. Which got me thinking, are APIs important enough to merit an entire "marketplace"?

My short answer: yes. Even some superficial Googling suggests that APIs, the language of software, are becoming ever-more important. Let's dive in.

***

Software uses APIs to communicate. Just as we follow an established set rules for interacting with each other, apps connect through application programming interfaces.

APIs are snippets of code that share data, functionality, or both. A few examples:

* Yelp's API lets us access millions of business reviews (data)
* Twilio's APIs share text-messaging capabilities (functionality)
* Twitter's API can be used to aggregate certain user info or embed a timeline on our site (both)

Instead of trying to hand-code an SMS messaging feature or collect years worth of Boston-area coffee shop reviews for our app, we can borrow from APIs. Easy.

Kind of like phone numbers, an API's endpoints allow us to talk to it — to do that borrowing. Endpoints look similar to URLs. We can tweak or add on to these basic endpoints in our requests, so that they return return different responses.

```ruby
# Twitter API endpoint for getting all favorites (likes) by a specific user
https://api.twitter.com/1.1/favorites/list.json

# example request -- getting exactly 200 favorites from user @twitterdev
GET https://api.twitter.com/1.1/favorites/list.json?count=200&screen_name=twitterdev

# if we want 150 favorites from user @neymarjr instead
GET https://api.twitter.com/1.1/favorites/list.json?count=150&screen_name=neymarjr
```

Parsing through this response to get exactly what we want can be difficult. Other times, like for my Sinatra project, it's quite simple.

```ruby
# example of the body of a response from this URL validation API
  {
    "input_url":"https://amzn.to/2S4UzSx"
    "response_time":669
    "target_url":"https://www.amazon.com/gift-cards/b?ie=UTF8&node=2238192011"
    "target_url_alive":true
  }
```

All we need to know is whether the link is valid or not. So, I created a method that takes a user-inputted link as an argument, makes a GET request using that link, and finally returns that true/false value for the `target_url_alive` key. If false, we ask the user to submit a different, valid link.

```ruby
def valid_link?(link)
    response = Unirest.get "https://url-expander1.p.rapidapi.com/url_expander?short_url=#{link}",
    headers:{
      "X-RapidAPI-Host" => "url-expander1.p.rapidapi.com",
      "X-RapidAPI-Key" => "7adf8c6d72msh488376094fc1eb6p10c2d6jsnc34f7743ac55"
    }
    response.body["target_url_alive"] # will return true or false
end
```

Most APIs require users to create a key, or a unique identifier, so that the API provider can track how it's being used. Many APIs are free up to a certain number of requests in a specific timeframe (AKA a rate limit), after which each subsequent request incurs a small fee.

Small projects like mine won't sneeze at any rate limits. It's when apps with thousands of users making millions of requests depend on APIs (think a Stripe API for embedding payments on an eCommerce website), that the charges add up.

This is already pretty long, so I'll leave the business side of APIs for part 2. As a quick preview: lightweight, very use-case specific APIs like Twilio, Stripe, and Algolia are getting popular. Thanks for reading 👋
