### Testing JavaScript with Mocha and Chai

Mocha is a feature-rich JavaScript test framework running on Node.js and in the browser, making asynchronous testing simple and fun. 
Chai is a BDD / TDD assertion library for node and the browser that can be paired with any javascript testing framework.
--

Start by creating a folder for your project:

`$ mkdir BMI` 

And go into that folder:

`$ cd BMI` 


We are going to install Mocha andd Chai locally in the project

`$ npm install mocha chai --save-dev`

We don't want to push up our node_modules folder to github so lets create a .gitignore file:

`$ touch .gitignore` 

Add this inside the .gitignore file:

`node_modules`

We are going to initialize npm to create a package.json file:

`$ npm init`

Open you text editor

`code .`


package.json was created and should look like this: 

``` javascript
{
  "name": "bmi",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "directories": {
    "test": "test"
  },
  "dependencies": {},
  "devDependencies": {
    "mocha": "^5.1.1"
  },
  "scripts": {
    "test": "mocha"
  },
  "author": "",
  "license": "ISC"
}
```



--


##### Run Mocha in your browser



`$ touch specrunner.html`

Add the following snippet in your `specrunner.html`

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Mocha Tests</title>
    <link href="https://unpkg.com/mocha@4.0.1/mocha.css" rel="stylesheet" />
</head>
<body>
<div id="mocha"></div>
<script src="https://unpkg.com/chai@4.1.2/chai.js"></script>
<script src="https://unpkg.com/mocha@4.0.1/mocha.js"></script>

<script>mocha.setup('bdd')</script>
<script>mocha.setup('bdd')</script>

<script src="src/sum.js"></script>
<script src="test/sum.test.js"></script>

<script>
    mocha.checkLeaks();
    mocha.run();
</script>
</body>
</html>
```


`$ open specrunner.html`
