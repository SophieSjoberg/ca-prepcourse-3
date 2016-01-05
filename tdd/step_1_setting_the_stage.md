## Step 1 - Setting the stage

We will be using Test Driven Development - this means, in general terms, that we will start with writing a test for the application, watch it fail, write the implementation and watch the test pass.

We will be using Ruby to write out implementation code. For our tests, we will be using a testing framework called RSpec.

In your terminal, create a project folder called `fizz_buzz` and `cd` into it:

```bash
$ mkdir fizz_buzz
$ cd fizz_buzz
```

Create a file called `Gemfile` and add `rspec` as a dependency: 

```ruby
# Gemfile
source "https://rubygems.org"

gem "rspec"
```
Remember to run `bundle install` in your terminal. When you do, you should see similar output:
```shell
$ bundle install

Fetching gem metadata from https://rubygems.org/.........
Fetching version metadata from https://rubygems.org/..
Resolving dependencies...
Using diff-lcs 1.2.5
Using rspec-support 3.4.1
Using rspec-core 3.4.1
Using rspec-expectations 3.4.0
Using rspec-mocks 3.4.0
Using rspec 3.4.0
Using bundler 1.9.1
Bundle complete! 1 Gemfile dependency, 7 gems now installed.
Use `bundle show [gemname]` to see where a bundled gem is installed.
```

Again, in your terminal, write the following command to initialize `RSpec`: 

```shell
$ rspec --init
create   .rspec
create   spec/spec_helper.rb
```

Now, open the `.rspec` file (it is a hidden file) and change it's content to display the tests results in a verbose format.

```text
# .rspec

--format documentation
--color
--require spec_helper
```
Now, if you go back to your terminal and run the `rspec` command, you should see something like this:

```shell
$ rspec
No examples found.

Finished in 0.00028 seconds (files took 0.40297 seconds to load)
0 examples, 0 failures

```

This is good, you have set up RSpec and are ready to write your first test.








