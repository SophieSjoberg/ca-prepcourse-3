# Classes

A class is the blueprint from which individual objects are created. A Ruby class always starts with the keyword `class` followed by the name of the class. The name should always be in initial capitals. For instance a `Account` class can be created as:

```ruby
class Account
end 
``` 
This is the bare minimum code you need to write to create a class. Try to define and insatiate the `Account` class in `irb`:

```bash
$ irb
2.2.0 :001 > class Account
2.2.0 :002?>   end
 => nil 
2.2.0 :003 > Account.new
 => #<Account:0x007fc55110ad60> 
```
The `Account.new` command creates an **instance** of the `Account` class. At this point there is not much we can do with this object, but still, it has come to life ;-)

### The `initialize` method
Let's say that we want the `Account` class to have some attributes, like the account holders name and account balance (Yeah, I forgot to mention that, let's assume that we are creating a bank account and not a user account in a system). 

Every Ruby class invokes a **constructor** method called `initialize`. The `initialize` method is useful when you want to initialize some class variables at the time of object creation. This method may take a list of parameters and like any other ruby method it would be preceded by the `def` keyword:

```ruby
class Account  
  def initialize(holder, balance)
    @holder = holder
    @balance = balance
  end
end
```
Try this code in `irb` by defining the class and trying to instantiate an new  `Account` object. What happens if you do this?

```bash
2.2.0 :001 > a = Account.new
```
You have not passed in any values to the `initialize` method and you are getting an error, right? It might look something like this:
```bash
ArgumentError: wrong number of arguments (0 for 2)
	from (irb):87:in `initialize'
	from (irb):96:in `new'
	from (irb):96
	from /Users/thomas/.rvm/rubies/ruby-2.2.0/bin/irb:11:in `<main>'
```

Try instead to pass in a name and a balance as arguments:
```bash
2.2.0 :098 > a = Account.new 'Thomas', 100
 => #<Account:0x007fb35421ab60 @holder="Thomas", @balance=100> 
```
Looks like that works better, right?

However, we are still not quite where we want to be. In many cases you want to be not only be able to access the values (that we can do at this point), but also modify them. For that we need some **setter methods**. We can define the ourselves, but Ruby offers us a better way. How about this code:

```ruby
class Account  
  attr_accessor :holder, :balance
  def initialize(holder, balance)
    self.holder, self.balance = holder, balance
  end
end
```

### Exercise
Have a look at the latest code defining the `Account` class. 
* What methods are available to you now?
* What does the `self` keyword mean?
* Can you modify the attributes of an account? 
* Is it good to always be able to do that? 
* What changes would you introduce?

Think about this by putting this class and objects you can create with it in a real life context. For instance, if this was a real life bank account, would it be good to be useful to be able to modify the account holders name after the account has been opened? Why? Why not?




## Extending Ruby classes

As a programmer, you are free to modify, change or extend any class. Even those that are built in to the Ruby language. For instance, let's say that you want a method that check if a given number id even or odd. That might come in handy, right? We know that a number without decimals is of a `Fixnum` class. Let's extend that class with a custom method:

```ruby
class Fixnum
  def is_even?
    self % 2 == 0
  end
end
```
We just created a `is_even?` method that can be called on any number. We are using a `Modulus` operator (`%`) that divides the number we are calling this method on with 2 and returns `true` if the reminder equals to `0`. If not, the method returns `false`.

Try to define this method in `irb` and call it on some numbers.
```bash
$ irb
2.2.0 :001 > class Fixnum
2.2.0 :002?>     def is_even?
2.2.0 :003?>         self % 2 == 0
2.2.0 :004?>     end
2.2.0 :005?> end
 => :is_even? 
2.2.0 :006 > 4.is_even?
 => true 
2.2.0 :007 > 5.is_even?
 => false 
```

If you do this and want to use the extension or modification in a program that you've created, then I suggest you create a separate file and store it in the `lib` folder, something like: `/lib/core_ext.rb`. Make sure to `require` that file in your main program file or controller or what have you. 

