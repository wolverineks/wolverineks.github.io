---
layout: post
title:  "Enumerable Methods"
date:   2016-01-29 08:40:52 -0800
categories: jekyll update
---

According to [ruby-docs.org][ruby-docs],

> Enum#map returns a new array with the results of running block once for every element in enum.

If no block is given, an enumerator is returned instead.
But what does this mean?
#map is going to create and return a new array or hash.
It will also execute the code inside the block once for every element in the array or hash.
It will take the results for executing the code, and put it into the new array.
This code may modify elements from the original array/hash, or not.
Here are the examples from ruby-docs.org
{% highlight ruby linenos %}
(1..4).map { |i| i*i }      #=> [1, 4, 9, 16]
{% endhighlight %}


{% highlight ruby linenos %}
(1..4).collect { "cat"  }   #=> ["cat", "cat", "cat", "cat"]
{% endhighlight %}

In the first example, #map is iterating over the array, accessing the element of the current iteration, squaring it, and putting it into the returned array.
In the second example, #collect (an alias for #map), is iterating over the array, executing the block of code (which is just the string "cat"), and inserting the result into the returned array.
The same will happen if the method were called on a hash.
{% highlight ruby linenos %}
{a:1, b:2}.map { "cat" }    #=> ["cat", "cat"]
{% endhighlight %}

To demonstrate that this methods returns a new array...
{% highlight ruby linenos %}
a = (1..4)
a.map { |i| i*i } == a    #=> false
{% endhighlight %}

[ruby-docs]: http://ruby-doc.org/core-2.3.0/Enumerable.html#method-i-map
