---
layout: post
title:  "Arrays and Hashes"
date:   2016-01-20 08:40:52 -0800
categories: jekyll update
---

Arrays and Hashes are useful object in Ruby. You can use them to store information. In this post we will discuss what arrays and hashes are, when to use them, how to create them, and provide some examples.


# Arrays

According to Ruby-Doc.org,

> Arrays are ordered, integer-indexed collections of any object.

But what does this mean?

This means an array is a single object that can contain many different objects, making it easy to manipulate and use. You can consider it a single list, with many items on it, but which can be used simply by referencing the name of the list.

Example: If you have a list of students in a class, you could create an array, add all the names of the students, then do something interesting with all the names in one foul swoop, instead of keeping track of each student individually, and duplicating the same code to use each of the students.


{% highlight ruby linenos %}

# creates an array
students = ["Tom", "Dick", "Harry", "Sally"]

{% endhighlight %}


{% highlight ruby linenos %}

# iterates though the array and does something
# interesting with each student
students.each do |student|
  student.do_something_interesting
end

{% endhighlight %}

To accomplish the same task without an array would take dozens of lines of code, take more time to write, and increase the potential for mistakes.

Here are some additional ways you can create and manipulate arrays.

{% highlight ruby linenos %}

# Creates a new, empty array, assigns it to some_variable
some_variable = Array.new()

{% endhighlight %}


{% highlight ruby linenos %}

# Creates a new, empty array, assigns it to some_variable
some_variable = []

{% endhighlight %}


{% highlight ruby linenos %}

# Creates a new array, with 3 nil values, assigns it to some_variable
some_variable = Array.new(3)

{% endhighlight %}



Here are some ways to access the elements of an array.

{% highlight ruby linenos %}

# gives access to the first element of an array
some_array[0]

{% endhighlight %}


{% highlight ruby linenos %}

# gives access to the last element of an array
some_array[-1]

{% endhighlight %}


{% highlight ruby linenos %}

# gives access to the 2nd element through the 5th element
some_array[1..4]

{% endhighlight %}


Here are some ways to add elements to an array.

{% highlight ruby linenos %}

# adds some_element to some_array
some_array << some_element

{% endhighlight %}


{% highlight ruby linenos %}

# adds some_element to some_array
some_array.push(some_element)

{% endhighlight %}


Here are some ways to remove elements from an array.

{% highlight ruby linenos %}

# removes the last element from the array
some_array.pop

{% endhighlight %}


{% highlight ruby linenos %}

# removes the first element from the array
some_array.shift

{% endhighlight %}


Hash

According to Ruby-Doc.org,

> A Hash is a dictionary-like collection of unique keys and their values. Also called associative arrays, they are similar to Arrays, but where an Array uses integers as its index, a Hash allows you to use any object type.

But what does this mean?

This means that while an array is like an ordered list, with each element referenced with a number, a hash is a list where you get to choose the thing that each element is references with.

Hashes are useful when you have a list of items that each have a value you want to keep track of.

Example: If you had a list of classes, and you wanted to keep track of how many students were in each class.


{% highlight ruby linenos %}

# creates a new hash and stores some information in it
classes = {
history: 25,
literature: 23,
geography: 15,
mathematics: 32,
}

{% endhighlight %}


To accomplish the same task without a hash would take dozens of lines of code, take more time to write, and increase the potential for mistakes.

{% highlight ruby linenos %}

# Creates a new, empty hash, assigns it to some_variable
some_variable = Hash.new

{% endhighlight %}


{% highlight ruby linenos %}

# Creates a new, empty hash, assigns it to some_variable
some_variable = {}

{% endhighlight %}


Here are some ways to access the elements of an hash.

{% highlight ruby linenos %}

# gives access to the value accociated with :some_key
some_hash[:some_key]

{% endhighlight %}


Here are some ways to add elements to an hash.

{% highlight ruby linenos %}

# adds some_element to some_hash
some_hash[:some_key] = some_value

{% endhighlight %}


Here are some ways to remove elements from an hash.

{% highlight ruby linenos %}

# removes the first key_vlue pair from the hash
some_hash.shift

{% endhighlight %}
