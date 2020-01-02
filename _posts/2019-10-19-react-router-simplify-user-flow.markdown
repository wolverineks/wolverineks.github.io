---
layout: post
title: "React Router: Simplifying a user flow"
date: 2019-10-21 18:40:52 -0800
categories: react react-router
---

## TLDR;

I used `react-router` and nested routers to clean up a particular user flow

## Background

Recently, I've been developing a React Native / Expo application for a client that involves a user flow akin to a registration signup. (~10 screens, in a specific order, with a form)

I've been using `react-router`, (in this case `react-router-native`), like this...

```typescript
// App.tsx
...
<Router>
// ...some other routes


// routes pertaining to a single "entity"
  <Route path={"/path/to/route/a"}>
    <ScreenA />
  </Route>

  <Route path={"/path/to/route/b"}>
    <ScreenB />
  </Route>

  <Route path={"/path/to/route/c"}>
    <ScreenC />
  </Route>
</Router>
...
```

Unfortunately, when using `react-router` this way, every screen in the user flow that links to another route must know the path of that route.

```typescript
// ScreenB.tsx
...
<Link to={"/path/to/route/a"}>Back</Link>
<Link to={"/path/to/route/c"}>Next</Link>
...
```

My attempts to address this include:

1. Pass the next path in as a prop

```typescript
<Route path={"/path/to/route/b"}>
  <ScreenB nextPath={"/path/to/route/c"} />
</Route>
```

2. Pass the `<Link />` in as a prop

```typescript
<Route path={"/path/to/route/b"}>
  <ScreenB nextButton={<Link path={"/path/to/route/c"} />} />
</Route>
```

3. Pull the `<Link />` out into a peer component

```typescript
<Route path={"/path/to/route/b"}>
  <>
    <ScreenB />
    <NavFooter nextPath={"/path/to/route/c"} />
  </>
</Route>
```

### Pros

- They all move the knowledge of the order into a single place.
- 2 and 3 remove the dependency on `<Router />`

### Cons

- Kinda ugly
- Still have to "manage" the knowledge

## My Solution

When messing around one day, I decided to make the app as modular as possible, you know, just for the hell of it. I started by making each "entity" its own "sub-app". This meant putting all the files for a given entity in a separate folder, essentially mirroring the "root-app". I migrated the sub-app closer and closer to the format of the root-app until I came to the part that made me hesitate.... `<Router>`. Hmmm, I thought. Could it work? Could I put a `<Router>` _inside_ another `<Router>`.........?

Yep. So I did. And some neat stuff fell out.

So, apparently `<NativeRouter>` and `<BrowserRouter>` inherit from `<MemoryRouter>`. And `<MemoryRouter>` has an interesting prop, `initialEntries`. This is used to seed the router in your tests with history. Well, if `<MemoryRouter>` has it, then so does everything else.

By using this prop, I can inject into `<Router>`, all the routes, in the correct order, giving me a router that looks like

```typescript
const ENTRIES = ["/a", "/b", "/c"] // <- makes it easy to add, remove, change order
<Router initialEntries={ENTRIES}>
  <Route path={"/a"}>
    <ScreenA />s
  </Route>

  <Route path={"/b"}>
    <ScreenB />
  </Route>

  <Route path={"/c"}>
    <ScreenC />
  </Route>
</Router>
```

and screens that have buttons like

```typescript
// ScreenB.tsx
...
<Link onPress={history.goBack}>Back</Link>
// I turned this into <BackButton /> */
<Link onPress={history.goForward}>Next</Link>
// I turned this into <NextButton />
...
```

## Conclusion

1. Modularity for the win
2. Not all who wander are lost
3. Probably some other stuff
