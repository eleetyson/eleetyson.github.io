---
layout: post
title:      "05: straight cache"
date:       2020-08-15 23:18:37 +0000
permalink:  05_straight_cache
---


An elephant never forgets. And neither do computers.

But unlike elephants, we expect our machines to move quickly. Part of the reason they can is because of caches.

Very literally, caches are small, secure places for storage. A closet is a cache. Short-term memory is a type of cache. While we can't hold much in a cache, it's easy to sort through.

Computers cache copies of files and data so we can access them promptly. 

The internet is a massive network of (mostly underwater) cables. These cables facilitate interactions between clients, like my browser, and servers. When I google 'the best taco trucks near me', I'm sending a request to Google's servers. My request will travel along these cables to Google's servers so they can process it and respond with recs, fast.

Like with a flight, the farther my request and the subsequent response have to travel, the longer it will take. A server 10 miles from me will provide a faster response than one 10,000 miles away.

Content delivery networks (CDNs) are groups of servers that coordinate to provide speedier responses by caching popular content. When a company talks about serving "from the edge" or "at the edge", they mean using servers that are physically close to users.

If everyone in LA started frantically googling for local taco trucks all at once, CDNs will ensure that copies of the responses from Google's servers, the search results, are cached in some nearby servers for rapid delivery.

All computers, not just servers, have random access memory (RAM), where its caches live. Your laptop has multiple caches and retrieving information from the smallest, top-level one will be fastest.

Computers, like brains, can only hold so much in short-term memory. Caching is just prioritization: we need to keep the important stuff close.
