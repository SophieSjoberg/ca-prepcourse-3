# **So you want to collaborate and write code with your pairing partner?**

In order to work with a pairing partner you will need to have a good git flow. This means that two programmers use git and version control to share code. The following guide is used to collaborate with version control, we call it "GitPong".  
For this exercise you need to collaborate with another student and follow these following steps:  
  
**Step 1 Setting the stage**

Create a new directory from your terminal

![](/assets/Screen Shot 2018-02-22 at 13.34.33.png)

Move into the new directory

![](/assets/cdgit.png)

_**Both**_** **programmers fork the [main repo](https://github.com/CraftAcademy/gitpong) 

**  **[![](/assets/Screen Shot 2018-02-22 at 13.47.27.png)](https://github.com/CraftAcademy/gitpong)**    
**

_**Both**_** **programmers clone the main repo

![](/assets/Screen Shot 2018-02-22 at 13.37.21.png)

**Both** programmers add the main repo as the upstream![](/assets/Screen Shot 2018-02-22 at 15.15.55.png)

Both programmer add each other as remote copy each others forked repo url and add those as a remote ** **![](/assets/Screen Shot 2018-02-22 at 13.39.10.png)

Check if all remotes are set it should look something like this![](/assets/Screen Shot 2018-02-22 at 13.39.31.png)

#### Step 2 Start ponging

**a\)**

**Programmer 1** makes changes to the README file and pushes to his/her own repo

![](/assets/git push.png)

**Programmer 2** pulls from Programmer 1

![](/assets/git pull.png)

**b\)**

**Programmer 2** makes changes to the README file and pushes to his/her own repo

![](/assets/git push.png)

**Programmer 1** pulls from Programmer 2

![](/assets/git pull.png)

And the process is repeated untill the project is completed

#### Step 3 Create a PR to the main repo

The last Programmer that finished the feature creates the Pull Request buy pushing it to his/her own repo and pressing the on her/his own repo and press the "New pull request" button.

![](/assets/Screen Shot 2018-02-22 at 16.14.39.png)

Make sure that the base fork is the main repo and that your head fork is your own repo.  ![](/assets/Screen Shot 2018-02-22 at 16.15.41.png)

Add information to the PR and press the "Create pull request" button and you are done!

![](/assets/Screen Shot 2018-02-22 at 16.17.53.png)

