---
layout: post
title:  "RSpec Tests"
date:   2016-03-13 08:40:52 -0800
categories: jekyll update rspec tdd
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/1.5.8/clipboard.min.js"></script>
<script>
var clipboard = new Clipboard('.test');
clipboard.on('success', function(e) {
    console.log(e);
});
clipboard.on('error', function(e) {
    console.log(e);
});
</script>

### Click on any test to copy to the clipboard

<form action="#ARRAYS" style="display: inline;">
    <input type="submit" value="ARRAYS">
</form>

<form action="#HASHES" style="display: inline;">
    <input type="submit" value="HASHES">
</form>

<form action="#STRINGS" style="display: inline;">
    <input type="submit" value="STRINGS">
</form>

<form action="#INTEGERS" style="display: inline;">
    <input type="submit" value="INTEGERS">
</form>

<form action="#TRUE/FALSE" style="display: inline;">
    <input type="submit" value="TRUE/FALSE">
</form>

<form action="#COUNTER" style="display: inline;">
    <input type="submit" value="COUNTER">
</form>

<form action="#ERRORS" style="display: inline;">
    <input type="submit" value="ERRORS">
</form>

<form action="#YIELD" style="display: inline;">
    <input type="submit" value="YIELD">
</form>

<form action="#TERMINAL" style="display: inline;">
    <input type="submit" value="TERMINAL">
</form>

<!-- <a href="#ARRAYS">ARRAYS</a>
<a href="#HASHES">HASHES</a>
<a href="#STRINGS">STRINGS</a>
<a href="#INTEGERS">INTEGERS</a>
<a href="#TRUE/FALSE">TRUE/FALSE</a>
<a href="#COUNTER">COUNTER</a>
<a href="#ERRORS">ERRORS</a>
<a href="#YIELD">YIELD</a>
<a href="#TERMINAL OUTPUT">TERMINAL OUTPUT</a> -->

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

_______________________________________________________________

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
