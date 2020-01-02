---
layout: post
title: "React Hook: useSideMenu"
date: 2019-10-05 18:40:52 -0800
categories: react react-native hook side-menu
---

# TLDR;

Here is a snack similar to how I'm implementing a side menu in a React Native / Expo app
https://snack.expo.io/@wolverineks/withsidemenu

# Background

I'm currently building a [React Native](https://facebook.github.io/react-native/) / [Expo](https://docs.expo.io/versions/latest/) app for a client. The app uses [React Router](https://reacttraining.com/react-router/), and [React Native Drawer](https://github.com/root-two/react-native-drawer).

Some of the routes have a side menu, and some do not. So I wrote context like...

```typescript
interface SideMenuContext {
  open: () => void;
  close: () => void;
  enable: () => void;
  disable: () => void;
  enabled: boolean;
  shouldOpen: boolean;
}
```

and a hook like...

```typescript
export const useSideMenu = () => {
  const sideMenu = React.useContext(SideMenuContext);
  if (sideMenu === undefined) {
    throw new Error("useSideMenu must used in a SideMenuProvider");
  }
  const { enable, disable, close } = sideMenu;

  React.useEffect(() => {
    enable();

    return () => {
      disable();
      close();
    };
  }, []);

  return sideMenu;
};
```

and on the screens that have a side menu:

```typescript
const SomeScreen = () => {
  useSideMenu()

  return ...yada...yada...yada
}
```

## Can anyone spot the undesirable behavior?

So, I noticed a few things about this approach that I didn't like.

1. The imperative nature of the hook api meant that if (for some reason) multiple components that `useSideMenu` are mounted simultaneously, removing _any_ of them would disable the side menu. The behavior I was looking for was, disabling the side menu only if _all_ of the components were unmounted.

2. When testing the screens in isolation, a `<SideMenuProvider />` would have to be mounted, or the hook would throw an error.

## Next Steps

To overcome the second issue, I've written a component, `<WithSideMenu />`, and moved the `useSideMenu()` call from just inside the screens, to just outside of the screens...

```typescript
<WithSideMenu>
  <SomeComponent />
</WithSideMenu>
```

And, to overcome the first issue, I've rewritten the context to...

```typescript
interface SideMenuContext {
  open: () => void;
  close: () => void;
  register: () => () => void; // <- returns an "unregister"
  enabled: boolean;
  shouldOpen: boolean;
<Drawer />
}

```

to be used like...

```typescript
const WithSideMenu: React.FC = ({ children ) => {
  const sideMenu = useSideMenu()
  const { register } = sideMenu;

  React.useEffect(register, []);

  return typeof children === "function"
    ? children(sideMenu)
    : children;
};
```

## Conclusion

1. Declarative for the win.
2. Composition for the win.
3. Probably some other stuff...

Here is the snack again:

https://snack.expo.io/@wolverineks/withsidemenu
