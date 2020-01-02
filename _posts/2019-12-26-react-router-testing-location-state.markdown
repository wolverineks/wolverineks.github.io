---
layout: post
title: "React Router: testing "location.state""
date: 2019-12-14 18:40:52 -0800
categories: react router testing
---

# Background

In the react channel on Spectrum, someone asked how to test that a component displayed data provided by `location.state` from `react-router-dom`. I had never done this before, so I sought to find out how to do it.

After some investigation, and trial and error, I came up with the following...

```typescript
import * as React from "react";
import { render } from "@testing-library/react";
import { Router } from "react-router-dom";
import { createMemoryHistory } from "history";
import { App } from "./App";

it("renders location state", () => {
  const history = createMemoryHistory();
  const state = { a: 123, b: 456 };
  history.push("/", state);

  const { getByText } = render(
    <Router history={history}>
      <App />
    </Router>
  );

  getByText(state.a);
  getByText(state.b);
});
```

# Other Interesting Tidbits

- `<MemoryRouter history={createMemoryHistory(...)}>` doesn't work

- `<BrowserRouter history={createBrowserHistory(...)}>` does work, but doesn't typecheck

- According to [the docs](https://github.com/ReactTraining/history/blob/master/docs/Navigation.md)

> Note: Location state is only supported in createBrowserHistory and createMemoryHistory.

[and here](https://github.com/ReactTraining/history/blob/master/docs/GettingStarted.md)

> location.state - Some extra state for this location that does not reside in the URL (supported in createBrowserHistory and createMemoryHistory)

# Conclusion

So, this seems to work. It passes the tests.
Know of a better way? See any problems? Let me know, thanks.
