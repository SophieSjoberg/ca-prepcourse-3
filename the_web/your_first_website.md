## Your first website

It's all about the web. During this course we'll be building a lot of applications. For starters we'll be writing small pieces of software that will be run on our own computers. Relatively soon we'll move on to more advanced applications built to be deployed and run on a web server.

The idea is that you get to master the different techniques before we introduce another layer of complexity. Before you know it, we'll be deploying fully featured, dynamic web apps on virtual servers. But not today. Today we'll learn how to crawl so that we can run a marathon in the future.

#### Learning experience
In this exercise we will start scratching the surface of HTML and CSS and build a small static web page - and deploy it on the internet for everybody to see. We'll also get a chance to practice some git skills - an essential part of your skill-set as a developer. 

### Walkthrough

All of us are using GitHub for storage of our code in the cloud and for collaboration.

One of the many features of GitHub offers is the possibility to create web sites for users and projects. We'll take advantage of that feature to publish a personal web site.

Head over to GitHub and create a new repository named `username.github.io`, where username is your username on GitHub. In my case it would be: `tochman.github.io`. **Please note: If the first part of the repository name doesn't exactly match your username, it won't work, so make sure to get it right.**

![Creating a new repository](../images/github_io_step1.png)

In your terminal, go to the folder where you want to store your project, and clone the new repository. Remember we'll need the URL of our repository to make this step work.

```html
$ git clone repo_url
$ cd repo_name
$ touch index.html
$ atom index.html
```
This copies the repository from GitHub onto your local computer, switches into that folder, creates an `index.html` and opens it. Now add some text. For example:
```html
<h1>Hello World</h1>
<p>I'm Thomas and I attend the Craft Academy Bootcamp.</p>
```
You can view your website by opening up `index` in your browser. Right-click on `index` in your finder and select `Open With >` and pick your browser of choice.

Use Git to commit, and push your changes to GitHub:
```shell
$ git add .
$ git commit -m "initial commit"
$ git push origin master
```

** Open your browser and go to `http://<your_github_username>.github.io`. **

You have just deployed your first web site. 

![Your first website](../images/github_io_step2.png)

### The look and feel of your site

Okay, so now you have published your first website. It is **NOT** an application - it is just a static site. Since we are using GitHub's very generous mechanism for publishing personal or project websites, we are limited in what we can do in terms of functionality. We won't be able to create a fully featured application on this platform. But we can, however, take the opportunity and practice some basic HTML and CSS skills, as well as version control.

Making sure you are still in your `github.io` folder, type
```shell
$ atom .
```
This will open up the entire folder inside of Atom.

Now you can double-click the `index.html` and open it for editing. We want to make the following changes to that file:

```html
# index.html

<!DOCTYPE HTML>

<html>

<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
  <title>My First Website</title>
</head>

<body>
  <h1>Hello World</h1>
  <p>I'm Thomas, and I attend the Craft Academy Bootcamp<p>
</body>

</html>
```

What we've done now is we added the basic HTML5 document structure. 

We can do more, of course. How about adding some basic CSS? Add this line inside the `<head>` tags on your `index` page:

```html
# index.html

<link rel="stylesheet" href="style.css">
```
This will link a new file we will create: `style.css`. Either use Atom's GUI commands or the terminal to create a file in the root folder called `style.css`. Add this code:
```css
h1 {
  color: #0066ff
}
```

Open your `index` on your browser. Your "Hello World" should now be blue. Cool, right?

CSS is the way we add "styling" to our web pages. It's important to learn and perhaps more important to understand as you work with folks who do the bulk of the design work for our web apps. 






