# Methods

A method is a group of actions. You've already seen one called `initialize`. That is a method that creates an object from a class. We can put unlimited actions inside of the `initialize` method. Let's look at some other examples.

Let's use a new example, something that _does_ things (as opposed to a house, which doesn't do much.) This time we'll create a file called `dog.rb`. Create a `Dog` class and an `initialize` method like in the last exercise. You should be able to instantiate new `Dog` objects when you load the file in irb. What attributes should a dog have? Give your dog class some.

Now, let's give our dog class some methods. Right now, we should have something like this:

```ruby
class Dog
  attr_accessor :breed
  
  def initialize(breed)
    @breed = breed
  end
end
```
