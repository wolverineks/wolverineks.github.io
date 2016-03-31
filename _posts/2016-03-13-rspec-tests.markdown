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


{% for test in site.tests %}
  {{ test.content }}
{% endfor %}
