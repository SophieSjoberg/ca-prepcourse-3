# Linux

In this section we will cover the steps required to setup your development environment on Ubuntu 14.04

If you haven't already, grab a copy of [Ubuntu 14.04 here](http://www.ubuntu.com/download/desktop) and install it on your computer.

### Installing Ruby

First thing we want to do is make sure our system has the latest updates and security patches. We will also install some dependencies for Ruby.

```shell
$ sudo apt-get update && sudo apt-get upgrade -y
$ sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
```

Next we are going to install [Ruby Version Manager (RVM)](http://rvm.io/). `RVM` will allow us to install and manage multiple versions of Ruby in our environment. We first have to download the [author's](http://rvm.io/authors/mpapis) public key to ensure we're downloading the correct packages.

```shell
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```

If for some reason the above command fails try the following:

```shell
$ command curl -sSL https://rvm.io/mpapis.asc | gpg --import -
```

We can now install `RVM` on our system.

```shell
$ \curl -sSL https://get.rvm.io | bash
$ source ~/.rvm/scripts/rvm
```

Now that we have `RVM` installed, let's install ruby.

```shell
$ rvm install 2.2.3
$ rvm use 2.2.3 --default
$ ruby -v
```

Now we need to tell `Rubygems` to skip documentation while installing packages (`gems`) locally.

```shell
$ echo 'gem: --no-ri --no-rdoc' > ~/.gemrc
```

Lastly we need to install [bundler](http://bundler.io/)

```shell
$ gem install bundler
```

### Git configuration

`Git` is a version control system we will be using throughout the course.

```shell
$ sudo add-apt-repository ppa:git-core/ppa
$ sudo apt-get update
$ sudo apt-get install git-core
```

Next, let's tell git who we are.

```shell
$ git config --global user.name "you name"
$ git config --global user.email "your@email.com"
```

### Wrap

This should do for now. We will install the rest of packages we need as we progress through the course. 