# Flow Control

Control structures are bits of code that determine which part of a code should run next. You can think of our code as coming to a crossroads - which road to choose? Our computer will choose the road that is `true` and not go down the road that is `false`.

Consider this code:

```ruby
if 2 + 2 == 4
  puts "Correct!"
else
  puts "Uh oh, something very wrong."
end
```

Try it in irb. Hopefully the laws of math are working there! Our computers look for the code that comes after `if` to see whether or not it is true. If it is, it will do the code inside of that block. Otherwise, it will do the code inside of the `else` block. This line:

```ruby
if 2 + 2 == 4
```

is called a "conditional". If two plus two is four, we run the code below the `if`. If not, we run other code.

In Ruby and many other languages, we do not need to supply an else. We can also do:

```ruby
if 2 + 2 == 4
  puts "Correct!"
end
```

Try some control flow of your own. You can use the mathematical operators on the next page to create different true/false statements.

Ruby has some additional helpful methods. Consider:

```ruby
unless 2 + 2 == 3
  puts "Always!"
end
```

`unless` is the flip-side of `if`. Now we will run the code inside the block _unless_ the conditional is true. Two plus two will never be three, so the code in the block will always run.

There are many flow control structures in Ruby. Take this opportunity to do a little research. You also need to know about `while` and `case`. Google them with a search like `while loop in Ruby`. Learning how to find the information you need online is a critical developer skill. Make sure you play around with these flow control structures in irb to get a feel for how they work.

**One note of caution! You may find yourself with a neverending **`while`** loop that goes on and on and on. You'll need to quit irb to make a stop. Just type ctrl-C and your program will quit.\***

