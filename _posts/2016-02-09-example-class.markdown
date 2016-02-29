---
layout: post
title:  "Example Class"
date:   2016-01-29 08:40:52 -0800
categories: jekyll update
---

Ruby is an object oriented language. Sometimes this is referred to as "OOP" (object oriented programming). This means that everything in your code is a type of object. The originators of OOP wanted the language to mirror the physical world. The real world is full of objects that have characteristics and behavior. Ruby is full of objects that have characteristics and behaviors.

Here is an example of the code your Ruby environment uses to create a new object. It is a set of instructions that define the characteristics and behaviors of all 'Chairs' in your currently running Ruby environment.

{% highlight ruby linenos %}

class Chair

  attr_reader :color # Automagically creates a getter method
  attr_accessor :height # Automagically creates a getter and setter method

# This is an example of a class variable
  @@count = 0

# This is the method that executes when creating a new instance of the Chair class
  def initialize(color, height)
    @color = color
    @height = height
    @@count += 1
  end

# This is an example of a class method
  def self.count
    puts "There are currently #{@@count} chairs."
  end

# This is an example of an instance method
  def spin(direction, strength)
    puts "The chair is spinning #{direction}."
    sleep strength
    puts "The chair has stopped spinning."
  end

end

{% endhighlight %}

Here is some more code that you execute in the Ruby environment. This code is telling Ruby to execute the code from above, in order to create several 'Chairs' and interact with these 'Chairs'.

{% highlight ruby linenos %}

Chair.count

# This is an example of creating a new instance of the Chair class.
chair1 = Chair.new("black", "high")
chair2 = Chair.new("black", "high")
chair3 = Chair.new("black", "high")
chair4 = Chair.new("black", "high")
chair5 = Chair.new("black", "high")

Chair.count

# This is an example of using an instance method.
chair.spin("counter-clockwise", 1)

# These are examples of accessing instance variables through a getter methods.
p "The height of the chair is #{chair.height}."
p "The color of the chair is #{chair.color}."

# This is an example of modifying an instance variable with a setter method.
chair.height = "low"
p "The height of the chair is #{chair.height}."

{% endhighlight %}

Here are some explanations of several parts of the first section of code.

* **Class Variable**: A class variable is a variable that is shared by all instances of a class.
* **Instance Variable**:  An instance variable is a variable that is references with the same code for each instance of a class, but with returns a value that is unique to each instance of the class.
* **Local Variable**: A local variable is a variable that is only accessible within the method in which it is created.
* **Class Method**: A class method is a method that you call by referencing the class and the class method.
* **Instance Method**: An instance method is a method that you call by referencing an instance of a class and the method
