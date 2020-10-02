---
layout: post
title:      "08: design for devs"
date:       2020-10-02 19:21:51 +0000
permalink:  08_design_for_devs
---


In which I write up a long list of links...

---

Ira Glass describes '[the gap](https://www.youtube.com/watch?v=r5Kc1DVlqq4)' as the chasm between a beginner's creative output and their taste.

As a new dev, it feels awesome to ship something, anything, because I think there's an inherent joy in translating an idea into some form of reality.

Conversely, the gap is still there. It's obvious. My Rails project looks fine, but there are very tangible differences between what I've made and what I *want* to make; tangible differences between my project and the apps / websites I use.

Glass also explains that producing — continuing to work through this frustrating phase where our output doesn't line up with our taste — is key to narrowing the gap between them.

The gap is evident in the code that we write (could be more concise, performant, etc.)  and often very evident in how that code looks on the frontend. We tend to, rightfully, focus on the former at Flatiron School, so with this post I'll aim to provide support for the latter.

---

### CSS layout systems

Bootstrap and Tailwind are popular CSS frameworks that can get you from my-app-is-some-trash to this-actually-looks-half-decent, quickly. However, I think a firm grasp on modern *techniques* for creating responsive layouts will still apply to whatever the cool framework is in five years.

Flexbox is mainly used to display elements in a single direction, like a nav bar, whereas grid is better for organizing content both horizontally and vertically, like a full page. Both reduce the need for hackier solutions, such as using clearfix.

- MDN - [guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Realizing_common_layouts_using_CSS_Grid_Layout) to replicating popular layouts with grid
- Scrimba - free, <1 hour video series on [flexbox](https://scrimba.com/learn/flexbox) and g[rid](https://scrimba.com/learn/R8PTE)
- [Flexbox Froggy](https://flexboxfroggy.com/) and [Grid Garden](https://cssgridgarden.com/) - simple games
- [Flexbox Zombies](https://flexboxzombies.com/p/flexbox-zombies) (free) and [Grid Critters](https://gridcritters.com/) (paid) - more comprehensive games

### CSS frameworks and libraries

As I mentioned, frameworks like Bootstrap and Tailwind are awesome — I'm excited to learn both. I'll also highlight some lesser known, simpler resources. No JavaScript knowledge required.

- [Wing](https://kbrsh.github.io/wing/) - a clean, minimal CSS framework
- [Animate.css](https://animate.style/) - library of CSS animations
- [blocks.css](https://thesephist.github.io/blocks.css/) - library for styling any element as a 3D block
- [Hover.css](http://ianlunn.github.io/Hover/) - like it sounds, a collection of CSS hover effects

### Fonts

Companies like Apple and Stripe do typography really well, but I think most of us prefer free fonts. Each of the links below can help with picking out some beautiful ones.

- [FontPair](https://fontpair.co/) - featured font pairings from Google's [repository](https://www.notion.so/08-design-for-devs-2e88e58cca564e3b97f670f4ce9a07eb) of free fonts
- [Colors and Fonts](https://www.colorsandfonts.com/font-pairings) - some additional fonts that play nicely together
- [WhatFont](https://chrome.google.com/webstore/detail/whatfont/jabopobgcpjmedljpbcaablpmlmfcogm?hl=en) - chrome extension that allows you to identify fonts on any page

### Colors

Like with fonts, I can't truly do this justice because it's a deep, deep rabbit hole. For the sake of your time and sanity, here are a few resources for creating solid color palettes, fast.

- [Colormind](http://colormind.io/image/) - generate a color palette from any image
- [Colors and Fonts](https://www.colorsandfonts.com/) - color palettes and a Hex Code to RGBA converter
- [WebGradients](https://webgradients.com/) and [Eggradients](https://www.eggradients.com/) - lots of copy-pasteable color gradients, great for styling buttons

### Illustrations and images

Illustrations are useful for filling the white space on pages with minimal content. These seem to be more common on websites for companies selling technical, complicated products.

- [Ouch](https://icons8.com/illustrations) - free illustrations and graphics
- [unDraw](https://undraw.co/illustrations) - index of illustrations you can customize by color
- [Icons8](https://icons8.com/icons) - popular icons (think Github's logo or the App Store icon) in every style imaginable

### Miscellaneous

Finally, an assortment of tools that didn't fit into any of the above categories.

- [Brandfetch](https://brandfetch.io/) - search engine for retrieving any brand's colors, logos, and icons
- [Clearbit API](https://clearbit.com/logo) - an API to help with programmatically embedding company logos
- [PixelZoomer](http://pixelzoomer.com/) (PC) and [PixelSnap](https://getpixelsnap.com/) (Mac) - tools for measuring anything on screen
- [ColorPick Eyedropper](https://chrome.google.com/webstore/detail/colorpick-eyedropper/ohcpnigalekghcmgcdcenkpelffpdolg?hl=en) - chrome extension for pulling color values from a page
- [CSS Scan](https://getcssscan.com/) - an alternative to sifting through the DevTools console for a page's CSS
