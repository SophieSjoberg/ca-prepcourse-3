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
Most famous online place to store git repositories. GitHub is more than just a programmer's tool. It's useful for collaborating on almost anything. 

#### Features
* Can be your team’s central project repository 
* Largest code host on the planet
* Powerful tools for  
    * Group permissions
    * Integrated issue tracking
    * Collaborative code review
    * Wikis

Head over to [Github.com](http://github.com) and sign up for an account. You'll need it for nearly everything in this course and the bootcamp itself.

### Git Commands
Git is used to keep track of changes in your projects over time. You'll make a "snapshot" of your project with a `commit`. Then you'll have a `log` of your changes and can review them. If you mess something up, you can always `revert` to a previous commit and start again from where everything was working.

#### Initializing Git
Make a new folder called `basic_git`. You can initialize version control in your folder with:
```shell
$ git init
```
This adds some hidden files to your folder, a `.git` folder that will store information about your version control. Don't touch it - git will take care of everything.

![](Screen Shot 2016-11-29 at 1.03.10 PM.png)

If you installed the bash profile from the last section, your terminal should look like mine: a purple `branch` and a green check box - signifying that there are no changes to commit.

Now `touch git.txt` and `atom git.txt` to create and open a file. Add some text to it - anything is fine. Save. Now if you run another command in your terminal (like `ls`), you will see that the green check mark is gone and a light blue number is there instead. That is because we have files in our folder that are not part of version control. We'll add them now.

![](Screen Shot 2016-11-29 at 1.07.35 PM.png)

#### Git Status
To view all changes since the last commit, run:
```shell
$ git status
```

#### Staging area
Git has a concept of a ‘staging area’. This is where we gather up all the changes we want to add to a commit or snapshot of our work. First stage all of the changes you want in a single “commit”.

Add a single file to the staging area:
```shell
$ git add [filename] 
```
Or add all changed ﬁles to the staging area:
```shell
$ git add .
```

Note that after we add our file to the staging area, either by `git add git.txt` or `git add .`, our terminal prompt has again changed colors. Now we have a red dot and a number. This means we have files staged but uncommitted.

![](Screen Shot 2016-11-29 at 1.09.34 PM.png)

#### Commits
Create a commit. 
```shell
$ git commit -am “commit message”
```

Your commit messages are notes to yourself and other programmers about the changes that have been made since the last commit. They should be short and helpful. Here are some examples of good commit messages:
- Add acceptance test for user registration
- Fix bug #23
- Style form for signup

It takes some practice to get good at writing commit messages. See [this article](http://chris.beams.io/posts/git-commit/) for further tips. Employers will look at your commit messages (as well as your coaches and teammates), so it's well worth the investment of time to start writing them well from the start.

#### Git Log
To see a list of your commits, run
```shell
$ git log
```
Try `git log --oneline`. Some prefer to see a more condensed version of their log.

#### Remotes
Now we'll connect our local computer to GitHub. Sign into your account. Create a new repository using the `+` sign at the top right of the screen. Copy the repository (repo for short) URL:

![](Screen Shot 2016-11-29 at 1.17.41 PM.png)

Now add a remote repository by replacing `repo_url` with the url you copied above:

```shell
$ git remote add origin repo_url
```
`git remote -v` will show you a list of your remotes - the online folders you can connect to. Right now we only have `origin` - that refers to our own GitHub repository online. Later you will connect with your teammates with the same functions. "Origin" is just a nickname we use, by convention, for our own project online.

####Push
Push to your remote repository.
```shell
$ git push origin master 
```
We are pushing to `origin` our branch `master`. You only have one branch right now, but we are about to add a new one.

Now go to your GitHub repo and refresh the page - you should see your `git.txt` file.

Note that you don't have to push after every commit. You can save them up and push them all together if you like.

#### Branching
Branching is one of the most useful parts of version control. With a branch, we can try out all kinds of new code and if none of it works, we can just delete the branch. It's a way to organize features (things we want to do in our project) and also helps us work effectively with colleagues.

To see your current branches:

```shell
$ git branch 
```

To make a new branch:
```shell
$ git branch new_branch_name
```

To "checkout" or switch to your new branch:
```shell
$ git checkout new_branch_name
```

To both create and checkout a branch in one line:
```shell
$ git checkout -b new_branch_name
```

Now make a new branch - `git2`. Check it out and create a new text file inside this branch. Save, stage, commit, then push (use `git push origin git2` to `origin`. Go to GitHub and see what has happened. (Hint: check at the top left under "branch: master").

Locally (your own computer is referred to as `local`), check out `master` again. Where has your `git2` text file gone? The branch `master` doesn't know about it, so it will not appear in your text editor.

#### Merging
So now that we have a new branch and a second text file we would like to keep, we can merge the two branches so that can have all of our changes together.

First check out `master`. Then:
```shell
$ git merge git2
```
You have now "merged" changes from `git2` into `master`. You can see both files. Try `git log` to see the history. You can now safely delete the `git2` branch with:
```shell
$ git branch -D git2
```

**Craft Academy bootcamp students: when you have finished this exercise, drop a link to your `basic_git` repo in Slack so we can track your progress.**










