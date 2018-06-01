## Files

A Ruby program can, of course, be stored in a file. By convention, Ruby source files have the `.rb` file extension. In most editors, like Atom, your code will automatically be color coded. That is very convenient.

Let's say you write a short Ruby script and save it in a file called `hello_world.rb`. 

```ruby
# hello_world.rb

names = ['Thomas', 'Kalle', 'Anders']
names.each do |name|
  puts "Hello #{name}"
end

```

What do you think this code will do? (Hint: `puts` will print onto the terminal). When you have a guess, run the file in your terminal:

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
```

### Exercise

Let's return to your `my_group.rb` program. I have a small challenge for you. I want you to iterate through the array of hashes you created in the previous exercise, and display information for each person on the screen. Something like this:
```
Thomas is a 44 years old man
Anna is a 38 years old woman
# and so on...
```
You are free to Google, stack overflow or whatever you need to do to find out how to do this, but I want you to know that the answer is right above in this chapter. ;-) **Happy coding!**










