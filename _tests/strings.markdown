---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="STRINGS"></a>

### STRINGS

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a').to be < 'b'">

{% highlight ruby linenos %}
expect('a').to be < 'b'
# passes if 'a' < 'b'
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(/foo/).to match('food')">

{% highlight ruby linenos %}
expect(/foo/).to match("food")
# passes
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(/foo/).to match('drinks')">

{% highlight ruby linenos %}
expect(/foo/).to match("drinks")
# fails
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a string').to include('a')">

{% highlight ruby linenos %}
expect("a string").to include("a")
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a string').to include('str')">

{% highlight ruby linenos %}
expect("a string").to include("str")
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a string').to include('str', 'g')">

{% highlight ruby linenos %}
expect("a string").to include("str", "g")
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a string').not_to include('foo')">

{% highlight ruby linenos %}
expect("a string").not_to include("foo")
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a string').to match(/str/)">

{% highlight ruby linenos %}
expect("a string").to match(/str/)
# passes
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('a string').to match(/foo/)">

{% highlight ruby linenos %}
expect("a string").to match(/foo/)
# fails
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('this string').to end_with 'string'">

{% highlight ruby linenos %}
expect("this string").to end_with "string"
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('this string').not_to end_with 'stringy'">

{% highlight ruby linenos %}
expect("this string").not_to end_with "stringy"
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('this string').to start_with 'this'">

{% highlight ruby linenos %}
expect("this string").to start_with "this"
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect('this string').not_to start_with 'that'">

{% highlight ruby linenos %}
expect("this string").not_to start_with "that"
{% endhighlight %}

</div>

_______________________________________________________________
