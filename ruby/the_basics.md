## The basics

### IRB
Interactive Ruby Shell is an interactive programming environment that comes with Ruby. IRB is useful to experiment with or to explore Ruby. You start it by typing `irb` at a shell or command prompt, and begin entering ruby statements and expressions:

```bash
$ irb
2.2.2 :001 > # type your ruby command
```
### Variables
Variables are the memory locations which hold any data to be used by any program. There are several types of variables but for now we will introduce and use a type that we refer to as **local variable**. More on that later.

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
2.2.2 :004 > puts name
Thomas
 => nil
```

### Datatypes
The following example just gives a quick look at the most common datatypes in Ruby
#### Strings
Strings are one of the most important data types in computer languages. A string is a sequence of characters. In Ruby a string, as everything else, is an instance of a class - `String`

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
There is many more things we can do with strings and we will be going over them in a separate section.

#### Numbers
Generally speaking there are two main types of numbers **floats** and **integers** (or `Fixnum`). Floats represent real numbers while integers are a subset of the real numbers. While floats can be decimal numbers, an integer is written without a fraction or a decimal component. Let's have a look at our `age` variable:

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

#### Symbols
Symbols are a simple form of strings and are often used to represent or identify other objects. They are also used in Hashes as key names. Symbols has an colon before an identifier, like `:name`. For now, try this:

```bash
2.2.2 :071 > :name.class
 => Symbol 
```

#### Arrays
Arrays are indexed collections of objects. You create an array by instantiating a new object of the `Array` class:
```bash
2.2.2 :014 > collection = Array.new
 => [] 
```
However, in Ruby you can skip that step if you want. Let's say you want to store some names in the array. You want it to contain the names of you and your two classmates. "Thomas", "Kalle" and "Anders". In Ruby, you can both create an array AND assign objects to it at the same time:

```bash
2.2.2 :016 > collection = ["Thomas", "Kalle", "Anders"]
 => ["Thomas", "Kalle", "Anders"] 
2.2.2 :017 > collection.class
 => Array 
```
You can access the value stored in an array by calling it's index. The first position in an array has index number 0.
```bash
2.2.2 :018 > collection[0]
 => "Thomas" 
```
Ruby is a very programmer friendly language and we get a lot of methods for free that makes out lives easier. Try calling `last` and `first` on the `collection` variable:

```bash
2.2.2 :019 > collection.last
 => "Anders" 
2.2.2 :020 > collection.first
 => "Thomas"
```
Arrays can store any type of data, whether it be a string, an integer, booleans, objects, even additional arrays. We'll be covering Arrays in a separate section. One thing that we want to have a look at is how to add and remove objects from an array.

##### Pop and Push
Let's say we want to add another name to our `collection` variable. We can use the `push` method to do that:

```bash
2.2.2 :021 > collection.push "Anna"
 => ["Thomas", "Kalle", "Anders", "Anna"] 
```
The `pop` method has an alias called the shovel operator. Try This:
```bash
2.2.2 :021 > collection << "Anna"
 => ["Thomas", "Kalle", "Anders", "Anna"] 
```
It does the same thing.

If we want to remove an object (last added object) from that array, we can use the `pop` method:
```bash
2.2.2 :054 > collection.pop 
 => "Anna" 
```
And now if we check what is stored in the `collection` variable, "Anna" is not longer there:
```bash
2.2.2 :055 > collection
 => ["Thomas", "Kalle", "Anders"] 
```
Let's restore the array and try another method. We will deleta an object from the array by it's index. Try this:
```
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
Now if we would like to access this `person`'s name, we could to this:
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

### Exercise

Here's a simple exercise for you to try what we have covered in this section:

1. Create an array and store it in a variable called `my_group`
2. Create three hashes describing an individual and name them `person_1`, `person_2`and `person_3`. The hash should contain the following keys:
    - `name`
    - `gender`
    - `age`
3. Add all persons to your `my_group` array.
4. Do everything in IRB but also save it in a `.rb` file called `my_group.rb`. We'll be returning to this example later on. 












