---
layout: post
title:      "02: request-response"
date:       2020-07-11 11:10:54 -0400
permalink:  02_request-response
---


Dead-simple products and processes are often very hard to design. Their simplicity belies tremendous complexity. For example, what actually happens when we type in a URL and hit Enter?

The *request-response cycle* is the process by which one computer requests some information, then another computer processes and responds to that request. 


### **Request**

In this case, we're using our own computer and our request is to access a specific website, using its *domain name*. 

Street addresses are to physical homes what domain names are to digital homes (websites!). Unique domain names allow us to differentiate between unique websites.

So we press Enter and our browser uses a digital address book, a *DNS* (Domain Name Service), to find an *IP address* that corresponds to the domain name we've provided.

Internet Protocol addresses are long strings of numbers that, like domain names, serve as a unique ID or digital address. We don't need to get lost in the details, but websites typically have many IP addresses associated with their domain name.

If you're curious why two separate forms of ID are necessary, think about it like this: is it easier to remember 216.58.219.206 or google.com?

We type in a URL, hit Enter, our browser uses a DNS to find an IP address that corresponds to the specific domain na— wait. You may be wondering if 'domain names' and 'URLs'  are interchangeable terms... and that's an important distinction, they're not.

The full URL for what we refer to as Reddit's website, reddit.com, is actually https://www.reddit.com/. The domain name is the chunk after the forward slashes and everything before the domain name, 'https://', is the *protocol*. 

Very simply, the protocol gives your browser instructions for how to access the given domain name.


### **Response**

OK. Browser uses DNS to find IP address for domain name, using the given protocol, and finally uses that IP address to send a request to the appropriate servers. Sticking with the Reddit example, we'd be pinging Reddit's servers for Reddit's homepage with reddit.com.

What now? Reddit's servers recognize that we want to access their homepage so as a response, it will retrieve copies of the files that make up their homepage.

Every website is just a collection of these different files — HTML, CSS, and JavaScript files are the most common types — which enable us, the user, to interact with it.

Reddit's servers will divide these files into different *packets*, or smaller chunks of data, and send them back to our browser, using our browser's IP address (which is found using DNS).

Upon reaching our browser, these packets are finally re-assembled so we can actually see and interact with the website as Reddit intended.

The steps where packets are divided and re-assembled are done so via a standardized process called *TCP*, or Transmission Control Protocol. The piece in between, sending these packets separately, is completed using a different standardized process, *IP (*Internet Protocol).


### **Summary**

There's more nuance involved that I won't touch on here, but as a basic overview of the request-response cycle described above:

1. We type in a domain name and hit Enter.
2. Our browser takes the given domain name and uses DNS to find a corresponding IP address.
3. Our browser uses that IP address to send a request to servers.
4. Those servers process our request and retrieve the proper files.
5. The servers divide those files into packets, by TCP, and in response, send them back to our browser using IP.
6. When all of the packets reach our browser, they're re-assembled by TCP.
7. We use the website :)
