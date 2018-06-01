## Installing Qt and compiling capybara webkit

### macOS

We will use homebrew in this process. Have it installed in your system

* Install Qt via homebrew. First update the formulas, then try installing the built binary with:

```
$ brew update
$ brew install qt@5.5
```

The Homebrew formula for qt@5.5 is keg only which means binaries like `qmake`  will not be symlinked into your `/usr/local/bin` directory and therefore will not be available for `capybara-webkit`

Then add to your shell configuration file:

Then add to your shell configuration file:

```bash
$ echo 'export PATH="$(brew --prefix qt@5.5)/bin:$PATH"' >> ~/.bashrc
```

* install the gem

```
$ gem install capybara-webkit
```

If you're running a version of macOS other than Sierra, El Capitan or Yosemite, visit the [capybara-webkit wiki](https://github.com/thoughtbot/capybara-webkit/wiki/Installing-Qt-and-compiling-capybara-webkit) and follow instructions for your version.

### Linux \(Ubuntu and other debian based distros\)

Required before doing the installation

* Ruby installed in the system

* Update your system to get the latest packages

```
$ sudo apt-get update -y
```

1. Install necessary build tools for compilation of packages

```
$ sudo apt-get install build-essential -y
```

1. The capybara-webkit gem needs the Qt toolchain \(including qmake and the webkit library and header files\). You want version 4.8 or later but not higher than qt5.5.1

```
$ sudo apt-get install libqtwebkit-dev -y
```

1. install the gem

```
$ gem install capybara-webkit
```



