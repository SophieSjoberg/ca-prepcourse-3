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

Every Ruby class invokes a constructor method called `initialize`. The `initialize` method is useful when you want to initialize some class variables at the time of object creation. This method may take a list of parameters and like any other ruby method it would be preceded by the `def` keyword:

```ruby
class Account  
  def initialize(holder, balance)
    @holder = holder
    @balance = balance
  end
end
```








### Extending Ruby classes

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

