---
layout: post
title: "React Context: (CRUD / REST)-ful Entities"
date: 2019-10-22 18:40:52 -0800
categories: react context rest crud
---

# TLDR;

Here's a codesandbox that uses react context to create a (CRUD / REST)-like interface to local entities. (think: index, new, show, edit, update, destroy)

<iframe
     src="https://codesandbox.io/embed/posts-context-8y1ub?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:500px; border:0; border-radius: 4px; overflow:hidden;"
     title="posts-context"
     allow="geolocation; microphone; camera; midi; vr; accelerometer; gyroscope; payment; ambient-light-sensor; encrypted-media; usb"
     sandbox="allow-modals allow-forms allow-popups allow-scripts allow-same-origin"
   ></iframe>

# Background

Recently, I've been in a [codesandbox.io](https://codesandbox.io/) template kick, making starter templates for various purposes. I've got one for [generic react](https://codesandbox.io/s/starter-rtsh3), one for [react with react-router](https://codesandbox.io/s/starter-router-7t7v6). And now, I've got one for a [react context](https://codesandbox.io/embed/posts-context-8y1ub).

# Meat n' Potatoes

In this template, the context provides a restful-ish interface for a `Posts` entity.

The context provides a state like this:

```typescript
interface State {
  posts: { [id: string]: Post };
  ids: Post["id"][];
}

...

const ids = usePostIds(); // index-ish
const posts = usePosts(); // index
const post = usePost(123) // show / edit
```

And behavior like this:

```typescript
const newPost = useNewPost()          // create
const updatePost = useUpdatePost(123) // update
const deletePost = useDeletePost(123) // destroy

...

<button onClick={() => newPost({ id: 123, title: "first post" })}>Create</button>
<button onClick={() => updatePost({ ...post, title: "updated: })}>Update</button>
<button onClick={() => deletePost()}>Delete</button>

```

# Thoughts...

Well, I haven't put it into anything significant yet, but it _seeeeeeems_ like it makes it simple to add a new entity to keep track of, if you want to treat it in a similar way.

I was able to encapsulate some basic async stuff in the components, and keep all the local state management synchronous.

```typescript
const savePostToRemoteServer = (post: Post) => {
  setPending(true);
  return wait(1000)
    .then(() => {
      if (!isMounted()) return;
      newPost(post);
    })
    .finally(() => {
      if (!isMounted()) return;
      setPending(false);
      setTitle("");
    });
};
```

I haven't done any error handling, so who know how that would go. Probably keep it all in the components alongside the async stuff.

It's not super faithful to either CRUD or REST and the naming convention is mixed, so...who knows.

# Anyway....

Here's the link to the codesandbox if you want to dive more into it.

https://codesandbox.io/s/posts-context-8y1ub?fontsize=14&module=%2Fsrc%2FApp.tsx

# Feedback

Let me know what you all think. Your feedback is very valuable.
Thanks.
