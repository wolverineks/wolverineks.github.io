---
layout: post
title:  "Cheat-Sheet"
date:   2016-02-18 08:40:52 -0800
categories: jekyll update
---

<html>

<head>
  <meta charset="utf-8">
  <link rel="stylesheet" href="https://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />
  <script src="https://code.jquery.com/jquery-1.11.1.min.js"></script>
  <script src="https://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>
</head>

<div class="ruby search">
  <h3>Ruby</h3>

  <form>
    <input type="text" data-type="search" id="filterable-input-ruby">
  </form>

  <form class="full" data-role="controlgroup" data-filter="true" data-input="#filterable-input-ruby" data-filter-reveal="true">

    <label>
      Assign an array literal
      {% highlight ruby linenos %}
        arr = [1,2,3,4,5,6]
        #=> [1,2,3,4,5,6]
      {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Return several elements from the front of an array
      {% highlight ruby linenos %}
        arr.take(3)
        #=> [1,2,3]
      {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Return several elements after the specified amount is dropped from the front of the array
      {% highlight ruby linenos %}
          arr.drop(3)
          #=> [4,5,6]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Add an element to the front of an array
      {% highlight ruby linenos %}
          arr.unshift(0)
          #=> [0, 1, 2, 3, 4, 5, 6]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Insert the second parameter at the index of the first parameter
      {% highlight ruby linenos %}
          arr.insert(3, 'apple')
          #=> [0, 1, 2, 'apple', 3, 4, 5, 6]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Insert all but the first parameter at the index of the first parameter
      {% highlight ruby linenos %}
          arr.insert(3, 'orange', 'pear', 'grapefruit')
          #=> [0, 1, 2, "orange", "pear", "grapefruit", "apple", 3, 4, 5, 6]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Remove and return the first element from the front of the array
      {% highlight ruby linenos %}
          arr.shift
          #=> 1
          arr
          #=> [2, 3, 4, 5]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Delete and return the element at the index of the parameter
      {% highlight ruby linenos %}
          arr = [1, 2, 2, 3]
          #=> [1, 2, 2, 3]
          arr.delete(2)
          #=> 2
          arr
          #=> [1,3]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Return an array of elements common to both arrays(no duplicates)
      {% highlight ruby linenos %}
          [ 1, 1, 3, 5 ] & [ 1, 2, 3 ]
          #=> [ 1, 3 ]
          [ 'a', 'b', 'b', 'z' ] & [ 'a', 'b', 'c' ]
          #=> [ 'a', 'b' ]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Return an array of elements common to both arrays(no duplicates)
      {% highlight ruby linenos %}
          [ 1, 1, 3, 5 ] & [ 1, 2, 3 ]
          #=> [ 1, 3 ]
          [ 'a', 'b', 'b', 'z' ] & [ 'a', 'b', 'c' ]
          #=> [ 'a', 'b' ]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Compares 2 arrays. Returns an integer (-1, 0, or +1) if this array is less than, equal to, or greater than other_ary
      {% highlight ruby linenos %}
          [ "a", "a", "c" ]    <=> [ "a", "b", "c" ]   #=> -1
          [ 1, 2, 3, 4, 5, 6 ] <=> [ 1, 2 ]            #=> +1
          [ 1, 2 ]             <=> [ 1, :two ]         #=> nil
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Compares 2 arrays. Two arrays are equal if they contain the same number of elements and if each element is equal to (according to Object#==) the corresponding element in other_ary
      {% highlight ruby linenos %}
          [ "a", "c" ]    == [ "a", "c", 7 ]     #=> false
          [ "a", "c", 7 ] == [ "a", "c", 7 ]     #=> true
          [ "a", "c", 7 ] == [ "a", "d", "f" ]   #=> false
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Invokes the given block once for each element of self. Creates a new array containing the values returned by the block.
      {% highlight ruby linenos %}
          a = [ "a", "b", "c", "d" ]
          a.collect { |x| x + "!" }         #=> ["a!", "b!", "c!", "d!"]
          a.map.with_index { |x, i| x * i } #=> ["", "b", "cc", "ddd"]
          a                                 #=> ["a", "b", "c", "d"]
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Converts a pathname to an absolute pathname
      {% highlight ruby linenos %}
          File.absolute_path("~oracle/bin")       #=> "<relative_path>/~oracle/bin
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Deletes the named files, returning the number of names passed as arguments
      {% highlight ruby linenos %}
          File.delete(file_name, ...) #=> integer
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Return true if the named file exists.
      {% highlight ruby linenos %}
          File.exist?(file_name) #=> true or false
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Join multiple strings into a filepath
      {% highlight ruby linenos %}
          File.join("usr", "mail", "gumby")   #=> "usr/mail/gumby"
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Renames the given file to the new name
      {% highlight ruby linenos %}
          File.rename("afile", "afile.bak")   #=> 0
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Splits the given string into a directory and a file component and returns them in a two-element array
      {% highlight ruby linenos %}
          File.split("/home/gumby/.profile")   #=> ["/home/gumby", ".profile"]
      {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns the size of file in bytes
        {% highlight ruby linenos %}
          File.new("testfile").size   #=> 66
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns true if hash is subset of other
      {% highlight ruby linenos %}
        h1 = {a:1, b:2}
        h2 = {a:1, b:2, c:3}
        h1 < h2    #=> true
        h2 < h1    #=> false
        h1 < h1    #=> false
      {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns true if hash is subset of other or equals to other
      {% highlight ruby linenos %}
          h1 = {a:1, b:2}
          h2 = {a:1, b:2, c:3}
          h1 <= h2   #=> true
          h2 <= h1   #=> false
          h1 <= h1   #=> true
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Two hashes are equal if they each contain the same number of keys and if each key-value pair is equal to (according to Object#==) the corresponding elements in the other hash
      {% highlight ruby linenos %}
          h1 = { "a" => 1, "c" => 2 }
          h2 = { 7 => 35, "c" => 2, "a" => 1 }
          h3 = { "a" => 1, "c" => 2, 7 => 35 }
          h4 = { "a" => 1, "d" => 2, "f" => 35 }
          h1 == h2   #=> false
          h2 == h3   #=> true
          h3 == h4   #=> false
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns true if other is subset of hash or equals to hash
      {% highlight ruby linenos %}
          h1 = {a:1, b:2}
          h2 = {a:1, b:2, c:3}
          h1 >= h2   #=> false
          h2 >= h1   #=> true
          h1 >= h1   #=> true
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns the default value, the value that would be returned by hsh if key did not exist in hsh
      {% highlight ruby linenos %}
          h = {}
          h.default = 5
          h[0]   #=> 5
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Deletes the key-value pair and returns the value from hsh whose key is equal to key
      {% highlight ruby linenos %}
          h = { "a" => 100, "b" => 200 }
          h.delete("a")    #=> 100
          h   #=> { "b" => 200 }
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns a copy of str with all characters in the intersection of its arguments deleted
      {% highlight ruby linenos %}
          "hello".delete "l","lo"        #=> "heo"
          "hello".delete "lo"            #=> "he"
          "hello".delete "aeiou", "^e"   #=> "hell"
          "hello".delete "ej-m"          #=> "ho"
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns a copy of str with the all occurrences of pattern substituted for the second argument
      {% highlight ruby linenos %}
          "hello".gsub(/[aeiou]/, '*')                  #=> "h*ll*"
          "hello".gsub(/([aeiou])/, '<\1>')             #=> "h<e>ll<o>"
          "hello".gsub(/./) {|s| s.ord.to_s + ' '}      #=> "104 101 108 108 111 "
          "hello".gsub(/(?<foo>[aeiou])/, '{\k<foo>}')  #=> "h{e}ll{o}"
          'hello'.gsub(/[eo]/, 'e' => 3, 'o' => '*')    #=> "h3ll*"
        {% endhighlight %}
      <input type="checkbox">
    </label>

    <label>
      Returns the Symbol corresponding to str, creating the symbol if it did not previously exist
      {% highlight ruby linenos %}
          "Koala".intern         #=> :Koala
          s = 'cat'.to_sym       #=> :cat
          s == :cat              #=> true
          s = '@cat'.to_sym      #=> :@cat
          s == :@cat             #=> true
        {% endhighlight %}
      <input type="checkbox">
    </label>

  </form>

</div>
