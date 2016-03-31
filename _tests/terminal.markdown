---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="TERMINAL"></a>

### TERMINAL

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { print('foo') }.to output.to_stdout">

{% highlight ruby linenos %}
expect { print('foo') }.to output.to_stdout
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { print('foo') }.to output('foo').to_stdout">

{% highlight ruby linenos %}
expect { print('foo') }.to output('foo').to_stdout
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { print('foo') }.to output(/foo/).to_stdout">

{% highlight ruby linenos %}
expect { print('foo') }.to output(/foo/).to_stdout
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { }.to_not output.to_stdout">

{% highlight ruby linenos %}
expect { }.to_not output.to_stdout
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { print('foo') }.to_not output('bar').to_stdout">

{% highlight ruby linenos %}
expect { print('foo') }.to_not output('bar').to_stdout
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { print('foo') }.to_not output(/bar/).t">

{% highlight ruby linenos %}
expect { print('foo') }.to_not output(/bar/).t
{% endhighlight %}

</div>

_______________________________________________________________
