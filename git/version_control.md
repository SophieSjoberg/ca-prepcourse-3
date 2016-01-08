## Version Control
### What is Version Control? 
A system that records changes to files over time. 
Git allows for:
* Reverting files or entire project to a previous state 
* Comparing changes over time 
* View of who modified the source last 
* Collaboration between multiple developers
* Clients don't checkout single files, they clone the entire repository
* Many types version control systems available - we focus on git

### Why is it called “Git”?
**British mild profanity [slang](http://www.urbandictionary.com/define.php?term=git
) for silly, incompetent, stupid, annoying, senile elderly or childish person.** 

Linus Torvalds, the creator of Git, is told to have said: <br/>*“I'm an egotistical bastard, and I name all my projects after myself. First Linux, now git.”* 

Alternatively: **“Global Information Tracker” **

### Why GitHub?
Most famous online place to store git repositories. GitHub is more than just a programmer's tool. If you want to collaborate on anything, you should definitly sign up for an account. 

#### Features
* Can be your team’s central project repository 
* Largest code host on the planet
* Powerful tools for  
    * Group permissions
    * Integrated issue tracking
    * Collaborative code review
    * Wikis

### Setting up git

```shell
$ git config --global user.name "Your Name"
    # Sets the default name for git to use when you commit
$ git config --global user.email you@yourdomain.example.com
    # Sets the default email for git to use when you commit

```

#### Staging area
Git has a concept of a ‘staging area’. First stage all of the changes you want in a single “commit”.

Add a single file to the staging area:
```shell
$ git add [filename] 
```
Or add all changed ﬁles to the staging area:
```shell
$ git add .
```
#### Commits
Create a commit. 
```shell
$ git commit -a -m “commit message”
```
#### Remotes
Add a remote repository

```shell
$ git remote -v 
$ git remote add origin [HTTPS or GIT]
```
####Push
Push to your remote repository
```shell
$ git push origin master 
    #or
$ git push origin my_branch:master
```

Note that several commits can be pushed to git repository at once

#### Branching
```shell
$ git branch 
$ git branch [new branch name]
$ git checkout [new branch name]
$ git checkout -b [new branch name]
$ git checkout remote/branch
$ git checkout -b branch
```

### Exercise

Create a new project and access the project folder

```shell
$ cd my_project
```
Initialize git
```shell
$ git init
Initialized empty Git repository in .git/
```

Create a file called `hello.rb` inside the `my_project` folder.
```shell
$ touch hello.rb
```

Add the following code to that file

```ruby
puts 'Hello World'
```
Run the code (just for the sake of it - it has no bearing on the exercise).
```shell
$ ruby hello.rb
```
Check the status
```shell
$ git status
```

Add the `hello.rb` file to git to track it, and create a commit
```shell
$ git add hello.rb
$ git commit -m “my commit”
```
Check your commit history
```shell
$ git log
```

### Labs - Git Immersion
There is a very good resource available on-line that allows you to practice your git skills called Git Immersion. Head over to their website and work your way through all labs. Make sure to follow the instructions carefully and push up your work to your GitHub account.

Start [Git Immersion Labs](http://gitimmersion.com/lab_01.html)

**Note that we have covered some of the steps in Git Immersion, but please go over everything again. Git is a very important skill to master if you want to succeed with the Craft Academy course.**
### Resources

* Git Pro online book - http://git-scm.com/book/en/v2
* Basic Video tutorials - http://git-scm.com/videos
* Git reference_ http://git-scm.com/docs










