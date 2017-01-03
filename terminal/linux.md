# Linux

In this section we will cover the steps required to setup your development environment on Ubuntu 16.04

If you haven't already, grab a copy of Ubuntu 16.04 LTS (Xenial Xerus) [here](http://www.ubuntu.com/download/desktop) and install it on your computer.

### Installing Ruby

First thing we want to do is make sure our system has the latest updates and security patches. We will also install some dependencies for Ruby.

```shell
$ sudo apt-get update && sudo apt-get upgrade -y
$ sudo apt-get install git-core curl zlib1g-dev build-essential \
libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 \
libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties \
libffi-dev libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
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
$ rvm install 2.3.1
$ rvm use 2.3.1 --default
$ ruby -v
```

Now we need to tell `Rubygems` to skip documentation while installing packages \(`gems`\) locally.

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

### Atom

At the beginning of the course \(week 1 - 6\) we'll be using a text editor to write code. There are many editors out there we can use. [Sublime](http://www.sublimetext.com/) is one, [TextMate](https://macromates.com/) is another, but our editor of choice for this course is [Atom](https://atom.io). It is brought to us by the good people of GitHub and comes with over 3000 extension packages - all open sourced.

_"Atom is a text editor that's modern, approachable, yet hackable to the core — a tool you can customize to do anything but also use productively without ever touching a config file."_ - [https://atom.io](https://atom.io)

![Atom landing page](/images/atom_io_landing_page.png)

Download and install Atom by following the instructions on their web site. Once you are done you can browse around for some packages you might find useful. Or you wait with that until you actually know what 'useful' is in the context of coding. If you want to find out more about how to install Atom packages head over to the excellent [documentation](https://atom.io/docs/v1.2.4/using-atom-atom-packages) site. Also, read through this blog post about some Atom extensions that might prove useful: [http://www.sitepoint.com/10-essential-atom-add-ons/](http://www.sitepoint.com/10-essential-atom-add-ons/)

For now, what you really want to do is to set Atom as the default editor fir Git (trust me, you are going to need it):

```shell
$ git config --global core.editor "atom --wait"
```

### **`zsh` and Pretzo **

### **`zsh`**

**[zsh](http://zsh.sourceforge.net)** is a shell designed for interactive use, although it is also a powerful scripting language. Many of the useful features of _[bash](https://www.gnu.org/software/bash/)_, **_ksh_**, and **_tcsh_** were incorporated into zsh; many original features were added.

**Steps to install `zsh`**

1. There are two main ways to install `zsh` :
 * with the package manager of your choice (_e.g._ `sudo apt-get install zsh`) or
 * from source, following instructions from the Zsh FAQ

2. Verify installation by running the following commad in your terminal: `zsh --version`.
 * The expected result: zsh 5.2 or more recent.

3. Make zsh your default shell by runnyng the following command in your terminal: `chsh -s $(which zsh)`

 > **Note:** This will not work if `zsh` is not in your authorized shells list (`/etc/shells`) or if you don't have permission to use `chsh`. If that's the case [you'll need to use a different procedure](https://www.google.com/search?q=zsh+default+without+chsh).

4. Log out and login back again to use your new default shell.

5. Go to your terminal to test if all worked by running: `echo $SHELL`.
 * The expected result should be: `/bin/zsh`


There are plenty of frameworks that have been created to help setup zsh configurations and themes, the following list shows some frameworks that have been created in alphabetical order.

* [alf](https://github.com/psyrendust/alf)
* [ant-zsh](https://github.com/anthraxx/ant-zsh)
* [antibody](https://github.com/caarlos0/antibody)
* [antigen-hs](https://github.com/Tarrasch/antigen-hs)
* [antigen](https://github.com/zsh-users/antigen)
* [dotzsh](https://github.com/dotphiles/dotzsh)
* [fresh](https://github.com/freshshell/fresh)
* [oh-my-zsh](http://ohmyz.sh/)
* [prezto](https://github.com/sorin-ionescu/prezto)
* [pumice](https://github.com/ryutamaki/pumice)
* [zeesh](https://github.com/zeekay/zeesh)
* [zgen](https://github.com/tarjoilija/zgen)
* [zilsh](https://github.com/zilsh/zilsh)
* [zim](https://github.com/Eriner/zim)
* [zoppo](https://github.com/zoppo/zoppo)
* [zplug](https://github.com/b4b4r07/zplug)
* [zplugin](https://github.com/psprint/zplugin)
* [ZPM](https://github.com/horosgrisa/ZPM)
* [ztanesh](https://github.com/miohtama/ztanesh)

### **Pretzo**

[Prezto](https://github.com/sorin-ionescu/prezto) is a configuration framework for `zsh`. It comes supplied with a variety of plugins and themes that can extend and customise your shell. There are other popular frameworks out there, one of which being [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh) which is has more plugins and themes available, but is known to be considerably slower.

**Steps to install Pretzo**

1. Open up a Terminal and launch zsh.
 ```shell
 $ zsh
 ```

2. Clone Pretzo git repository
 ```shell
 $ git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto"
 ```

3. Create a zsh configuration by copying the configuration files provided by the repo.
 ```shell
 setopt EXTENDED_GLOB
 for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
 ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
 done
 ```

 If you do the steps above, you will get the following files on your system:

 ```shell
 lrwxrwxrwx 1 user user 32 Jan 20 20:41 .zlogin -> /home/user/.zprezto/runcoms/zlogin
 lrwxrwxrwx 1 user user 33 Jan 20 20:41 .zlogout -> /home/user/.zprezto/runcoms/zlogout
 drwxrwxr-x 5 user user 4096 Jan 20 20:43 .zprezto
 lrwxrwxrwx 1 user user 35 Jan 20 20:42 .zpreztorc -> /home/user/.zprezto/runcoms/zpreztorc
 lrwxrwxrwx 1 user user 34 Jan 20 20:42 .zprofile -> /home/user/.zprezto/runcoms/zprofile
 lrwxrwxrwx 1 user user 25 Jan 20 20:33 .zsh -> /home/user/git/dotfiles/zsh
 lrwxrwxrwx 1 user user 32 Jan 20 20:42 .zshenv -> /home/user/.zprezto/runcoms/zshenv
 -rwx------ 1 user user 192662 Jan 20 20:48 .zsh_history
 ```

 If you do not need all the files, just clone the repository as described above and put the following line at the beginning of your `~/.zshrc`:

 ```shell
 # Source Prezto.
 if [[ -s "${ZDOTDIR:-$HOME}/.zprezto/init.zsh" ]]; then
 source "${ZDOTDIR:-$HOME}/.zprezto/init.zsh"
 fi
 ```

 > **Please note:** You will be asked if you wish to overwrite your existing files (like **.zshrc**) or skip them, if they already exists.

4. Configure your `~/.zpreztorc`

 This is the heart of prezto - here you enable modules and configure them.

 ```
 # Set the Prezto modules to load (browse modules).
 # The order matters.
 zstyle ':prezto:load' pmodule \
 'directory' \
 'utility' \
 'completion' \
 'git' \
 'prompt' \
 'syntax-highlighting' \
 'history-substring-search' \
 ```

5. Set Zsh as your default shell:
 ```shell
 $ chsh -s /bin/zsh
 ```

6. Open a new Zsh terminal window or tab.


**Common Commands**

1. To list all available prompt themes:
 ```shell
 $ prompt -l
 ```

2. To preview a theme:
 ```shell
 $ prompt -p <name-of-the-theme>
 ```

3. To change to another prompt theme
 ```shell
 $ prompt <name-of-the-theme>
 ```


> **Note:** If the above mentioned command does not work, follow the following steps to change the current prompt theme

Go to your terminal window and type the following command:

```shell
$ nano ~/.zpreztorc
```

Scroll through the file until you find a similar code to the following snippet then replace with the desired theme. The recommended theme: `giddie` or `steeef`

```
#
# Prompt
#
# Set the prompt theme to load.
# Setting it to 'random' loads a random theme.
# Auto set to 'off' on dumb terminals.
 zstyle ':prezto:module:prompt' theme 'steeef'
```

### Node JS With NVM

**Steps to Install NVM (Node Version Manager)**

1. Before we start let's update our system packages
 ```shell
 $ sudo apt-get update
 ```

 Even though the **build-essential** package should already be installed, we are still going to include it in our command for installation:Verify installation by running the following commad in your terminal: `zsh --version`.

 ```shell
 $ sudo apt-get install build-essential libssl-dev
 ```

2. Install NVM (Node Version Manager)

 Use the following curl command to start the installation script:

 ```shell
 $ curl https://raw.githubusercontent.com/creationix/nvm/v0.31.3/install.sh | bash
 ```

 At the time of publication, **NVM v0.31.3** was the most recent version available. You should check the [GitHub project page for the latest release of NVM](https://github.com/creationix/nvm/releases), and adjust the above command to include the newest version.

 **After running the above command, you may receive output similar to the following:**

 ```shell
 Close and reopen your terminal to start using nvm
 ```

3. Verify the Installation

 ```shell
 $ nvm --version
 ```

 Which in this case should return the version of nvm:

 ```shell
 0.31.3
 ```

 Another very useful command to get you started on node.js management is:

 ```shell
 $ nvm help
 ```


**Steps to install nodejs using NVM**

1. Check Available Node.js Versions

 ```shell
 $ nvm ls-remote
 ```

 I is also possible to install the latest **stable** or **unstable** versions, as shown in the next step.

2. Install a Node.js Version

 To download, compile, and install the latest version in the v6.3.x release of node.js:

 ```shell
 $ nvm install v6.3.1
 ```

 To display currently activated version:

 ```shell
 $ nvm current
 ```

 Which gives me the output:

 ```shell
 v6.3.1 #this is the version of node you currently using
 ```

 To show all the installed node versions via nvm use the following command:

 ```shell
 $ nvm ls
 ```

 If you want to change to another version of node use the following command:

 ```shell
 $ nvm use <another-version-of-node>
 ```

 The above command will return:

 ```shell
 Now using node
 ```

### Wrap

This should do for now. We will install the rest of packages we need as we progress through the course.