---
layout: post
title:      "10: transitions in React with 10 lines of code"
date:       2020-11-30 16:07:20 +0000
permalink:  10_transitions_in_react_with_10_lines_of_code
---


There are plenty of ways to add page transitions to a React application, this tutorial outlines a really simple one. It requires minimal effort but can make your single page app look a lot more professional.

---

Before we get into animations for the different routes, we'll build a fade-in transition for our initial page load. This is pretty simple with the CSS `animation` property.

```jsx
// your-app/src/App.css 

body {
  animation: fadeIn 1s ease;
}

@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}
```

Let's unpack that first ruleset. We're using a shorthand property instead of 3 separate declarations in the same block.

```jsx
// option a
body {
	animation-name: fadeIn; // specifying the name of our @keyframes animation
	animation-duration: 1s; // which should take 1 second to complete
	animation-timing-function: ease; // and start slowly, speed up, and finish slowly
}

// option b
body {
  animation: fadeIn 1s ease; // equivalent, much more concise declaration
}
```

So we're binding our selector —`body`, the whole page — to this animation `fadeIn` which has 2 keyframes.

Keyframes are basically checkpoints in the life of a CSS animation. We're only setting two of them here, indicating that we want to begin the animation with opacity set to 0 and end it with opacity set to 1.

```jsx
@keyframes fadeIn {
  0% { opacity: 0; } // from
  100% { opacity: 1; } // to
}
```

Tying the animation and keyframes declarations together, here's how we can interpret the code below in plain English:

- We're applying an animation called `fadeIn` to the entire page `body` on initial page load.
- The page will start out as completely transparent with opacity set to 0.
- Opacity will increase slowly, then more quickly, and slowly again until it finally reaches a value of 1. The page will finally be completely visible.
- This transition will occur over the span of one second.

```jsx
// your-app/src/App.css 

body {
  animation: fadeIn 1s ease;
}

@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}
```

Adding these seven lines of code to our stylesheet, we now have a fade-in transition on initial page load. Let's finish up with some transitions between our child routes. 

---

First, head over to the `react-fader` package [documentation](https://github.com/jcoreio/react-fader) and spend a few minutes reading through it.

 

In one of the code snippets provided, we see that the `TransitionSwitch` component from the `react-router-transition-switch` package can replace a `Switch` component.

```jsx

import { Route, BrowserRouter as Router } from 'react-router-dom'
~~import { Switch } from 'react-router'~~
import TransitionSwitch from 'react-router-transition-switch'
import Fader from 'react-fader'

<Router>
	~~<Switch>~~
  <TransitionSwitch component={Fader}>
    <Route path="/red" component={Red}/>
    <Route path="/green" component={Green} />
    <Route path="/blue" component={Blue} />
  </TransitionSwitch>
	~~</Switch>~~
<Router>
```

We needed to swap in the `TransitionSwitch` component so that we can pass it a prop: our `Fader` component. On transitions between routes, this will fade out the old route's children and fade in those for the new one.

```jsx
// here's how I implemented this in my React app
import './App.css'
import Navbar from './components/Navbar'
import { Route } from 'react-router-dom'
**import TransitionSwitch from 'react-router-transition-switch'**
**import Fader from 'react-fader'**
import Generator from './containers/Generator'
import IdeasIndex from './containers/IdeasIndex'
import About from './containers/About'

const App = () => {
  return (
    <div className="App">
      <Navbar />
      **<TransitionSwitch component={Fader}>**
        <Route exact path="/"> <Generator /> </Route>
        <Route exact path="/all"> <IdeasIndex /> </Route>
        <Route exact path="/about"> <About /> </Route>
      **</TransitionSwitch>**
    </div>
  )

}

export default App
```

I think the default settings look really clean but feel free to play with some of the other props detailed in the docs. Hope this helps :)
