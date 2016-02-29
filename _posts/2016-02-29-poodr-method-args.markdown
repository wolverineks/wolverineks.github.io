---
layout: post
title:  "POODR Method Args"
date:   2016-02-28 08:40:52 -0800
categories: jekyll update
---

In POODR, Sandi Metz talks about how when programming in an OO paradigm, it is important to minimize dependencies. This blog post will talk about one technique to remove the dependency on method argument sequencing.

This is an example of a typical class in Ruby, and how you initialize a new instance.

{% highlight ruby linenos %}

class SomeClass
  attr_accessor :arg1, :arg2, :arg3

  def initialize(arg1, arg2, arg3)
    @arg1 = arg1
    @arg2 = arg2
    @arg3 = arg3
  end
end

{% endhighlight %}

{% highlight ruby linenos %}

SomeClass.new(arg1, arg2, arg3)

{% endhighlight %}

To enable your class to receive all the same arguments but in any order, simply alter your class to initialize like this:

{% highlight ruby linenos %}

class SomeClass
  attr_accessor :arg1, :arg2, :arg3

  def initialize(args)
    @arg1 = args[:arg1]
    @arg2 = args[:arg2]
    @arg3 = args[:arg3]
  end
end

{% endhighlight %}

{% highlight ruby linenos %}

SomeClass.new(arg1: some_value1, arg2: some_value2, arg3: some_value3)

{% endhighlight %}

You will now need to initialize a new instance of your class by passing in a hash of arguments. However, this allows you to access the individual arguments in any order you specify in your initialize method. Not only that, but when you read the method call, it is readily apparent what each argument is. This is a simple way to permanently and effortlessly increase the flexibility of your Ruby code.

Happy Coding!
