---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="YIELD"></a>

### YIELD

<div class="test" data-clipboard-text="expect { |b| MyClass.yield_once_with(1, &b) }.to yield_control">

{% highlight ruby linenos %}
expect { |b| MyClass.yield_once_with(1, &b) }.to yield_control
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { |b| MyClass.dont_yield(&b) }.not_to yield_control">

{% highlight ruby linenos %}
expect { |b| MyClass.dont_yield(&b) }.not_to yield_control
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.twice">

{% highlight ruby linenos %}
expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.twice
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.exactly(2).times">

{% highlight ruby linenos %}
expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.exactly(2).times
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.at_least(1)">

{% highlight ruby linenos %}
expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.at_least(1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.at_most(3).times">

{% highlight ruby linenos %}
expect { |b| MyClass.yield_twice_with(1, &b) }.to yield_control.at_most(3).times
{% endhighlight %}

</div>

_______________________________________________________________
