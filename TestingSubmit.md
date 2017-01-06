-----stageing areas*** = 3---
***Working Directory >  untrack and modified are listed by runing git status

***Staging Area> files that wil be ccomited
orginizing what we want comited  = $git add -A //for all files or
$ git reset foobar.txt or git rest to move back to working directory

***.git directory (Repository)>$git commit  -m"initalcomitt foobar"//comits to the Repository
$ git push -u origin master
$git log //show the mesage and who and when of the last comit
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
-----------------------------------------------------------------------------------------------
Here's our logo (hover to see the title text):

Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"
# CREATE new BRANCH1 at github 
$ git checkout master


$git branch -a//*green is local pc


ls


clear


$git checkout -b foobar//creates new local branch


$git branch -a




$ git add -A

$ git commit -am "rrrrr"


$git push --set-upstream https://github.com/Michael-Toth/SpringBootIn50.git foobar


--------------------------------------------------------------------------------------------



------Adding an existing project to GitHub---------
Create a new repository on GitHub
Open Git Bash.
Change the current working directory to your local project.
Initialize the local directory as a Git repository.
$git init 
Add the files in your new local repository. This stages them for the first commit.
$ git add .//the last"." is for directoy copy
Commit the files that you've staged in your local repository.
$ git commit -m"firstcomitfromcmd" 
In the Command prompt, add the URL for the remote repository where your local repository will be pushed.
$git remote add origin remote repository URL
// Sets the new remote
$git remote -v
// Verifies the new remote URL
$git push origin master


---http://www.codebind.com/linux-tutorials/basic-git-commands-list/
Cmd operations---

cd
ls
cd /c
$ git config --global user.name "Michael-Toth"                    //is you git hub name
$ git config --global user.email foobar@foo.com                 //is you git hub name
--How to Dowload--
$ git clone https://github.com/Michael-Toth/TestGit.git           //copies directoyinto ur pc curent directory

---How to Upload---
//stageing areas = Working Directory >Staging Area>>.git directory (Repository)
$ git add TestingSubmit.txt or -A for all
$ git status //
$ git commit -m"firstcomitfromcmd" TestingSubmit.txt
$ git push -u origin master or u can $git pull origin master to make sure we are the lastone that changed the code
//the -u siginifes our local branch with remote brnach


-
----Initalize a Git Directory-----
$git init   //creates .git directory and starts tracking the projecy
$ git status //
$ls -la     // shows the director
$ rm -rf .git //stopss tracking the project
$ git status //
-----Cloneing-----
$gitclone urlfoobar.com .//the last period in comand means this directy or insted of the last period the directoy


-----Viewing Info---
git branch -a
git remote -v
That's the vi editor. Try ESC:q!.


----Ignore files----
touch .gitignore
ad file or *extsion to ignore in the . ignore file in the directory

COMMON WORK FLOW



$
$
$
$
$
$
---CREATE BRANCH-2-
$git branch fobar// CREATS FOBAR 
$git branch/list all local branches
$git checkout fobar//* denotes working branch
$git branch/list all local branches  * denotes working branch
--download a specific branch on git--
Clone the repository

$git clone <repository_url>//master branch

List all branches

$git branch -a 

Checkout the branch that you want

$git checkout <name_of_branch>

--merge brnach--
$git branch --merged /lists merged branches so far
$git branch merge  foobar/use when ur in the file directoy to acept the changes(I.e master)
$git push origin master
--delete Branch_--
Delete the .git directory in the root-directory of your repository //deltes the git from the files and is no longer tracked
$git branch --merged // checks
$git branch - d foobar //delets localy
$git branch - a//checks
$git push origin master --delete  foobar//remote delete

--delte amster branch---http://matthew-brett.github.io/pydagogue/gh_delete_master.html

How to delete master

First you delete master in your local clone. To do this we first make a new branch called placeholder or similar, and delete master from there:

git branch placeholder
git checkout placeholder
git branch -D master

All good so far. We next want to delete the branch on github. However, if we do this the naive way:

git push origin :master

we just get an error like this:

remote: error: refusing to delete the current branch: refs/heads/master
To git@github.com:matthew-brett/datarray.git
! [remote rejected] master (deletion of the current branch prohibited)
error: failed to push some refs to 'git@github.com:matthew-brett/datarray.git'

That is because github is looking at the master branch to provide the web content when you browse that repository. So we first have to make github look at our placeholder branch instead, then delete master.

First push up the placeholder branch:

git checkout placeholder # if not on placeholder already
git push origin placeholder

Then set placeholder to be the github default branch. Go to the main github page for your forked repository, and click on the “Admin” button.

There’s a “Default branch” dropdown list near the top of the screen. From there, select placeholder. On the interface I’m looking at, a green tick appears above the dropdown list. Now you can do (from the command line):

git push origin :master

and - no master branch...

