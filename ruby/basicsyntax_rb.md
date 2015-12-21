## Basic syntax

### Files
A Ruby program can, of course, be stored in a file. By convention, Ruby source files have the `.rb` file extension. In most editors, like Atom, your code will automatically be color coded. That is very convenient.

Let's say you write a short Ruby script and save it in a file called `hello_world.rb`. 

```ruby
# hello_world.rb

names = ['Thomas', 'Kalle', 'Anders']
names.each do |name|
  puts "Hello #{name}"
end

```

(Think about what this code does and consider the simplicity of Ruby.) If you want to execute it from your terminal you can do:

```shell
$ ruby hello_world.rb
Hello Thomas
Hello Kalle
Hello Anders
```

If you are in `irb` you can load this file with the `load` or `require` command:

```bash
$ irb
2.2.0 :001 > load 'hello_world.rb'
Hello Thomas
Hello Kalle
Hello Anders
 => true 
2.2.0 :002 > require './hello_world.rb'
Hello Thomas
Hello Kalle
Hello Anders
 => true 
```

Please note the different way you point to the file when you use the `load` command and when you use the `require` command. Why is that?

### Exercise

Let's return to your `my_group.rb` program. I have a small challenge for you. I want you to iterate through the array of hashes you created in the previous exercise, and display information for each person on the screen. Something like this:
```
Thomas is a 44 years old man
Anna is a 38 years old woman
# and so on...
```
You are free to Google, stack overflow or whatever you need to do to find out how to do this, but I want you to know that the answer is right above in this chapter. ;-) **Happy coding!**










