---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="ERRORS"></a>

### ERRORS

<div class="test" data-clipboard-text="expect { raise StandardError }.to raise_error">

{% highlight ruby linenos %}
expect { raise StandardError }.to raise_error
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { raise 'oops' }.to raise_error">

{% highlight ruby linenos %}
expect { raise "oops" }.to raise_error
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { raise 'oops' }.to raise_error(RuntimeError)">

{% highlight ruby linenos %}
expect { raise "oops" }.to raise_error(RuntimeError)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { raise 'oops' }.to raise_error('oops')">

{% highlight ruby linenos %}
expect { raise "oops" }.to raise_error("oops")
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { raise 'oops' }.to raise_error(/op/)">

{% highlight ruby linenos %}
expect { raise "oops" }.to raise_error(/op/)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { raise 'oops' }.to raise_error(RuntimeError, 'oops')">

{% highlight ruby linenos %}
expect { raise "oops" }.to raise_error(RuntimeError, "oops")
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { raise 'oops' }.to raise_error(RuntimeError, /op/)">

{% highlight ruby linenos %}
expect { raise "oops" }.to raise_error(RuntimeError, /op/)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->
