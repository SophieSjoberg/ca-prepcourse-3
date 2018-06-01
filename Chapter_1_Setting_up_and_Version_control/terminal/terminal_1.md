**We use our mouse to click images of icons and access files, programs, and folders on our devices. However, this is just one way for us to communicate with computers. The Terminal and the command line is a quick, powerful, text-based interface developers use to more effectively and efficiently communicate with computers to accomplish a wider set of tasks. Learning how to use it will allow you to discover all that your computer is capable of!**

There's are a ton of different terminal commands you can use. We'll only cover the basic ones that will make you pretty effective in the command line.


### Find your terminal

#### macOS

Use the Terminal program, located in your `Applications/Utilities` folder.

Another quick way to start it is by using `cmd + space` then search terminal.

![Search for terminal](/static/terminal_spotlight.png)

You'll want to change the color profile of the terminal to a dark background. It makes it easier to work in the long run. Open up Settings and change the profile to Pro.

![Terminal settings](/static/terminal_settings.png)

## Basic commands

We will only cover some very basic commands. Every one commands we list here can be used in a variety of ways - some very complicated. Don't worry about that but know that you can do almost anything you might imagine using the CLI \(command line interface\) and as a programmer, you should get used to it. We will be introducing more advanced commands as we progress, but for now, let's settle for these basic ones.

### Current Directory - `pwd`

`pwd` — stands for Present Working Directory and will show you a clear path to your location.  
![](/static/pwd_terminal.png)

### Create directories - `mkdir`

You create folders with `mkdir`. Simply type `mkdir Projects` and your new folder will be created.  
![](/static/mkdir_terminal.png)

### Change directories - `cd`

![](/static/cd_terminal.png)

### Create files - `touch`

The command for creating a file is called `touch`, so if we wanted to create a ruby source file called script, we would type `touch script.rb`

![](/static/touch_terminal.png)

### List files - `ls`

The `ls` command lists all files and sub folders in the current folder.  
![](/static/ls_terminal.png)

### Copy files - `cp`

The syntax for this command is straightforward: `cp` followed by the file name — `script.rb` followed by the path to the directory you want to save it in. In our case, the full command looks like this: `cp script.rb /Users/thomas/Projects/`, or, using a relative path command, `cp script.rb ../Projects`.   
![](/static/script.rb_terminal.png)

### Delete files \( `rm` \)

The command for deleting a file is `rm`. The command for this is simply `rm script.rb`.

![](../images/terminal_rm.png)

To be on the safe side, you can use the `-i` parameter to toggle interactive mode, where the Terminal will explicitly confirm your deletion command before executing it, in this case asking us if we want to `remove script.rb?` We can then answer `yes` or simply `y` to proceed.

To remove folders, you'll need to add a `-rf` tag. The full line is `rm -rf <folder name>`.

### Move files - `mv`

Instead of copying a file there are times when you want to move a file all together. You can do that with the `mv` command. First you put the file you want to move, then the place you want to move it to.  
![](/static/rm_terminal.png)

### Open folder in text editor

You can start your text editor from the command line as well:

![](/static/vs_code_terminal.png)

### Open folder in finder

Or, if you wish to navigate the folder in Finder, you can do it using the `open` command:  
![](/static/open_terminal.png)

![Your files in Finder](/static/projects_finder.png)

