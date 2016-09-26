---
layout: post
title:  "Ruby Arrays"
date:   2016-09-26 18:40:52 -0800
categories: jekyll ruby array
---

So, I found some behavior when accessing elements in a Ruby array that I found to be a bit counter-intuitive.

Suppose you have some array, and you want to access the 0th element. You might do this:

```
2.3.1 :001 > a = [1, 2, 3]
 => [1, 2, 3]
2.3.1 :002 > a[0]
 => 1
```
Seems logical. Now, try to access the 3th element.
```
2.3.1 :003 > a[3]
 => nil
```
Alright, so accessing a non-existent element in an array returns nil. Cool.
Not try to access 2 non-existent elements in the array.
```
2.3.1 :004 > a[3..4]
 => []
```
Huh, I might have expected an array of 2 nils...but alright.
Now let's try and access a different set of 2 non-existent elements.
```
2.3.1 :005 > a[4..5]
 => nil
```
What? So, when attempting to access elements beyond the end of the array, if you are including the nth + 1 element, you get an ```[]```, if you don't you get ```nil```....Right....

Ok, so what if we try to access an element that exist and an element that doesn't.
```
2.3.1 :006 > a[2..4]
 => [3]
```
We get an array of just the elements that exist. So, attempting to access the elements of a array, will not return an array of the results of each attempt. It will return an array of all the non-nil values of those attempts.

Now, what if we have an array, that may have nils in it...
```
2.3.1 :007 > b = [nil, nil, nil]
 => [nil, nil, nil]
```
And what if we try to access the 0th element?
```
2.3.1 :008 > b[0]
 => nil
```
And the 99th element?
```
2.3.1 :009 > b[99]
 => nil
```
Same result. So you don't know if you retrieved a ```nil``` or if you are trying to access beyond the end of the array.

Now, let's try accessing elements n + 1 and n + 2...
```
2.3.1 :010 > b[3..4]
 => []
```
Same weird behavior as before.

Now let's try and access a different set of 2 non-existent elements.
```
2.3.1 :011 > b[4..5]
 => nil
```

Yeah, so watch out for counter-intuitive behavior when accessing elements in a Ruby array. I haven't checked this behavior in other languages. But now I know to be on the lookout.
