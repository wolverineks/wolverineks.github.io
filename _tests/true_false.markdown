---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="TRUE/FALSE"></a>

### TRUE/FALSE

<div class="test" data-clipboard-text="expect(obj).to be_truthy ">

{% highlight ruby linenos %}
expect(obj).to be_truthy
# passes if obj is truthy (not nil or false)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_falsey">

{% highlight ruby linenos %}
expect(obj).to be_falsey
# passes if obj is falsy (nil or false)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to be_nil">

{% highlight ruby linenos %}
expect(obj).to be_nil
# passes if obj is nil
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).not_to be_truthy">

{% highlight ruby linenos %}
expect(obj).not_to be_truthy
# passes if obj is not truthy (nil or false)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).not_to be_falsey">

{% highlight ruby linenos %}
expect(obj).not_to be_falsey
# passes if obj is not falsy (not nil or false)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).not_to be_nil">

{% highlight ruby linenos %}
expect(obj).not_to be_nil
# passes if obj is not nil
{% endhighlight %}

</div>


<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(obj).to exist">

{% highlight ruby linenos %}
expect(obj).to exist
# passes if obj.exist? or obj.exists?
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect(person).to have_attributes(:name => 'Jim', :username => 'jimbo')">

{% highlight ruby linenos %}
expect(person).to have_attributes(:name => "Jim", :username => 'jimbo')
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

_______________________________________________________________s
