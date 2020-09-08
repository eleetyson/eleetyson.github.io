---
layout: post
title:      "07: APIs for beginners - part 2"
date:       2020-09-08 18:54:11 -0400
permalink:  07_apis_for_beginners_-_part_2
---


ICYMI - part 1 is over [here](https://eleetyson.github.io/06_apis_for_beginners_-_part_1).

If we want to use one of Stripe's APIs for embedding payments on an eCommerce site, we'd take a look at their [beautiful documentation.](https://stripe.com/docs/api) It's mind-boggling to think how many hours went into designing something like this.

Search, dark mode, click to copy, the actual content — beautiful, all of it. This tremendous attention to seemingly insignificant detail makes a bit more sense when we recognize that Stripe is an *entire company* built around APIs. And this strategy, an API-first approach, is only becoming more common.

To understand why, why there are sites solely devoted to aggregating APIs and why news outlets are singing their praises, let's expand on what we learned in part 1.

---

APIs are interfaces for developers. Just like a mobile app acts as an interface for playing music or ordering food, an API acts as an interface for developers to borrow data, functionality, or both, in building their own application.

I think APIs are like Lego blocks in that they make building easier. You can always try and manufacture your own blocks instead — you'd have more freedom that way — but it would also be incredibly complicated and time-consuming.

Maybe this analogy makes more sense: on any large team, each individual has a narrowly-defined job. They'll also have a very particular set of skills, skills they've acquired over a very long career, that would make it a nightmare for any rando plucked from a different department to replace them.

By virtue of specialization, the team becomes more than the sum of its parts and does more than they could with a roster of generalists. Similarly, APIs are all about focus.

---

Here's how it might look: the provider dedicates years to solving a difficult, though common problem: Stripe with online payments, Plaid with banking, Auth0 with authentication, and so on. That's all they work on.

Eventually, the API provider finds a decent solution to this problem and then shares it with the world. Their solution is an API (often a set of APIs), or publicly-available chunks of code that other developers get to copy and paste. In the writing world, this is called plagiarism. In programming, it's encouraged.

Because of the API provider's toil, customers don't need to spend months of their engineering team's time (easily a 5 or 6 figure cost) for a solution to accepting credit card payments... that *might* work. Weighed against [~3% and $0.30 per transaction](https://stripe.com/pricing), no up-front cost, and guaranteed support on the off-chance it ever *doesn't* work, the decision is easy.

If you're Zoom then no, obviously you don't utilize any kind of video API. You build video functionality into your product because that is the most important part of your product. But if you're an eCommerce app that wants to occasionally connect frustrated customers with support through video chat, a video API is your friend. 

---

Technology is a form of abstraction (abstraction = removing non-essential details), which is why I think abstraction *within* the process of developing software, already a powerful technology / abstraction itself, is so interesting.

Before 2006, tech companies had to buy and manage their own servers. I've read that this was complicated and annoying, which is why AWS has become an ATM for Amazon. Renting someone else's servers saves a ton of headaches. 

Around that same time, Git was also released. Its inception meant that developers could finally track changes to their code and restore older versions (like Google Docs). GitHub and GitLab are popular products built around this system, enabling teams of developers to collaborate on files stored online, instead of on their individual computers.

AWS allowed engineering teams to focus on coding their apps, not managing servers. GitHub made it easier for these teams to collaborate. APIs let engineering teams and individual devs further narrow their scope and only code the most important parts of their apps. 

Like Infrastructure-as-a-Service (AWS) and remote version control (GitHub), APIs are an important abstraction in the world of software development. Thanks to these abstractions, it's never been cheaper, faster, or easier for us to create software.

Twilio, Stripe, Auth0, Algolia, Plaid, and Sendgrid have been successful because their APIs solve a painful, ubiquitous problem. Looking ahead, here are a few newer ones I'm interested in:

- [Iggy](http://www.askiggy.com/) - location enrichment API (example: an apartment rental platform could use it to add data on air quality and street noise to its listings)
- [Noyo](https://www.noyo.com/) - health insurance API (example: an HR department could use it for sending employee info to health insurance providers like Aetna and Cigna, to secure a plan)
- [Sendbird](https://sendbird.com/customers) - chat / messaging API (example: any mobile app could use it to add a chat feature)
