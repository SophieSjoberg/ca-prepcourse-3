## Wrap it up

Now it is up to you to write the rest of your tests and implement the code you need to make them pass.

You have to make sure that each and every scenario that can arise is tested, meaning that all numbers has to be checked and returned the right value according to the game rules.

Try out your program in `irb`. Remember that you have to `load` or `require` the source file.

```irb
$ irb
2.2.0 :001 > load './lib/fizz_buzz.rb'
 => true 
2.2.0 :002 > fizz_buzz(23)
 => 23 
2.2.0 :003 > fizz_buzz(3)
 => "fizz" 
2.2.0 :004 > fizz_buzz(6)
 => "fizz" 
2.2.0 :005 > fizz_buzz(10)
 => "buzz" 
2.2.0 :006 > fizz_buzz(45)
 => "fizz buzz" 
2.2.0 :007 > 
```

At the very end of your development process you want to make a run through an series of numbers and get a similar response as we showed you in the first step of this exercise.

In the example below, we'll create an `Array`and store it in a variable called `output`. As the next step we'll do 100 loops and add call `fizz_buzz` on each number from 1 to 100. Finally we'll display the content of the `output`-array.

```irb
$ irb
2.2.0 :001 > load './lib/fizz_buzz.rb'
 => true 
2.2.0 :002 > output = []
 => []
2.2.0 :003 > 100.times {|n| output << fizz_buzz(n+1)}
 => 100 
2.2.0 :004 > output
 => [1, 2, "fizz", 4, "buzz", "fizz", 7, 8, "fizz", "buzz", 11, "fizz", 13, 14, "fizz buzz", 16, 17, "fizz", 19, "buzz", "fizz", 22, 23, "fizz", "buzz", 26, "fizz", 28, 29, "fizz buzz", 31, 32, "fizz", 34, "buzz", "fizz", 37, 38, "fizz", "buzz", 41, "fizz", 43, 44, "fizz buzz", 46, 47, "fizz", 49, "buzz", "fizz", 52, 53, "fizz", "buzz", 56, "fizz", 58, 59, "fizz buzz", 61, 62, "fizz", 64, "buzz", "fizz", 67, 68, "fizz", "buzz", 71, "fizz", 73, 74, "fizz buzz", 76, 77, "fizz", 79, "buzz", "fizz", 82, 83, "fizz", "buzz", 86, "fizz", 88, 89, "fizz buzz", 91, 92, "fizz", 94, "buzz", "fizz", 97, 98, "fizz", "buzz"] 
```

### Refactoring

Since we are calling basically the same calculation in all `divisible_by_...?` methods, we can extract that to a method of its own. Something like:

```ruby
# lib/fizz_buzz.rb

def has_zero_reminder(number, divider)
  number % divider == 0
end
```

And once we have that method available, we can refactor our other methods to perform the calculation using the `has_zero_reminder` method, but still get the same results.

Our final spec file can look like this:

```ruby
# spec/fizz_buzz_spec.rb

require './lib/fizz_buzz'

describe 'fizz_buzz' do
  it "returns number if no conditions are met" do
    expect(fizz_buzz(1)).to eq 1 
  end

  it "returns 'fizz' if number is divisible by 3" do
    expect(fizz_buzz(6)).to eq 'fizz'
  end

  it "returns 'buzz' if number is divisible by 5" do
    expect(fizz_buzz(10)).to eq 'buzz'
  end

  it "returns 'fizz buzz' if number is divisible by 15" do
    expect(fizz_buzz(30)).to eq 'fizz buzz'
  end

end
```

And our final source file could look something like this:

```ruby
# lib/fizz_buzz.rb

def fizz_buzz(number)
  case
    when divisible_by_fifteen?(number) then 'fizz buzz'
    when divisible_by_five?(number) then 'buzz'
    when divisible_by_three?(number) then 'fizz'
    else number
  end
end

def divisible_by_three?(number)
  has_zero_reminder(number, 3)
end

def divisible_by_five?(number)
  has_zero_reminder(number, 5)
end

def divisible_by_fifteen?(number)
  has_zero_reminder(number, 15)
end

def has_zero_reminder(number, divider)
  number % divider == 0
end
```

### Follow up

Here are some links to documentation for the things mentioned in this chapter. It is always a good idea to glance over the docs to see what else exists in the API or DSL you are using.

* [RSpec: basic structure](https://relishapp.com/rspec/rspec-core/v/3-1/docs/example-groups/basic-structure-describe-it)
* [RSpec: expectations](https://relishapp.com/rspec/rspec-expectations/docs)
* [RSpec: built-in matchers](https://relishapp.com/rspec/rspec-expectations/v/3-1/docs/built-in-matchers)

