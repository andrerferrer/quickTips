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