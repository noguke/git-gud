# git-gud

## Description
My tutorial on the necessary commands and techniques to git gud.

## Basic Stuff

#### Create a new repository
```
git init
```

#### Add new project to git repo
```
// while in working directory
git init
git add .
git commit -m "Initial commit"
// set-up your origin
git remote add origin <https://github.com/git_username/your_project.git>
git push --set-upstream origin master
```

#### Create/checkout a new branch
```
git checkout -b "<branch-name>"
```
More info on branches [here](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

#### Pushing your new changes
```
git add [file1 file 2 .. file10] // OR . for entire working path
git commit -m "your commit message"
git push
```

#### oh sh*t situations
This [website](http://ohshitgit.com/) will prove very useful

## Collaborative Etiquette

#### Setting Up

If you are collaborating on someone else's project, make sure to create a your own fork (a personal copy of the project) so you can make changes without affecting the original project

Then, clone down the fork that was created
```
git clone <https://github/your_username/example.git>
```
This will create the project in your working directory with your origin already set up.

Typically, I will create another remote to link the project to the original project's repository:
```
git remote add upstream <https://github.com/orig_author/example.git>
```

You can view the remote repositories your project is linked to by using
```
git remote -v
```

#### Ready to code
Make sure to get the most recent updates to the project:
```
git checkout master
git fetch upstream
git rebase upstream/master
```

Best practice is to create a branch off master for each new feature and bug fix you implement so you do not mess up your 'master' branch.

#### Code Review
Code is reviewed through github's pull request (PR) feature. When you commit and push your code, you can conveniently set up a pull request which will compare your new branch with the one you will eventually merge the change into. This is all possible through the GitHub UI.

![pullrequest](https://help.github.com/assets/images/help/pull_requests/pull-request-review-page.png)

There, we can view your changes, have a discussion and suggest any changes you should make before the code is production ready.
