---
layout: post
title:      "04: regex and abstraction"
date:       2020-07-29 13:38:10 -0400
permalink:  04_regex_and_abstraction
---


I'm looking forward to going deeper on exception handling and designing durable applications.

In this case though, my project (CLI Blackjack) actually handles some invalid user inputs with a regex — also known as a regular expression.

Like maps, metaphors, and algebra, regexes (regexen? regi??) are forms of abstraction. A map of the US merely represents our country's physical geography. It's not actually the mountains and oceans themselves.

When we make something more abstract, we sacrifice specificity to gain flexibility.

I learned more about this in designing a method that takes user input, the amount the user would like to bet for the current hand, and invokes other methods accordingly.

Instead of trying to rescue different exceptions, like a `TypeError`, I was able to print an error message and loop the method until the user's input omits any non-digit characters. A simple regex checks whether this is the case.

While Ruby often reads like plain English, regular expressions can look like gibberish. I found this  [Ruby-specific resource](https://rubular.com/) to be extremely helpful.

As you can see at the bottom of the linked page, it's possible to pass a regex as an argument to methods like `#match` or `#scan`, in order to cover a broader set of circumstances.

If I wanted to check whether a given string contained a certain character, I could do something simple like this:

```
given_str.include?("certain_char")
```

But what if I wanted to check a string for a bunch of different characters, all at once? Instead of calling `#include` on the string and passing in a different vowel, 6 separate times, I could use a regular expression instead:

```
# Return whether a given string contains any vowels
# less abstract
"why".include?("a") #=> false
"why".include?("e") #=> false
"why".include?("i") #=> false
"why".include?("o") #=> false
"why".include?("u") #=> false
"why".include?("y") #=> true -- Pluto is a planet too :)

# more abstract
"why".match?(/[aeiouy]/) #=> true
```

The brackets surrounding `[aeiouy]` indicate that we want to check whether any one of these characters matches any single character in the receiver of this method — the string `"why"`. The forward slashes indicate that we want this interpreted as a regular expression (not an array!).

To summarize, we call `#match?` on `"why"` and pass in this specific regex `/[aeiouy]/` as an argument to check whether "why" contains any vowels.

This is very similar to how I checked for any non-digit characters in the user's input for my project. The method itself is long so I've included the relevant pieces below:

```
def deal_hand

print "Please enter your bet for this hand: "
input = gets.strip # remove leading / trailing whitespaces and store user input

# loop #deal_hand until given valid user input
  if input.match?(/\D/)
    puts "* please enter an integer, omitting non-digit characters *"
    self.deal_hand
	#if/else chain continues here..... 
	end
		
end
```

The if statement here is very similar to our previous example. As we know from this [handy reference](https://rubular.com/), `\D` enables us to catch any non-digit character. 

So instead of calling `#match?` on `"why"`, we're simply calling `#match` on a different string — the local variable `input`. We're still checking for a specific set of characters, now we're just looking for any non-digits `/\D/` instead of any vowels `/[aeiouy]/`.

With this CLI project, I needed to get out my narrow perspective and design for what might go wrong, in case users interacted with the app in unintended or undesirable ways.

I was able to do this, in part, by using a common form of abstraction: a regular expression. Even though it's a little more difficult to read because it's less specific, this regex provided the flexibility to write in one line of code what would otherwise take me many more. I'd like to think doing so simplified the user experience.
