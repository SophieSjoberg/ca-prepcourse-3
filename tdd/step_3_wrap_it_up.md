## Wrap it up

Now it is up to you to write the rest of your tests and implement the code you need to make them pass.

You have to make sure that each and every scenario that can arise is tested, meaning that all numbers has to be checked and returned the right value according to the game rules.

At the very end of your development process you want to make a run through an series of numbers and get a similar response as we showed you in the first step of this exercise.

```irb
$ irb
2.2.0 :001 > load './lib/fizz_buzz.rb'
 => true 
2.2.0 :002 > output = []
 => []
2.2.0 :003 > 100.times {|n| output << fizz_buzz(n)}
```
