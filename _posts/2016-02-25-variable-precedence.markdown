---
layout: post
title:  "Variable/Method Name Precedence"
date:   2016-01-29 08:40:52 -0800
categories: jekyll update
---

The following demonstrates the precedence of variable.
The variable 'test' can be assigned in several way, and called in several ways.

{% highlight ruby linenos %}

class TestClass
  attr_accessor :test

  def initialize(test)
    @test = test
  end

  def test
    "this is defined in the method"
  end

  def test_method(test)
    test
  end

  def other_test_method
    test
  end

end

t = TestClass.new("this is the instance variable")

t.test_method("this is the method parameter")

t.other_test_method

{% endhighlight %}

First, when an instance of TestClass is instantiated, the value "this is the instance variable" is assigned to the instance variable "@test".

"attr_accessor" then creates getter/setter methods equivalent to

{% highlight ruby linenos %}
...
def test
  @test
end
...
{% endhighlight %}

Next, a method is named "test". This method is identical to the method created by "attr_accessor", but returns a different value. In this case it returns, "this is defined in the method".

Lastly, a method is defined call "test_method" that takes a parameter called "test" as a local variable, and returns it.

It may not be immediately clear which value will be returned when "test_method" is called. It could be the value that was initially assigned to the instance variable, the value set by the method, or the value of the local variable.

As you can now see, the value that is returned is the value that was passed in as a parameter when the method was called. This illustrates that local parameters take precedence over all other variable/method names.

When there is a potential conflict between an instance variable and a method, as illustrated in the calling of "other_test_method", the method name wins out.

{% highlight ruby linenos %}

t.test_method("this is the method parameter")
#=> "this is the method parameter"

t.other_test_method
#=> "this is defined in the method"
{% endhighlight %}

So, the order of precedence goes like this:

1. local variables
2. method names
3. instance variables/attr_accessor/attr_reader
