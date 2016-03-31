---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="INTEGERS"></a>

### INTEGERS

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { 3 / 0 }.to raise_exception">

{% highlight ruby linenos %}
expect { 3 / 0 }.to raise_exception
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to eql(b)">

{% highlight ruby linenos %}
expect(a).to eql(b)
# passes if a.eql?(b)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to equal(b)">

{% highlight ruby linenos %}
expect(a).to equal(b)
# passes if a.equal?(b)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to eq(b)">

{% highlight ruby linenos %}
expect(a).to eq(b)
# passes if a == b
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to be > b">

{% highlight ruby linenos %}
expect(a).to be > b
# passes if a > b
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to be <= b">

{% highlight ruby linenos %}
expect(a).to be <= b
# passes if a <= b
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to be < b">

{% highlight ruby linenos %}
expect(a).to be < b
# passes if a < b
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).not_to be_zero">

{% highlight ruby linenos %}
expect(a).not_to be_zero
# calls a.zero?
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(a).to be_multiple_of(b)">

{% highlight ruby linenos %}
expect(a).to be_multiple_of(b)
# calls x.multiple_of?(b)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(area_of_circle).to be_within(0.1).of(28.3)">

{% highlight ruby linenos %}
expect(area_of_circle).to be_within(0.1).of(28.3)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(1..10).to cover(5)">

{% highlight ruby linenos %}
expect(1..10).to cover(5)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(1..10).to cover(4, 6)">

{% highlight ruby linenos %}
expect(1..10).to cover(4, 6)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(1..10).not_to cover(11)">

{% highlight ruby linenos %}
expect(1..10).not_to cover(11)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

_______________________________________________________________
