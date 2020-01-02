---
layout: post
title: "Untangle React Contexts"
date: 2019-08-18 18:40:52 -0800
categories: react context composition
---

Recently on Twitter a [question](https://twitter.com/ovidme/status/1162873760489381894) was asked, roughly, how to untangle 2 react contexts that use state/callbacks provided by each other.

Several answers were suggested, ranging from combining them into a single context, to using callbacks from one context to sync state with another.

While I have no doubt that any of the provided solutions could be made to work, I couldn't help but think about another solution that I think is more in the react style of [composition](https://dev.to/bouhm/thinking-in-react-component-composition-fp5).

So, without further ado, my solution:

<iframe
     src="https://codesandbox.io/embed/fast-sun-w0tsj?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="fast-sun-w0tsj"
     allow="geolocation; microphone; camera; midi; vr; accelerometer; gyroscope; payment; ambient-light-sensor; encrypted-media; usb"
     sandbox="allow-modals allow-forms allow-popups allow-scripts allow-same-origin"
   ></iframe>

Much like the [unix philosophy](https://en.wikipedia.org/wiki/Unix_philosophy) of "Do 1 thing, and do it well", each context is reduced to a single responsibility. The two original contexts can now be used independently, with the third context doing only the composition.

Feel free to provide feedback. Good? Bad? Pro's / Con's?
