# Classes

The concept of a "class" is abstract. You can think of classes as _blueprints_ for creating objects. Say you want to make a house. You'll need some instructions for how to make a house - a blueprint. A house should have a roof, and some windows, and needs to be on a piece of land, it needs to have paint, etc. You can use that blueprint to make any number of houses, right? And the blueprint itself is not a house. It's just a plan about how to make a house.

Classes work the same way. We'll create a class and give it "properties" or "attributes". Any objects created from that class will have the same attributes, but different values. For instance, our blueprint might say that a house needs to have "paint". When we create a real house from that blueprint, we'll define that paint color.

A Ruby class always starts with the keyword `class` followed by the name of the class. The name should always be in initial capitals. For instance a `House` class can be created as:

```ruby
class House
end 
``` 
This is the bare minimum code you need to write to create a class. Try to define and instantiate the `House` class in `irb`:

```bash
$ irb
2.2.0 :001 > class House
2.2.0 :002?>   end
 => nil
 ````
Now let's create a account object and use it:
```ruby
2.2.0 :003 > a = House.new
 => #<House:0x007fc55110ad60> 
```
The `a = House.new` command creates an **instance** of the `House` class and stores it in a local variable called `a`. At this point there is not much we can do with this object, but still, it has come to life ;-)

Now `a` stores a "real" `House`, whereas the `House` class is just instructions for creating one.

### The `initialize` method
Let's say that we want the `House` class to have some attributes, like color or number of windows. 

Every Ruby class invokes a **constructor** method called `initialize`. This is stuff that happens to the instance of the class (the object) right when it is created.

```ruby
class House  
  def initialize(color, windows)
    @color = color
    @windows = windows
  end
end
```
Try this code in `irb` by defining the class and trying to instantiate an new  `Account` object. What happens if you do this? (You'll have to load the file again to get the new changes.)

```bash
2.2.0 :001 > a = House.new
```
You have not passed in any values to the `initialize` method and you are getting an error, right? It might look something like this:
```bash
ArgumentError: wrong number of arguments (0 for 2)
	from (irb):87:in `initialize'
	from (irb):96:in `new'
	from (irb):96
	from /Users/thomas/.rvm/rubies/ruby-2.2.0/bin/irb:11:in `<main>'
```

Try instead to pass in a name and a balance as "arguments":
```bash
2.2.0 :098 > a = House.new 'blue', 10
 => #<House:0x007fb35421ab60 @color="blue", @windows=10> 
```
Looks like that works better, right?

However, we are still not quite where we want to be. In many cases you want to be not only be able to access the values (that we can do at this point), but also modify them. For that we need some **setter methods**. We could define those methods ourselves, but Ruby offers us a better way. How about this code:

```ruby
class House  
  attr_accessor :color, :windows
  def initialize(color, windows)
    @color = color
    @windows = windows
  end
end
```
That `attr_accessor` is a helper method that allows us to `read` and `write` to the _attributes_ listed after it. So now we can "set" the attributes `color` and `windows`. Try running your code again in irb. Change the color of the house. Give it some more windows.

### Exercise
Have a look at the latest code defining the `House` class. 
* What methods are available to you now?
* What does it mean when there is a `@` in front of a variable?
* Can you modify the attributes of an account? 
* Is it good to always be able to do that? 
* What changes would you introduce?

Think about this by putting this class and objects you can create with it in a real life context. For instance, it's good that we can change the paint color - we do that to houses in real life, yes? But what about windows? Should those be so easy to change?

