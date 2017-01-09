# jQuery

jQuery is a Javascript library that is used to manipulate objects in the DOM (Document-Object-Model, also known as a the browser). This is a brief overview with a bit of play, but if it feels good, go ahead and dive in deeper.

## Some fun with jQuery
First, open up a Chrome browser. Don't have Chrome? That's ok - [you can go download it](https://www.google.com/chrome/browser/desktop/). Then install [Chrome Developer Tools](https://developers.google.com/web/tools/chrome-devtools/).

Now open up a page, pretty much any page. Try craftacademy.se for this example. Right-click anywhere on the page and select "Inspect" from the drop-down menu. A side window should pop up in the browser. Make sure you can see the Console.

Type this in the console:
```
$('.hero-splash').text('what up')
```
Cool, right?
Now try this one:
```
$('.hero-splash').hide()
```
You can bring it back with `.show()`

Now click on the 'Har du frågor?' box at the bottom, just to see what it does. Close it. Now, in the console, type:
```
$('#doorbell-button').click()
```
We can use jQuery to do all the things that a user can do manually.

Ok, that was an extremely brief introduction to jQuery. You can definitely dive in and learn more here.

## Extra Resources for jQuery
We're nearing the end of the prep course and you'll shortly start the real bootcamp! See if you can't put in a little time working with jQuery to wrap up your pre-course studies.

- [Codecademy's JQuery class](https://www.codecademy.com/learn/jquery) (~ 3 hours)
- [W3 School's JQuery Introduction](http://www.w3schools.com/jquery/jquery_intro.asp)
- And if you find yourself with lots of time and energy to spare, [30 Days to Learn JQuery](https://code.tutsplus.com/courses/30-days-to-learn-jquery)