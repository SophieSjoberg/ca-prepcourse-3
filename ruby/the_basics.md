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

### Strings
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

### Numbers
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

### Arrays

### Hashes



