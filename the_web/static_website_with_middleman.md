# Static Website with Middleman

> Middleman "is a static site generator using all the shortcuts and tools in modern web development"
>
> <cite>[Middleman site](https://middlemanapp.com/)</cite>

Static websites are widely used because they are fast, easy to setup. They are served to the user exactly as stored and there is no transaction to a database. It's pretty much HTML, CSS and Javascript if needed.

You might be wondering now, why go through the trouble of using a tool like Middleman to build a static website?

Building a static site with multiple pages can lead to having lots of repeated code across. Updating them during development will quickly become a nightmare. Middleman will allow you to structure your project in a more modular manner using things like layouts, partials, etc. Giving you a DRY and more manageable project.

Middleman uses the Ruby programming language. But don't worry if you're still new to Ruby as you'll likely not write too much of it while build your site.

Now let's install middleman and build our first site.

### Installation

If you don't have Ruby installed yet, please refer to our setup instructions for [Linux](../terminal/linux.md) or [Mac OS X](../terminal/mac_osx.md)

Once you're done, head to your terminal and run the following command:

```shell
$ gem install middleman
```

This will install Middleman, its dependencies and command line tools for using Middleman.

### Create a new project - `middleman init`

Let's build a middleman skeleton project. From your terminal, navigate to the folder where you would like to create your project and run the following command:

```shell
$ middleman init my_fancy_site
```

This will create a folder named `my_fancy_site` in the current directory.

### Serving the Application - `middleman server`

Middleman ships with a local server to test your application during development. 

```shell
$ cd my_fancy_site
$ middleman server
```

This will start up the server and you should now be able to access the site at [http://localhost:4567/](http://localhost:4567/)


### Directory Structure

```shell
my_fancy_site/
+-- .gitignore
+-- Gemfile
+-- Gemfile.lock
+-- config.rb
+-- source
    +-- images
    ¦   +-- background.png
    ¦   +-- middleman.png
    +-- index.html.erb
    +-- javascripts
    ¦   +-- all.js
    +-- layouts
    ¦   +-- layout.erb
    +-- stylesheets
        +-- all.css
        +-- normalize.css
```

***Add Description of main folders here***

### Build and Deploy

### Frontmatter

### Templating language

### Helper Methods

### Layouts

### Partials