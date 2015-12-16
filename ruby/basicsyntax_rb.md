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

If you want to execute it from your terminal you can do:

```shell
$ ruby hello_world.rb
Hello Thomas
Hello Kalle
Hello Anders
```

If you are in `irb` you can load this file with the `load` command:

```bash
$ irb
2.2.0 :001 > load 'hello_world.rb'
Hello Thomas
Hello Kalle
Hello Anders
```










