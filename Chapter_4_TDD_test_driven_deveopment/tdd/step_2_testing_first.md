## Testing first

We will start by writing our specs (tests) for the game. First we need to create a test file. All our specs will live in the `spec` folder. Go ahead and create a file named `fizz_buzz_spec.rb`

```shell
$ touch spec/fizz_buzz_spec.rb
```

Open it up in your editor and add the following code:

```ruby
require './lib/fizz_buzz'

describe 'fizz_buzz' do
  
end
```
The line at the top means that the tests file will look for and test the source file in the `lib` folder, called `fizz_buzz.rb`. At this moment it will not find that file (we have not created it yet). Our test will return an error.

The following lines are a describe block where we will put our tests. We will return to them shortly. 

First, I want you to return to your terminal and run `rspec` again. I want you to actually see the test fail and get accustomed to the error messages you will be seeing.

```shell
rspec
/Users/thomas/Projects/fizz_buzz/spec/fizz_buzz_spec.rb:1:in `require': cannot load such file -- ./lib/fizz_buzz (LoadError)
	from /Users/thomas/Projects/fizz_buzz/spec/fizz_buzz_spec.rb:1:in `<top (required)>'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/configuration.rb:1361:in `load'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/configuration.rb:1361:in `block in load_spec_files'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/configuration.rb:1359:in `each'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/configuration.rb:1359:in `load_spec_files'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/runner.rb:102:in `setup'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/runner.rb:88:in `run'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/runner.rb:73:in `run'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/lib/rspec/core/runner.rb:41:in `invoke'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/gems/rspec-core-3.4.1/exe/rspec:4:in `<top (required)>'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/bin/rspec:23:in `load'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/bin/rspec:23:in `<main>'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/bin/ruby_executable_hooks:15:in `eval'
	from /Users/thomas/.rvm/gems/ruby-2.2.0/bin/ruby_executable_hooks:15:in `<main>'
```

**Yes, that IS a lot!** But the most important lines are the two on the top:
```text
/Users/thomas/Projects/fizz_buzz/spec/fizz_buzz_spec.rb:1:in `require': cannot load such file -- ./lib/fizz_buzz (LoadError)
```

Quite often, RSpec is returning a lot of text when we get an error and it can get quite intimidating. One tip is to always look at the top of the output. That is where the important message is.

RSpec is telling us that there is no file in the `lib` folder called `fizz_buzz.rb`. There isn't. Let's create one.

```shell
$ mkdir lib
$ touch lib/fizz_buzz.rb
```

So, let's pause for a moment. It is important that we agree on three things at this point. 
1. Your **tests/specs** are placed in the `spec` folder
2. Your **implementation (or production) files** are placed in the `lib` folder
3. Your **settings** (like `Gemfile`, etc.) are placed in the main project folder

Alright?

Moving on... Time to write some tests. 

Let's make some decisions. Let's say that we want a main method in our program that can take a number and return 'fizz', 'buzz', fizzbuzz' or the number if no conditions are met. That is our objective, right?

Add the following `it` block to your test file (make sure to place it **inside** the `describe` block)

```ruby
# spec/fizz_buzz_spec.rb

it 'returns 1 if number is 1' do
    expect(fizz_buzz(1)).to eq 1 
end
```

Go back to your terminal and run RSpec. You will get an error:

```shell
$ rspec

fizz_buzz
  returns 1 if number is 1 (FAILED - 1)

Failures:

  1) fizz_buzz returns 1 if number is 1
     Failure/Error: expect(fizz_buzz(1)).to eq 1
     
     NoMethodError:
       undefined method `fizz_buzz' for #<RSpec::ExampleGroups::FizzBuzz:0x007f832ccde158>
     # ./spec/fizz_buzz_spec.rb:5:in `block (2 levels) in <top (required)>'

Finished in 0.00046 seconds (files took 0.1437 seconds to load)
1 example, 1 failure

Failed examples:

rspec ./spec/fizz_buzz_spec.rb:4 # fizz_buzz returns '1' if number = 1


```
Again, a lot of text, but if you read the message carefully, you'll see that we are getting a `NoMethodError`. This means our test can't find a method called `fizz_buzz`. Again, we haven't created it yet - so that's what we would expect.

Even though we know our test will fail, we still want to run it and see our expected error. This way we will be confident that we are ok to go on. If we get the wrong error, something else is broken.

Let's write the minimum amount of code to make this test pass:

```ruby
# lib/fizz_buzz.rb

def fizz_buzz(number)
  number
end
```

This very simple method takes a number as an argument and simply returns it. In Ruby, methods return their last line. They _output_ the last thing before the `end`. Here, our method will `return` our `number`.

It makes the test pass - try by running the `rspec` command in your terminal again.

```shell
$ rspec

fizz_buzz
  returns '1' if number = 1

Finished in 0.00215 seconds (files took 0.14163 seconds to load)
1 example, 0 failures
```

So we asked the program to return '1' if we pass in '1'. All in accordance with the game rules, right? We've written the minimum amount of code needed to make that happen. At this stage we are all good.

But we are far from done, right? One of the objectives is to return the word `fizz` if the number we pass in is divisible by 3. Let's write a test for that.

```ruby
# spec/fizz_buzz_spec.rb

it "returns 'fizz' if number is divisible by 3" do
  expect(fizz_buzz(3)).to eq 'fizz'
end
```

If you run `rspec` again, you'll get an error (of course)

```shell
$ rspec

fizz_buzz
  returns 1 if number is 1
  returns 'fizz' if number is divisible by 3 (FAILED - 1)

Failures:

  1) fizz_buzz returns 'fizz' if number is divisible by 3
     Failure/Error: expect(fizz_buzz(3)).to eq 'fizz'
     
       expected: "fizz"
            got: 3
     
       (compared using ==)
     # ./spec/fizz_buzz_spec.rb:9:in `block (2 levels) in <top (required)>'

Finished in 0.0952 seconds (files took 0.13986 seconds to load)
2 examples, 1 failure

Failed examples:

rspec ./spec/fizz_buzz_spec.rb:8 # fizz_buzz returns 'fizz' if number is divisible by 3
```

Let's say that we want our implementation to have a some methods that checks if a number is divisible by 3, 5 and 15.

Let's make use of flow control. We want our program to go down the 'fizz' path only if `number` is evenly divisible by 3.
```ruby
# lib/fizz_buzz.rb

def fizz_buzz(number)
  if number % 3 == 0
    'fizz'
  end
end
```
If modulus (%) is still unclear, try [this YouTube video](https://www.youtube.com/watch?v=b5cb_nfDyyM) explaining it visually. Modulus is an important, though confusing, operator to understand.

Remember that we can always open up irb and play around. You can copy the method above and see what different numbers will give you `fizz`. You'll notice that only numbers that evenly divide by 3 will return 'fizz' - 3, 6, 9, etc. You'll have to write `fizz_buzz(3)` or `fizz_buzz(9)` to see `fizz`. Try writing just `fizz_buzz`. Why are you getting that error?

Now, this code will make our second test to pass. Try it.

```shell
$ rspec

fizz_buzz
  returns 1 if number is 1
  returns 'fizz' if number is divisible by 3

Finished in 0.00148 seconds (files took 0.13955 seconds to load)
2 examples, 0 failures
```
### Review and reflect
Okay, so at this point we need to take a step back and review and reflect on what we have done. There are a series of questions you need to ask yourself:
1. How does flow control work?
2. Can you come up with another example of flow control that you could have used here?
3. How does the `%` operator work?
4. What is the difference between `=` and `==`?

Some of the answers are available to you in this documentation, some are not. Feel free so search on Google, StackOverflow, etc. for answers.  






