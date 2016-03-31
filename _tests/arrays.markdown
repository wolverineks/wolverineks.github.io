---
layout: post
title:  "Array Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="ARRAYS"></a>

### ARRAYS

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([]).to be_empty">

{% highlight ruby linenos %}
expect([]).to be_empty
# calls [].empty?
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 3, 5]).to all( be_odd )">

{% highlight ruby linenos %}
expect([1, 3, 5]).to all( be_odd )
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 3, 5]).to all( be_even )">

{% highlight ruby linenos %}
expect([1, 3, 5]).to all( be_even )
# fails
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 3, 5]).to all( be_an(Integer) )">

{% highlight ruby linenos %}
expect([1, 3, 5]).to all( be_an(Integer) )
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 3, 5]).to all( be < 10 )">

{% highlight ruby linenos %}
expect([1, 3, 5]).to all( be < 10 )
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 3, 5]).to all( be_odd.and be < 10 )">

{% highlight ruby linenos %}
expect([1, 3, 5]).to all( be_odd.and be < 10 )
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 4, 21]).to all( be_odd.or be < 10 )">

{% highlight ruby linenos %}
expect([1, 4, 21]).to all( be_odd.or be < 10 )
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2, 3]).to contain_exactly(2, 3, 1)">

{% highlight ruby linenos %}
expect([1, 2, 3]).to contain_exactly(2, 3, 1)
# pass
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([:a, :c, :b]).to contain_exactly(:a, :c )">

{% highlight ruby linenos %}
expect([:a, :c, :b]).to contain_exactly(:a, :c )
# fail
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2, 3]).to    match_array [2, 3, 1]">

{% highlight ruby linenos %}
expect([1, 2, 3]).to match_array [2, 3, 1]
# pass
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([:a, :c, :b]).to match_array [:a, :c]">

{% highlight ruby linenos %}
expect([:a, :c, :b]).to match_array [:a, :c]
# fail
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([0, 1, 2]).to end_with 1, 2">

{% highlight ruby linenos %}
expect([0, 1, 2]).to end_with 1, 2
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([0,1,2]).to start_with(0, 1)">

{% highlight ruby linenos %}
expect([0,1,2]).to start_with(0, 1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2]).to include(1)">

{% highlight ruby linenos %}
expect([1, 2]).to include(1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2]).to include(1, 2)">

{% highlight ruby linenos %}
expect([1, 2]).to include(1, 2)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2]).to include(a_kind_of(Integer))">

{% highlight ruby linenos %}
expect([1, 2]).to include(a_kind_of(Integer))
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2]).to include(be_odd.and be < 10 )">

{% highlight ruby linenos %}
expect([1, 2]).to include(be_odd.and be < 10 )
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2]).to include(be_odd)">

{% highlight ruby linenos %}
expect([1, 2]).to include(be_odd)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect([1, 2]).not_to include(17)">

{% highlight ruby linenos %}
expect([1, 2]).not_to include(17)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(array).not_to have_odd_values">

{% highlight ruby linenos %}
expect(array).not_to have_odd_values
# calls array.has_odd_values?
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->
_______________________________________________________________
