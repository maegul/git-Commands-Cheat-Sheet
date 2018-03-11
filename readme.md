
# Git Cheat Sheet

<!-- MarkdownTOC -->

1. [Vocabulary](#vocabulary)
1. [General commands \(for UNIX\)](#general-commands-for-unix)
1. [Git commands](#git-commands)
	1. [Setting up your local git program](#setting-up-your-local-git-program)
	1. [Starting a Git Repository](#starting-a-git-repository)
	1. [Adding files and Committing Changes](#adding-files-and-committing-changes)
	1. [Changing your history](#changing-your-history)
	1. [Making and Using Branches](#making-and-using-branches)
	1. [Syncing with GitHub](#syncing-with-github)

<!-- /MarkdownTOC -->


## Vocabulary

**Repository**
	A log book for a captain

**Commit**
	How you put something in your diary - a single diary entry

**Master**
	The name for the default “universe”

**Hunk**
	A location in your code where Git has detected changes

**Branch**
	Parallel Universe

**Master Branch**
	Original version

**Merge**
	Put history of one branch into another

**Origin**
	Online parallel universe

**HEAD**
 	Is a reference to the last commit in the currently checked-out branch.

**Working Tree / Working Directory**
	The actual files, with all the changes you’ve made, whether you have committed them or not

**Staging Area / Index**
	Intermediate collection of files and changes prepared to all be committed together.
	Useful for excluding some changes that you don’t want to commit just yet
	Ignore for now if you like




## General commands (for UNIX)

**List**
> ls 

_List what is here_

**Change Directory**

> cd [directory]

_Change to specified directory_

> cd ..

_Change to the directory above.  The double dots means 'directory above'_


**Where am I**
> pwd

_Print working directory ... the directory we are in now._


**Make A New Directory**
> mkdir [new directory name]

_Make a new directory in the directory that you are currently in._


**Copy**
> cp [original file] [new file]

_Copy the original file to a file named what you specify in "new file"_
_File specifications can include whole directories too: "/my_folder/file.txt"_

**Move**
> mv [original file] [new file]

_Much like cp, but doesn't copy the file into a new one, just moves it._


**Remove or Delete**
> rm [file]
> rm -r [directory]

_Remove (or delete) a file or directory._
_This is permanent!_
_Using the "-r" flag is necessary for directories_




## Git commands

### Setting up your local git program

**Configure your user name**
> git config --global user.name [My Name] 

_Lets git know who you are_
_If you ever collaborate with others, this way people can know which commits are yours._

**Configure your email**

> git config --global user.email my.email@myEmailProvider.com 

_Tell Git your email address_
_Create a config file in your home directory_


### Starting a Git Repository

> git init 

_Create that hidden .git directory so Git is ready to start working with your project._


> git status 

_“Hey Git, what’s up right now?”_
_Displays general information about your current repository._


### Adding files and Committing Changes
_Your Captain's Log or Diary_

**Add a File**
> git add [file] 

_Tell git to now keep records on a file so you can commit changes you've made to it._

**Commit a Change**

> git commit -m “Commit message here” 

_Whatever changes you've made (and added to the staging area), commit them with the note or message provided after the "-m" flag._


**Commit a Change without Adding to the Staging Area**

> git commit -a -m 'Added first verse' 

_The "-a" flag means: git-add, then do commit_
_Only works for changes to files that have previously been added.  If you want to commit changes to a new file, you have to add as above, then you can use the above._


**Seeing your History**

> git log
_shows captain’s log activity_


> git log --oneline 
_Show the git log in a more concise form._


**Seeing Differences between changes or commits**

> git diff

_Shows differences between current uncommitted changes and those of the most recent commit_


### Changing your history
_Time Travel_

**Cancelling previous commits**

> git revert [unique change id]

_The "Unique Change ID" is what the commands "git log" give you for each commit_
_Cancels the changes made in a particular commit, and adds a new commit recording this reversal of changes_


**Going back in time to a previous commit**

> git checkout [unique change id]

_Goes back to the state of your files at this commit_
_Lets you look at your files as they were at this time, and run code if you need to_


**Going back to the present**

> git checkout master


### Making and Using Branches
_Parallel Universes_

**List all Current Branches**
> git branch

**Make a new Branch**
> git branch [branch name]

**Go to a branch**
> git checkout [branch name]


**Merge the History of a branch into the current branch**
> git merge [branch name]

_Takes the history of "branch name" and merges that into the branch you are current in._
_Running "git branch" before, to confirm which branch you're in maybe helpful._
_If there are different changes in each branch that can't be merged, ie that conflict with each other, you will get a conflict that needs to be resolved._


### Syncing with GitHub
_Sharing your repositories online_

**List current Remotes**
> git remote -v

**Add your GitHub (or other) repository to your local repository**

> git remote add [name] [URL]

_Adds the URL of your online Repo to your local repo under the name you provide._
_Within Git, this is the name of the remote that you are using_


**Put your Local History onto your Online Repo**
> git push [remote name] [branch]

_Takes all of the history of the branch you specify and adds it to the remote you specify_
_This history is put into a branch of the same name as your local one, the one you specify._


**Bring changes that are on your online repo into your local Repo**
> git pull [remote name] [branch]

_Here, "branch" specifies the branch name in the GitHub account (which will generally be the same name as the one on your local computer, as it will have been created by you doing "git push" as above)_

_Will take the history of the "branch" on "remote name" and merge it into the branch you are currently in_
	

