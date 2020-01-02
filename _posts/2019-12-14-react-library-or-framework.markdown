---
layout: post
title: "React: Library or Framework? Or something else...."
date: 2019-12-14 18:40:52 -0800
categories: react library framework
---

Have you ever heard someone say this,

> React isn't a framework, it's a library

I have.

So, which camp do you fall in? Is it a library? Is it a framework?

---

## Background

I was tasked not too long ago with creating a React Native app (whatever that is...). After developing for a while, I couldn't help but get the feeling that an app framework should do more than React Native was doing. It just didn't feel like a framework. So, maybe I wasn't building a React Native app. Maybe I was building a React app, and using React Native as more of a component library.

After a little while longer, I started getting a similar feeling but for React. The Redux code I was writing seemed more like application stuff, so maybe I was building a Redux app. But then what was I using React for?

...ummm

...errr

...well

I wasn't sure what.

After longer still, I realized Redux was good at encapsulating business logic, but it too didn't feel like an application framework. Maybe I was building a javascript app and using all that other stuff cobbled together to make a framework? Maybe....?

So to better clarify these thoughts, I made an app. It's a simple app. TicTacToe. [Here is is](https://csb-0q363.netlify.com/), just so you believe me.

{% codesandbox tic-tac-toe-0q363 %}

Then, I looked at all the places where I used React to see if I could figure out what I was using it for. If it's used for "fundamental stuff" that shapes the app, then it must be a framework, right?

---

## import \* as React from 'react'

Let's take a look at one example of using React

```typescript
// Display.tsx
import * as React from "react";

import { TicTacToeContext } from "../../connect";
import { Col } from "../../../utils";

interface Props {}
interface State {
  display: boolean;
}

export class Display extends React.Component<Props, State> {
  static contextType = TicTacToeContext;
  context: React.ContextType<typeof TicTacToeContext>;

  state = {
    display: true
  };

  render() {
    const { gameOver, currentPlayerId, winnerId, tied, newGame } = this.context;
    const { display } = this.state;

    return (
      <>
        {display ? (
          <button onClick={() => this.setState({ display: false })}>
            Hide
          </button>
        ) : (
          <button onClick={() => this.setState({ display: true })}>Show</button>
        )}
        {display && (
          <Col>
            {!gameOver && `Current Player: ${currentPlayerId}`}
            {gameOver && (
              <>
                {winnerId && `${winnerId} Won!`}
                {tied && "Tied!"}
                <button onClick={newGame}>New Game?</button>
              </>
            )}
          </Col>
        )}
      </>
    );
  }
}
```

It's a pretty harmless component definition. And it depends on React for a few things. Let's see what we are actually using it for.

---

### React.Component

This component is written using the older (no longer recommended) class syntax. But we could just as easily write this using the "newer" syntax (good old javascript functions). And seeing how classes are kinda like syntactic sugar for functions anyway, let's drop one use of React, and re-write it like this:

```typescript
export const Display: React.FC = () => {
  const [display, setDisplay] = React.useState(true);
  const {
    gameOver,
    currentPlayerId,
    winnerId,
    tied,
    newGame
  } = React.useContext(TicTacToeContext);

  return (
    <>
      {display ? (
        <button onClick={() => setDisplay(false)}>Hide</button>
      ) : (
        <button onClick={() => setDisplay(true)}>Show</button>
      )}
      {display && (
        <Col>
          {!gameOver && `Current Player: ${currentPlayerId}`}
          {gameOver && (
            <>
              {winnerId && `${winnerId} Won!`}
              {tied && "Tied!"}
              <button onClick={newGame}>New Game?</button>
            </>
          )}
        </Col>
      )}
    </>
  );
};
```

### Types

It looks like we traded one use of React for several more...

```typescript
export const Display: React.FC = () => { ... }
```

So, this application is created with [typescript](https://www.typescriptlang.org/), which is then compiled to javascript. React exports some types to help us write typescript. But these types are for the developer, and not for app functionality. We could remove these and the application would still run just fine.

### JSX

Even if we were to eliminate every explicit use of React in this component, there would still be one more implicit use: [JSX](https://reactjs.org/docs/introducing-jsx.html).

Basically, JSX is a syntactic sugar that is meant to be compiled into valid javascript. Well, what does it get de-sugared to?

I'm glad you asked

This:

```typescript
const element = <h1 className="greeting">Hello, world!</h1>;
```

Becomes this:

```typescript
const element = React.createElement(
  "h1",
  { className: "greeting" },
  "Hello, world!"
);
```

But these function calls get evaluated to (roughly) this:

```typescript
const element = {
  type: "h1",
  props: {
    className: "greeting",
    children: "Hello, world!"
  }
};
```

So, React in this capacity, is syntactic sugar and helper functions. We could go so far as to replace all of the JSX in `Display.tsx` with the objects that they would evaluate to, and eliminate one more use of `react`.

You can read more about this [here](https://reactjs.org/docs/react-without-jsx.html)

And mess around with a little demo [here](https://codesandbox.io/s/what-is-jsx-3eje3)

### Context

I see that this component uses context. That seems kinda significant. So, what's that all about?
`React.createContext` doesn't do anything all that special. Much like the `React.createElement` used in JSX, it's a function to help create a plain old javascript object.

From a [blog post](https://overreacted.io/how-does-setstate-know-what-to-do/) by Dan Abramov,

```typescript
// A bit simplified
function createContext(defaultValue) {
  let context = {
    _currentValue: defaultValue,
    Provider: null,
    Consumer: null
  };
  context.Provider = {
    $$typeof: Symbol.for("react.provider"),
    _context: context
  };
  context.Consumer = {
    $$typeof: Symbol.for("react.context"),
    _context: context
  };
  return context;
}
```

### Hooks

So, React provides the `Component` class (replaced by plain old javascript functions), it provides types (not required to make the app run), it enables JSX which is syntactic sugar for `React.createElement` which, along with `React.createContext`, is a helper function to create properly shaped objects.

But it also has that state persistence thing and side effects thing with hooks and all. So for sure it looks like it's creeping into framework territory, right?

```typescript
const [display, setDisplay] = React.useState(true);
```

Yeah, about that. React doesn't really do that.

According to Dan Abramov, it's the renderers (react-dom, react-native, and others) that do this, and all of the interesting stuff. Here are a few snippets from his blog post [How Does setState Know What to Do?](https://overreacted.io/how-does-setstate-know-what-to-do/)

---

> There is a common misconception that the React “engine” lives inside the react package. This is not true.

> In fact, ever since the package split in React 0.14, the react package intentionally only exposes APIs for defining components. Most of the implementation of React lives in the “renderers”.

---

> the base class setState() implementation has been an illusion all along. It doesn’t do anything except forwarding the call to the current renderer. And useState Hook does exactly the same thing.

---

> Okay, so now we know that the react package doesn’t contain anything interesting, and the implementation lives in renderers like react-dom, react-native, and so on.

## Case Closed

So React helps developers by providing some niceties, and all the interesting bits are contained in the renderer. So, that seems like case-closed for the library / framework question. But why was this a question to begin with?

I believe the confusion stems from 3 places.

I see value in distinguishing between `ReactJS` / `React` and `react`. I consider `react` to mean the package, and `ReactJS` / `React` to mean the ecosystem. The ecosystem is full of mix-n-match plugins, utilities, helpers, systems, patterns, techniques, and whatever's. With enough of these, you could surely build something that resembles a framework.

Until version 0.14, the `react` package was all inclusive. It contained all the interesting bits, like state management, context, and the renderer.

And my favorite, calling react a "UI Library". "UI Library" sounds so final to me. Like, "This is the library I use to make UI's". But I've used plenty of libraries to make UI's. Libraries like [momentjs](https://momentjs.com/). But I would never say I was building a momentjs app. Would you?

## Conclusion

In the end, what we call things is a matter of preference, tradition, and expediency. I try to avoid ambiguous terms that have caused confusion, but I'm not dogmatic about it. I won't chew your head off for calling React a framework. Then what's my preference? What do I call it. I think the [official website](https://reactjs.org/) has my favorite description.

> React

> A JavaScript library for building user interfaces
