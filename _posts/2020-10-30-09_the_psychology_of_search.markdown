---
layout: post
title:      "09: the psychology of search"
date:       2020-10-30 13:44:06 +0000
permalink:  09_the_psychology_of_search
---


I recently read that Apple is working on its own search engine. Internet search is big business and Apple already has its own browser, Safari, so maybe this is just a natural progression.

Regardless, the news pushed me down the rabbit hole of *intranet* search: search limited to a small subset of information or restricted to certain users.

Intranet search matters because there's a lot of stuff for us to sift through. About 90% of the world's data has been [created in the past two years](https://techjury.net/blog/how-much-data-is-created-every-day/#gref). If the history of data was a book, 2018-2020 would be everything except the prologue and acknowledgments.

We create so much data so often that finding the right pieces gets tedious. Back in 2011, McKinsey estimated knowledge workers [spend ~12% of their time searching for content](https://www.mckinsey.com/~/media/mckinsey/dotcom/client_service/high%20tech/pdfs/impact_of_internet_technologies_search_final2.aspx). To meet this demand, knowledge management tools like [Confluence](https://www.atlassian.com/software/confluence) and [Notion](https://www.notion.so/product) were born.

As maintaining internal wikis becomes a job in and of itself, it's probably worth asking: do you dedicate people full-time to them or instead give up on organizing altogether?

---

Powered by Algolia's APIs, the search feature in [Bootstrap's documentation](https://getbootstrap.com/docs/4.5/getting-started/introduction/) is a good example of intranet search. Visitors can specify exactly what they're looking for and quickly determine whether they'll need to look elsewhere for answers.

This is a *way* better user experience than being forced to click around the docs. Even the most thoughtfully organized folder, or file structure, can grow difficult to navigate.

My guess is that most site visits are brief, which is exactly what the good people behind Bootstrap want. Short visits mean that visitors can get in, easily get what they need, and get out. Especially for beginners, simple is better.

This is what drove the shift from command-line interfaces (CLIs) to graphical user interfaces (GUIs). GUIs personified dense technical concepts with everyday objects like "folders" and "trash", making personal computers accessible to all. While few could master early CLIs, we all have learned to point and click.

---

Powerful software allows us to do more with less. The challenge in designing these tools lies in deciding which features to feature, and how. There's a finite amount of real estate on any screen, which is partially why famous designer Don Norman believes [CLIs are making a comeback](https://jnd.org/ui_breakthrough-command_line_interfaces/):

> "GUIs work well only when the number of alternative items or actions is small. When the number of items reaches the level within today's complex operating systems, applications, and the information spaces of the internet, the GUI does not scale well."

The classic command line was literally just an empty box. Users needed to memorize commands which made for a steep learning curve. The modern command line, maybe more accurately described as a command palette, is far more sophisticated.

Text editors like VS Code were early to this game, offering autocomplete functionality for common keywords, and the concept has bled into products for non-technical users. The most prominent is probably Superhuman, though there are enough examples now to make up [an entire Product Hunt collection](https://www.producthunt.com/@chrismessina/collections/launchers).

I'd imagine that Norman, long an advocate for human-centered design, would support such features. Which is a better sneaker shopping experience: an employee points you to the store's back where you wander shelves and shelves of shoes... or they bring a couple boxes out for you?

---

This dichotomy between 'find it yourself' and 'bring it to me' defines these flexible command line-esque features. Norman explains it much better than I can:

> Search is never anything I want to do. I don't want to search — I want to know something. I want an answer engine, not a search engine.

> "Command line interfaces. Once that was all we had. Then they disappeared, replaced by what we thought was a great advance: GUIs. GUIs were — and still are — valuable, but they fail to scale to the demands of today's systems. So now command line interfaces are back again, hiding under the name of search."

To answer my own question from earlier (dedicate entire roles to maintaining internal content or concede maintenance entirely) I'd say, ideally, neither. The value of modern software is that it empowers us to carefully organize *and* quickly parse. 

I've created tons of pages and sub-pages on Notion, but also frequently use `CTRL + P` to figure out where something lives. I probably won't remember the exact title of this particular page, but if I can just remember that it had 'search' in it then that'll be enough to trigger a match.

Our daily lives are increasingly overwhelmed with information and tools to manage it. Software that offers intelligent command line or search engine-like features is an immense help. Simply typing what we want to do or find and receiving an answer is a better user experience for newcomers and power users alike.
