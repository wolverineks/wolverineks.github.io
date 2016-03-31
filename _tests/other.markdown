---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---








## TYPE

<div class="test" data-clipboard-text="expect(a).to be(b)">

{% highlight ruby linenos %}
expect(a).to be(b)
# passes if a.equal?(b)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_instance_of(type)">

{% highlight ruby linenos %}
expect(obj).to be_instance_of(type)
# passes if obj is an instance of type
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_a_kind_of(type)">

{% highlight ruby linenos %}
expect(obj).to be_a_kind_of(type)
# same as expect(obj).to be_kind_of(type)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_a(type)">

{% highlight ruby linenos %}
expect(obj).to be_a(type)
# same as expect(obj).to be_kind_of(type)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_an(type)">

{% highlight ruby linenos %}
expect(obj).to be_an(type)
# same as expect(obj).to be_kind_of(type)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_an_instance_of(type)">

{% highlight ruby linenos %}
expect(obj).to be_an_instance_of(type)
# same as expect(obj).to be_instance_of(type){% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

_______________________________________________________________





<div class="test" data-clipboard-text="expect(obj).to respond_to(:foo)">

{% highlight ruby linenos %}
expect(obj).to respond_to(:foo)
# pass if obj.respond_to?(:foo)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to respond_to(:foo, :bar)">

{% highlight ruby linenos %}
expect(obj).to respond_to(:foo, :bar)
# passes if obj.respond_to?(:foo) && obj.respond_to?(:bar)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to respond_to(:foo).with(1).argument">

{% highlight ruby linenos %}
expect(obj).to respond_to(:foo).with(1).argument
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to respond_to(:bar).with(2).arguments">

{% highlight ruby linenos %}
expect(obj).to respond_to(:bar).with(2).arguments
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(10).to satisfy { |v| v % 5 == 0 }">

{% highlight ruby linenos %}
expect(10).to satisfy { |v| v % 5 == 0 }
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(7).not_to satisfy { |v| v % 5 == 0 }">

{% highlight ruby linenos %}
expect(7).not_to satisfy { |v| v % 5 == 0 }
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(10).to satisfy('be a multiple of 5') do |v|\nv % 5 == 0\nend">

{% highlight ruby linenos %}
expect(10).to satisfy("be a multiple of 5") do |v|
 v % 5 == 0
end
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { throw :foo }.to throw_symbol">

{% highlight ruby linenos %}
expect { throw :foo }.to throw_symbol
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { throw :foo }.to throw_symbol(:foo)">

{% highlight ruby linenos %}
expect { throw :foo }.to throw_symbol(:foo)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { throw :foo, 7 }.to throw_symbol(:foo, 7)">

{% highlight ruby linenos %}
expect { throw :foo, 7 }.to throw_symbol(:foo, 7)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

_______________________________________________________________
