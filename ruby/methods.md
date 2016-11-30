# Methods

A method is a group of actions. You've already seen one called `initialize`. That is a method that creates an object from a class. We can put unlimited actions inside of the `initialize` method. Let's look at some other examples.

Let's use a new example, something that _does_ things (as opposed to a house, which doesn't do much.) This time we'll create a file called `dog.rb`. Create a `Dog` class and an `initialize` method like in the last exercise. You should be able to instantiate new `Dog` objects when you load the file in irb. What attributes should a dog have? Give your dog class some.

Now, let's give our dog class some methods. Right now, we should have something like this:

```ruby
class Dog
  attr_accessor :breed, name
  
  def initialize(breed, name)
    @breed = breed
    @name = name
  end
  
  def wag_tail
    puts "Tail wagging"
end
end
```
Now to give our dogs something to do. `[...]` means there is extra code we are not showing.
```ruby
class Dog
[...]

def wag_tail
  puts "Tail wagging"
end
```
Reload your `dog.rb` file. You should now be able to make your dog wag its tail:
```shell
2.3.0 :023 > dog = Dog.new('shitzu', 'freddie')
 => #<Dog:0x007f953982a070 @breed="shitzu", @name="freddie"> 
2.3.0 :024 > dog.wag_tail
Tail wagging
 => nil 
2.3.0 :025 > 
```
`dog.wag_tail` is the way we _call a method on an object_. We are making the `dog` do `wag_tail`. Try `wag_tail` without the `dog.`. What happens? Any guesses why?

Give your dog some more actions. Try making some methods that take arguments.
