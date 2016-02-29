---
layout: post
title:  "Javascript"
date:   2016-02-14 08:40:52 -0800
categories: jekyll update
---

Both Javascript and Ruby have a built in mechanism for iterating over arrays.

In ruby, you can initialize a variable simply by typing the name of the variable and then
assigning the array to that variable.

Then you use the .each method, use the do..end syntax, and include the code that you wish to execute
for each element of the array.

{% highlight ruby linenos %}

some_array = [1,2,3,4,5]

some_array.each do |element|
  do something
end

{% endhighlight %}

Here is how to iterate over an array in Ruby.

In Javascript, you can iterate over an array by initializing a variable with the keyword 'var', typing the
name of the variable you wish to use, and assigning the array to that variable.

Then, you use the for syntax to iterate over the array. The 'i' is used as an index counter. It is incremented
with the 'i++' syntax. Inside the { } you write whatever code you wish to execute for each element of the array.

{% highlight ruby linenos %}

var someArray = [1,2,3,4,5];

for (i = 0; i < someArray.length; i++) {
  do something;
}

{% endhighlight %}

Here is how to iterate over an array in Ruby.
