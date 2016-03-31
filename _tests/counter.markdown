---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
collection: tests
---

<a name="COUNTER"></a>

### COUNTER

<div class="test" data-clipboard-text="expect { Counter.increment }.to change{Counter.count}.from(0).to(1)">

{% highlight ruby linenos %}
expect { Counter.increment }.to change{Counter.count}.from(0).to(1)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { Counter.increment }.to change{Counter.count}.by(2)">

{% highlight ruby linenos %}
expect { Counter.increment }.to change{Counter.count}.by(2)
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { Counter.increment }.not_to change{Counter.count}">

{% highlight ruby linenos %}
expect { Counter.increment }.not_to change{Counter.count}
{% endhighlight %}

</div>

<!-- ///////////////////////////////////////////////////// -->

<div class="test" data-clipboard-text="expect { Counter.increment }.to_not change{Counter.count}">

{% highlight ruby linenos %}
expect { Counter.increment }.to_not change{Counter.count}
{% endhighlight %}

</div>

_______________________________________________________________
