---
layout: post
title: "React Component Readability"
date: 2019-09-10 18:40:52 -0800
categories: react component readability
---

Recently, someone asked for a second set of eyes on a component they had written. They indicated that they wanted a better way to write it, but didn't specify what they thought could use improvement. 

In cases like these, I like to chant the mantra
> Make it work
> Make it pretty
> Make it fast

In this case, the code works. So, on to step 2. (I rarely ever go on to step 3)

Here is the original code.
```typescript
// yada yada yada, imports...

interface StatusBarProps {
  accent: string;
}

const MyStatusBar = ({ accent }: StatusBarProps) => {
  switch (accent) {
    case "yellow":
      if (Platform.OS === "ios") {
        return (
          <View
            style={{
              width: "100%",
              height: getStatusBarHeight(),
              backgroundColor: COLORS.yellow,
            }}
          >
            <StatusBar
              translucent={false}
              barStyle="light-content"
              backgroundColor={COLORS.yellow}
            />
          </View>
        );
      } else {
        return (
          <StatusBar
            translucent={false}
            barStyle="light-content"
            backgroundColor={COLORS.yellow}
          />
        );
      }
    case "purple":
      if (Platform.OS === "ios") {
        return (
          <View
            style={{
              width: "100%",
              height: getStatusBarHeight(),
              backgroundColor: COLORS.purple,
            }}
          >
            <StatusBar
              translucent={false}
              barStyle="light-content"
              backgroundColor={COLORS.purple}
            />
          </View>
        );
      } else {
        return (
          <StatusBar
            translucent={false}
            barStyle="light-content"
            backgroundColor={COLORS.purple}
          />
        );
      }
    default:
      return (
        <StatusBar
          translucent={false}
          barStyle="light-content"
          backgroundColor={COLORS.white}
        />
      );
  }
};
```

## What does it do?

My first observation is this component does not **scream** what is does. A *real* 10x developer reads 10x more code than they write. So anything you can do to reduce the time it takes for someone to read your code will pay dividends.

It appears that this component does 2 things:
* Add a `<View>` wrapper on ios and not on android
* Set the background color based on a prop

Well, [unix philosophy](https://en.wikipedia.org/wiki/Unix_philosophy), roughly speaking, says

> Do one thing, and do it well.

So, let's break this into to parts.

### Platform Specific Imports

In the React Native docs you can find a section on [Platform Specific Imports](https://facebook.github.io/react-native/docs/platform-specific-code#platform-specific-extensions)

This means that when using `import { MyStatusBar } from "./MyStatusBar`, react-native will automatically import the component from `MyStatusBar.android.tsx` on android and `MyStatusBar.ios.tsx` on ios. With this we can remove the platform-based logic from the component.

```typescript
if (Platform.OS === "ios") {
  ...yada yada ios stuff
} else {
  ...yada yada android stuff
}
```

### What does a `switch` statement do?

In the switch statement, the cases seem pretty similar. This makes it difficult to know what the `switch` statement is doing. To determine what a specific `switch` statement is doing, look at what the differences are between the `case`s. In this instance, the only difference in the `case`s are the value passed to `backgroundColor`. So, if we limit this `switch` statement to only determining that value, we can reduce the component to:

```typescript
// MyStatusBar.android.tsx
// ...stuff

let backgroundColor = COLORS.white
switch (accent) {
  case "yellow": backgroundColor = COLORS.yellow
  case "purple": backgroundColor = COLORS.purple
}

return <StatusBar translucent={false}
  barStyle="light-content"
  backgroundColor={backgroundColor} />
```

or better still

```typescript
// MyStatusBar.android.tsx
// ...stuff

const DEFAULT_BACKGROUND_COLOR = COLORS.white

// ...more stuff

return <StatusBar translucent={false}
  barStyle="light-content"
  backgroundColor={COLORS[accent] || DEFAULT_BACKGROUND_COLOR} />
```

## Conclusion

When writing a component, or any code for that matter, I ask myself some questions about some future developer that is reading this code for the first time, or the first time in a while...

* How long will it take them to know what this code does?
* Are there any parts of the code that take them longer to understand than others?
* Will they need to know what each part of this code does, or can some of it abstracted away?
* Are they aware of alternatives that are more standardized/recognizable than any of the patterns used here?
* Are they confused about the naming of any variables?
* Are they confused about the number of parameters, or their types?
* Which parts of this code would they need to change in order to implement some possible changes in the future?
* When implementing changes, which part of this code is more likely going to be a foot-gun?

So yeah, that's it on that topic. 

I'd be interested in any examples you have of refactoring React components to increase readability, so please put them in the comments.

Thanks.