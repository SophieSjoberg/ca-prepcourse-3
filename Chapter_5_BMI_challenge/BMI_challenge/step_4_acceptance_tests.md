## Acceptance tests

Start by checking your Node version 

`$ node -v`

It should be version 10.2.0 or higher. 

`$ npm init`

```$ npm i e2e_training_wheels --save-dev```


Add following scripts to your ```package.json``` file

``` javascript
"scripts": {
    "test": "npm run features && npm run specs",
    "features": "superstatic src -p 8080 & mocha --timeout 100000 --recursive  --reporter=spec features ; PORT=8080 npm run stop-test-server ",
    "specs": "mocha --recursive  --reporter=spec spec",
    "server": "superstatic src -p 3000",
    "stop-test-server": "lsof -ti tcp:$PORT | xargs kill"
  }
```

The command `npm run` features will start a local webserver, launch Chrome and run your acceptance tests.

`npm run` specs will run your unit tests.

If you execute `npm test` in your terminal, both your acceptance tests and unit tests will be run.






**To stop the server in your terminal, just press the `ctrl` + `C` keys on your keyboard. To start it again, just type `rackup` and press enter.**

At this point, we are ready to add some tests to our `bmi_ui_spec.js`. 

What we want the test to do is to:
1. Fill in the fields for Weight and Height with values.
2. Click the `Calculate` button.
3. Assert that the right content is displayed on the page.

Modify your `bmi_ui_spec.js` with the following code

```ruby
# spec/bmi_ui_spec.js

describe('BMI_UI - index.html', function() {
    beforeEach(function() {
        jasmine.getFixtures().fixturesPath = '.';
        loadFixtures('index.html');
        $.holdReady(false);
        $('#weight').val('90');
        $('#height').val('186');
        $('#calculate').trigger('click');
    });
    
    it("displays BMI Value", function() {
        expect($('#display_value').text()).toBe('Your BMI is 26.01');
    });

    it("displays BMI Message", function() {
        expect($('#display_message').text()).toBe('and you are Overweight');
    });
});
```
Why do we need the `beforeEach` block? What are the last three lines of that block doing?

Now, run your tests by pointing your browser to the following URL.


```text
http://localhost:9292/SpecRunner.html
```
![Jasmine tests passing using the local web server](https://github.com/CraftAcademy/ca_course/raw/master/images/jasmine_sinatra_passing_tests.png)