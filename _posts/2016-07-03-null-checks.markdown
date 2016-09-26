---
layout: post
title:  "Removing Null Checks"
date:   2016-07-03 18:40:52 -0800
categories: jekyll null
---

So, I found this little pattern today while reading [Michael Feather's blog](http://michaelfeathers.typepad.com/michael_feathers_blog/).

```
data_source.person(id) do |person|
  person.phone_number = phone_number
  data_source.update_person person
end
```

He describes the 'person' method as yielding to the block only if it doesn't return nil.

He doesn't specify exactly what the 'person' method looks like, but I imagine it could look something like this:
```
class DataSource
  attr_accessor :people

  def initialize(people)
    @people = people
  end

  def person(index)
    yield @people[index] if @people[index]
  end

end
...
```

From here you can then execute something like the following code without blowing up your app:

```
2.3.1 :001 > d = DataSource.new([{name: "Alice"}])
=> #<DataSource:0x00000000ba5bd0 @people=[{:name=>"Alice"}]>
2.3.1 :002 > d.person(0) { |person| person }
=> {name: "Alice"}
2.3.1 :003 > d.person(0) { |person| person[:name] = "Bob"}
=> #<DataSource:0x00000000ba5bd0 @people=[{:name=>"Bob"}]>
2.3.1 :004 > d.person(0) { |person| person.name }
=> {name: "Bob"}
2.3.1 :001 > d.person(99) { |person| person.name = "Non-existing person"}
=> nil
```
