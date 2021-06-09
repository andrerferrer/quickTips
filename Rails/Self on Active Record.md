`ActiveRecord::Base` placed all the column names inside `@attributes` instance variable (`Hash`) and create accessors instance methods for those column names.

For example:

`card_status` is a column in `cards` table, it will have accessor methods with the name `card_status` and `card_status=`

Since ruby local variable definition is dynamic, the line
```ruby
def after_find
  ....  
  card_status = false if self.is_used_up?
  ....
end
```
will mean we are defining and assigning to a local variable `card_status` rather than the instance method `card_status=`

[This article](https://thoughtbot.com/blog/to-self-or-not-to-self) provides more explanation on this.

[Source](https://stackoverflow.com/questions/1496380/why-do-activerecord-callbacks-require-instance-variables-or-instance-methods-to)

### Following up on that

If we had a `Restaurant` model like this:
```ruby
class Restaurant < ApplicationRecord
  def what_are_attributes
    p @attributes
    binding.pry
  end
end
```

We'd be able to check what `@attributes` actually is:
![image](https://user-images.githubusercontent.com/45776359/121343394-00c11d80-c8f9-11eb-9a55-caadad58a623.png)

```ruby
@attributes.class
# => ActiveModel::AttributeSet 
# https://www.rubydoc.info/gems/activemodel/ActiveModel/AttributeSet
```

So, when we do `Restaurant.new(attributes)`, it's actually running the initializer differently than we expect:
![image](https://user-images.githubusercontent.com/45776359/121343919-8f359f00-c8f9-11eb-845e-878de41737c0.png)

And that's why plain old ruby objects' (POROs) getters and setters won't work properly here.
https://www.rubydoc.info/gems/activemodel/ActiveModel/AttributeSet
