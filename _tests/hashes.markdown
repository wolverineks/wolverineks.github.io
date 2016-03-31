---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="HASHES"></a>

### HASHES

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).to include(:a)
">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).to include(:a)

{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).to include(:a => 1)">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).to include(:a => 1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).to include(:a => 1)">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).to include(:a => 1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).to include(:b => 2, :a => 1)">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).to include(:b => 2, :a => 1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).not_to include(:c)">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).not_to include(:c)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).not_to include(:a => 2)">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).not_to include(:a => 2)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(:a => 1, :b => 2).not_to include(:c => 3)">

{% highlight ruby linenos %}
expect(:a => 1, :b => 2).not_to include(:c => 3)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(hash).to have_key(:foo)">

{% highlight ruby linenos %}
expect(hash).to have_key(:foo)
# calls hash.has_key?(:foo)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->
_______________________________________________________________
