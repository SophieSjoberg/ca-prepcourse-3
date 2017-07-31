## The basics

### IRB

Interactive Ruby Shell is an interactive programming environment that comes with Ruby. IRB is useful to experiment with or to explore Ruby. You start it by typing `irb` at a shell or command prompt, and begin entering ruby statements and expressions:

```bash
$ irb
2.2.2 :001 > # type your ruby command
```

### Variables

Variables are labels for bits of data. We use them to store information so we can easily reference it. Variables can hold almost anything.

In irb write:

```bash
2.2.2 :001 > name = "Thomas"
 => "Thomas"
2.2.2 :002 > occupation = "Coach"
 => "Coach"
2.2.2 :003 > age = 44
 => 44
```

`name`, `occupation` and `age` are variables and store the values we have assigned to them. You can try to use them by calling them in the irb-console:

```bash
2.2.2 :004 > name
"Thomas"
 => nil
```

### Datatypes

The following example just gives a quick look at the most common datatypes in Ruby

#### Strings

Strings are one of the most important data types in computer languages. A string is a sequence of characters. In Ruby a string, as everything else, is an instance of a class - `String`. \(We'll talk about classes in a minute. For now, think of it as an object "type"\).

Try the following in `irb`

```bash
2.2.2 :005 > "Thomas".class
 => String
```

And since we have "Thomas" stored in a variable called `name` we can also do:

```bash
2.2.2 :006 > name.class
 => String
```

Our computers will interpret anything inside quotes as a string. Variables look like strings, but they are never inside quotes. Try this out in your terminal. Type `'Thomas'` and then `Thomas`. You will get very different results.

#### Numbers

Generally speaking there are two main types of numbers **floats** and **integers** \(or `Fixnum`\). Floats represent real numbers while integers are a subset of the real numbers. While floats can be decimal numbers, an integer is written without a fraction or a decimal component. Let's have a look at our `age` variable:

```bash
2.2.2 :007 > age.class
 => Fixnum
```

But if we store a decimal number in another variable, let's say `weight`, we get another class.

```bash
2.2.2 :008 > weight = 85.5
 => 85.5 
2.2.2 :008 > weight.class
 => Float
```

Again, there are many methods we need to cover in relation to numbers and we will do that during the course.

#### Booleans

Booleans are `true` or `false`. Try this:

```ruby
2.3.0 :007 > true_thing = true
 => true
```

Notice that we don't use quotes here around true. It's not a variable and it's not a string, it's a boolean.

#### Arrays

Arrays are lists of objects. You create an array by creating a new object of the `Array` class:

```bash
2.2.2 :014 > collection = Array.new
 => []
```

or

```ruby
2.3.0 :020 > collection = []
 => []
```

However, in Ruby you can skip that step if you want. Let's say you want to store some names in the array. You want it to contain the names of you and your two classmates. "Thomas", "Kalle" and "Anders". In Ruby, you can both create an array AND assign objects to it at the same time:

```bash
2.2.2 :016 > collection = ["Thomas", "Kalle", "Anders"]
 => ["Thomas", "Kalle", "Anders"] 
2.2.2 :017 > collection.class
 => Array
```

Arrays have special properties and methods available to them. Try:

```ruby
collection.length
collection.reverse
collection.sort!
```

What do each of these methods do?

The objects stored in an array each have a number - an index. The first position in an array has index number 0, the next 1, etc. We use the following command to return items at index 0:

```bash
2.2.2 :018 > collection[0]
 => "Thomas"
```

Ruby is a very programmer friendly language and we get a lot of methods for free that make our lives easier. Try calling `last` and `first` on the `collection` variable:

```bash
2.2.2 :019 > collection.last
 => "Anders" 
2.2.2 :020 > collection.first
 => "Thomas"
```

Arrays can store any type of data, whether it be a string, an integer, a Boolean, objects, even additional arrays. One thing that we want to have a look at is how to add and remove objects from an array.

##### Pop and Push

Let's say we want to add another name to our `collection` variable. We can use the `push` method to do that:

```bash
2.2.2 :021 > collection.push "Anna"
 => ["Thomas", "Kalle", "Anders", "Anna"]
```

The `push` method has an alias called the shovel operator. Try This:

```bash
2.2.2 :021 > collection << "Raoul"
 => ["Thomas", "Kalle", "Anders", "Anna", "Raoul"]
```

It does the same thing.

If we want to remove an object \(last added object\) from that array, we can use the `pop` method:

```bash
2.2.2 :054 > collection.pop 
 => "Raoul"
```

And now if we check what is stored in the `collection` variable, "Raoul" is no longer there:

```bash
2.2.2 :055 > collection
 => ["Thomas", "Kalle", "Anders", "Anna"]
```

Let's restore the array and try another method. We will delete an object from the array by its index. Try this:

```bash
2.2.2 :064 > collection = ["Thomas", "Kalle", "Anders"]
 => ["Thomas", "Kalle", "Anders"] 
2.2.2 :065 > collection.delete_at(1)
 => "Kalle"
```

And now "Kalle" is gone.

The last method we will cover is the `shift` method. It deletes the object that is stored in the first position of the array:

```bash
2.2.2 :069 > collection = ["Thomas", "Kalle", "Anders"]
 => ["Thomas", "Kalle", "Anders"] 
2.2.2 :070 > collection.shift
 => "Thomas"
```

Now "Thomas" is gone.

#### Hashes

Hashes are collections of key-value pairs. Here is an example:

```bash
2.2.2 :021 > person = {name: "Thomas", age: 44, weight: 85.5}
 => {:name=>"Thomas", :age=>44, :weight=>85.5}
```

`:name` is the "key" and `"Thomas"` is the "value".

Now if we would like to access this `person`'s name, we could do this:

```bash
2.2.2 :022 > person[:name]
 => "Thomas"
```

And, consequently, we can access the `age` and `weight` in similar way:

```bash
2.2.2 :023 > person[:age]
 => 44 
2.2.2 :024 > person[:weight]
 => 85.5
```

Remember that the `hash[:key]` notation is saying "look in `hash` for `:key` and tell me what information is stored there."

#### Symbols

Symbols are a simple form of strings and are often used to represent or identify other objects. They are also used in Hashes as key names. Symbols have a colon before an identifier, like `:name`. For now, try this:

```bash
2.2.2 :071 > :name.class
 => Symbol
```

### Exercise

Here's a simple exercise for you to try what we have covered in this section:

1. Create an array and store it in a variable called `my_group`
2. Create three hashes describing an individual and name them `person_1`, `person_2`and `person_3`. The hash should contain the following keys:
   * `name`
   * `gender`
   * `age`
3. Add all persons to your `my_group` array.
4. Do everything in IRB but also save it in a `.rb` file called `my_group.rb`. We'll be returning to this example later on. 



