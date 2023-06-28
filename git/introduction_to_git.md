# Why do you want to use GIT?

Git for vesion control
Git to share code
Git to collaborate
Open source

Open-source code is publicly available. Open-source code is often worked on by community collaborators. 

## How does Git work?

Use Git locally

Remote repository https://github.com/GitRepo

Local Computer:

- Local repository (.git)
      ^
      |
  command Git Commit
      ^
      |
- Staging area
      ^
      |
  command Git Add filename or GiT add . (add all the changes to the staging area)
      ^
      |
- Local folder C:\scripts\GitRepo\

Use a Git provider

Now we want to push our code to a remote repository. Push our code, we focus on
the committed fast so the ones that are in the local repository we can push those
files to the remote repository by using the command, Git Push, that's all we need
to do. All the files that were committed are now pushed to that remote repository. 

Remote repository https://github.com/GitRepo
     ^
     |
command Git Push
     ^   
     |
Local Computer (Local folder, Staging area, Local repository)


Now, let's say we are on a different device and we want to get the files that are
in the remote repository to our local device or maybe we are working with a repository
that other people have added code to. We use the command Git Pool, this pools all
the files, not only to the local repository but also to our local folder. Now we can work with them and we will always have the latest version.

Remote repository https://github.com/GitRepo
     |
     ^
command Git Pull
     |
     ^
Local Computer

Distributed version control

Git is what we call distributed version control. 

To do that, let's first look at centralized version control. This is a version control
that you might know from other syncing tools like OneDrive or Dropbox. All the information
that we have is on the server, and we can sync our local files with the server but
we always use the latest version. So if I change a file on my computer, it will
also be changed on the server, and after that, also on the computer of other people
who are working with that file. The old version is stored on the server, but not
on my local computer and not on the other computers. So that means if something
happens to the server, we will only be able to work with the latest file, but we
will lose the history.

Now in distributed version control, we still have a remote server, the Git Provider.
But every client that uses the file has their own database with all the snapshots
and history. So if I collect files from the Git Provider, I don't just get the files.
I get the complete history of the files. That means that even if something happens
to the Git Provider, we still have complete copies of everything that happened to
those files. Note that the Git Provider in this context is pretty much the same as
all the other computers. The difference is that it's centrally located where we can
grab our files, but we all have the same files and the same versions stored.

### Install and Configure Git

Install Git in Linux

So, if I want to install Git on Linux I can go to the official website git-scm.com
and then /download/linux. Here, it gives me a lot of different versions of Linux
and what the options are to install Git. So I can look for the OS I'm actually
using and find the right command. I've set up an example in Ubuntu. Now, when you
install Ubuntu, Git is actually already installed and you can find it by saying
**git --version** command. Now, this is a new installation, and the Git version
is actually up to date, but if you have an older installation, there's a big chance
that it's out of date, and you can install the latest version by using **sudo**
command if you are not logged in as root, otherwise, that's not necessary, and
then **apt-get install git**. As you see, it says here, there's already the latest
version at this time, but if you want to install a new version, this is the way to
do it on Linux.

Command: sudo apt-get install git - install the latest version
Command: git --version - show the latest version on the computer

Configure Git

So before we can actually start using Git, we need to do some configuration. All
configuration in Git is done through a file called Gitconfig. 

You have the configuration that applies to the whole computer. We call this configuration
a global configuration and you can find it on the home folder in the dot gitconfig
file or in the user folder of the user that you're using. 

You can also set local configuration and this can be a configuration for a specific
repository. You can find that in every repository in the dot Git folder. There's
a file called config and you can set specific settings for this repository. 

Some examples of these settings could be what your default editor is or what the
default branch name should be. Or you can set aliases to all kind of commands if
you want shorter versions.

Scopes:

- Global:
  .gitconfig 
  C:\users\[user\.gitconfig

- Local: for a specific repository
  .git/config

Settings:

- Default editor
- Default branch
- Aliases

Command: git config --list - we can see the settings that have been set by default

Now we need to add those two settings we were talking about. So we use Git config
and we'll add this to the global settings file and we'll add our user's name. So
you can add your own name here. There we go. We won't get any feedback and after
that, we need to add our email address. This email address should be associated
with whatever Git provider you are using. So now if we use Git config dash dash
list, again, the two new settings will have been added at the bottom. As I've said before, there's a lot of settings you can add here but these two are the only ones that
are mandatory.

Command: git config --global user.name "your name"
Command: git config --global user.email "name@example.com"
Command: git config --list

#### Push your code with Git

1.Set up a remote repository

If you don't have an account yet, you can go to github.com (git provider). If you
see in the upper right corner, there is a link where you can sign up. It's completely
free to do so, you just need an email address. Once your account is ready, you
have the option in the web interface to create a new repository. 

We have a few options to fill in. First, we need to decide on the repository name,
this will be part of the URL, so it's best to not use spaces. For this, I will just
call it git-repo, which is short for repository. I can add a description if I want
to, and I can choose if I want this repository to be public or private. If it's
public, it's available to everyone. It doesn't mean that people can commit code to
it, but they will be able to see all your code. In this case, I'm going to create
a private one, so I'm the only one who can see and commit to this repository. Here
I can choose if I want to initialize the repository. I can add a Read Me file, I can
get a gitignore, and I can choose a license if I want to. I'm just going to add a Read
Me file because it's best practice to have that in every repository. We're not going
to set the other files at this moment, but once you get a hang of it, I do encourage
you to check what they are and why you could choose them. We'll click Create Repository,
and within a few seconds our repository is ready.

2.Clone the remote repository

We click Code right here. When we click that we get a URL that we can use to clone
this repository, which means that we make a local copy. I'll copy the URL and then
I'll open a terminal. I have created an overall folder where I want to keep all my Git repositories. In this case, I called it Code. What I'll do is type git, then clone,
and then I'll paste the URL that we just copied. I'll press enter. And it's now creating
a new folder for this Git repository. I can open it up. I'll do that in Visual Studio
Code by using code and then the name of the folder, git-repo. Press Enter. And here
I can find the Git repository that I had created in GitHub with the README file.

git clone link - type this in the terminal
code .\git-repo\ and press enter

3.Create a file and stage it

I'll right click and choose New File. I'm going to create a file called example.txt.
Note that it doesn't matter what kind of file I'm creating, I could also create code
in here. I add some content and I click Control + S to save this file. I can now add
this file to the staging area to make sure that Git understands that I want to save
this file in the next commit. So I'll use Git add and then the name of the file it
now has been added to the staging area. Note that in this case, I could also have
used Git add. If I use that and I make changes to both the example file and the
ReadMe file, they would both be added to be considered for the next commit.

git add example.txt - add to the stage area file example.txt
git add . - add to the stage area all changes

4.Commit a file

git status - to check where is our file "example.txt"

Let's commit this file locally.

git commt -m "adds example.txt"

I will say, "git commit -m". And now I can fill out a message so I can tell whoever
is viewing this history why I made a commit here or what I added.
This means that locally a snapshot has been created of the state of this file.

5.Push the file to the remote repository

6.The .git folder

7.Initialize a repository locally and sync it to the remote repository

git init - create an empty Git repository or reinitialize an existing one
git add .
git commit -m "initial commit" - we have a set up the local repository
git remote add origin URL- assign the local repository to the remote repository

##### Make changes to files

1.Git status

mkdir GITT - create a folder in the local computer
cd GITT - move to the folder GITT
git init - create a new local repository
touch example.txt - create a file example.txt
mv ../example.txt . - move the file example.txt from the folder documents to the
folder GITT (for one level down)
git add example.txt - add the file to the stage area
git commit -m "Added example.txt" - add the file example.txt to the local repository
git remote add origin URL - join the local repository to the remote repository
git push -u origin master - push our file to the remote repository
git restore --staged example.txt - unstage the file example.txt from the uncommitted local changes, unstage changes you have previously added to the Staging Area.

2.Edit a file and view changes

git add
git diff --staged

And here I will get the same overview so I can see exactly what has been removed
and what has been added to all my files before I make a commit.

3.Make use of the GUI of Visual Studio code

4.View commit history

git log - show the history off all commits

If you want to get out - press Q and then can add a new command

git show - check the information about one commit
git log -p - it will show what has happened in every commit that has been done

git log --graph - show us the visualization of how your branches are moving around.
Finally, a nice option is to do a search for a specific part of a commit message

git log --grep="what will find" - a search for a specific part of a commit message

5.Delete files

git rm --cached <filename> - we delete the file from Git and working area
rm - we delete the file from the file system

6.Rename files

git mv example.txt example1.txt - rename the file local repository
git add . - add to the staged area
git commit -m"Renemed the file"
git push

If we checked the site git, we will see the changes

7.Working with folders

Making the folder in Visual Studio Code (press + folder), move the file example1.txt
to the folder
git add .
git commit -m"Added the file to the folder"
git push

cd ~/Documents/GITT - if you need to jump through the folder - you type a right path
cd ../.. -  the same meaning through 2 folder (.. - one folder)

git commit --amend - change the commit message
git push --force - if you change the commit history, need to use force, but if you git commit with some file with changes it is possible to do it wothout "force"

But did you notice that we added two folders and I only see one of them here. This
is an important concept of Git. Git doesn't keep track of empty folders. So if a folder
is empty, it's going to be ignored, and you saw it nowhere in that staging or in the
status. There is a way to make sure that Git does keep track of the folder and it's
making sure it's not empty. So we add a file and we have a format for that. We call
that .gitkeep. This is something that developers use to make sure that it's understood
that this folder is important for the structure, but there's no content in it. So I'll
add it with the dot, I'll commit it saying adds secondfolder, and I can now push this.
And if I look at my remote repository now and I refresh, it will have that secondfolder
with the empty file here. So as you saw, I just had to name it .gitkeep. I didn't have
to add any content to it. And if I finally have content in this folder, of course, I
can delete it.

8.Undo your changes

git restore --staged 
git restore .

9.Look back in Git history

git log - see the history of all commits
git checkout 2ds33re - see the history of the derached state without joing to this branch
git checkout master - come back the branch master

See previous versions

10.Revert to an old state

Come back to previous versions

git log --oneline
git revert dkkl28485 - ID of the commit that I want to back

Now, one thing that's important is I'm not actually going back into history because
that's considered bad practice because we want to keep track of that history and
there's a big chance they're going to cause some issues if other people are also
using that code. So if I look at the history with oneline again, I see there's actually
a new commit, which code revert adds secondfolder.
So instead of removing part of the history, I'm adding some extra history that tells
you that I went back to a previous state.

Chellenge:
1.Create file "importantfile.md"
2.Add line "This is an important file", stage and commit the file
3.Add line "This is an important update to the important file", stage and commit the file
4.Create the folder "Important folder", add the file to it, stage and commit it
5.Revert: the file moves out of the folder and back to root folder

touch importantfile.md - make the file
nano importantfile.md - make some changes into the file
git add .
git commit -m"Added a new line This is an important file"
nano importantfile.md
git add .
git commit -m"Added a new line This is important update to the important file"
mkdir "Important folder" - make the folder, directory
mv importantfile.md "Important folder" - moving the file to the folder
git add .
git commit -m"Move the importantfile.md to the Important folder"
git log --oneline - see all commits in oneline
git revert 75059250a3e828f1f953be83986b603595cd0a68 - discard the changes
git log --oneline 
It shows a new commit with text "Revert "Move the importantfile.md to the folder""

###### Important Concepts in Git

1.Ignoring files

Let's first see how you can make Git ignore files. So what will often happen in folders
where code is involved is that there are files there that you don't want to track with
Git. They are often not interesting for the code but you need them for the application
locally. Or maybe you have some local settings you want to take care of that you don't
want to actually sync with Git and we can do something about that and we do that with
the file called git ignore.
.gitignore

Git knows this file and knows that everything that is mentioned in there needs to be
ignored.

touch .gitignore
mkdir logs
touch filelog1.txt
mv filelog1.txt logs
nano .gitignore
#filelog1.txt
git status
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

2.Git branches

Branches can be used to have a second version of the same code to work with. This is
useful, for example, if your code is running production and shouldn't be changed
while you are developing things. It can also be very useful if more than one person
is working on the code at the same time. Overall, in big projects, it's considered
the best practice to do all changes in branches.

So what's happening when you create a branch? We have the code that's running production
and the Git provider. And over here we can create a branch, which is a copy of the code.
So we can do it at the Git provider but we can also do it locally. So it can exist in
both places. So we have created a branch and we start making changes within this branch.
Note that production is keeping the same code so the main branch is not changed. What
we can do now with our branch is publish it to the Git provider. When we are done and
we want our changes to become part of production, we create what we call a **pull request**.
Locally, you would just merge this branch, but with bigger projects, often a pull request
is required. This is also a place where people can give reviews to your code. Once the
pull request is completed, your code becomes part of the main branch, and it's best
practice to delete the old branch, and it will seem like everything you did in the
branch is part of the main branch. Ideally, these branches have a short life. So you make
a branch for a specific future or bug that you are working on. After that is done, you
create that pull request, and it is merged.

3.Git commit messages

Git commit message is the most important part of the commit, as it helps to track the
version history.

A Git commit message should:

- describe exactly what changes are applied
- be present tense
- be a max of 50 characters
- could have an extra description if a blank line is added

4.Getting out of trouble

When Git get cause trouble:

- Git gives a lot of flexibility to work with code
- it can do a lot on its own
- but sometimes you will encounter issues

Merge conflicts

- merge conflicts
- different people working on the same files
- getting confused about where you are in history
- forgetting to move branches

Test

1.Why do you want to use Git?

- Where is Git located on your computer?

    - [x] It is installed as separate software.
          Although sometimes Git is part of the OS, overall, you will install it
          from the internet.
    - [ ] It is on the internet.
    - [ ] It is part of the Office Suite.
    - [ ] It is a part of the file explorer.

- Why would you use Git for your own files?

    - [ ] to make editing the code easier
    - [ ] to check if your code is correct
    - [ ] to create a folder structure for your files
    - [x] to keep track of old versions of files
          Git helps make sure you can go back to an old version, without saving
          multiple copies.

- You and your coworker want to use Git to work on the same code. How do you do that?

    - [ ] You send your coworker the code through email.
    - [ ] You open a Teams session so you can work in the same screen.
    - [ ] You need to make a direct Git connection between your machines.
    - [x] You store a version of the files online at a Git provider.
          When you store the code at a Git Provider, you and your coworker can
          both get a local copy and work on that.

- Fred wants to use Git to share a file from his computer with his friend Sally.
  What is not required to accomplish this?

    - [ ] Fred must have an account with a Git provider.
    - [x] Sally must have an account with a Git provider.
          While Fred might prefer to give Sally direct access, it is not necessary.
          He could make his code public and share the URL with Sally.
    - [ ] Fred must have Git on his local device.
    - [ ] Fred must have all the files he wants to share.

- What problem does branching solve?

    - [ ] It blocks people from deploying code to a repository.
    - [ ] A branch is used to put part of the code outside of the repository.
    - [ ] You can share a branch between multiple repositories.
    - [x] When a lot of people work on the same file, Git might not be able to
          merge the different files.
          Branching solves more problems than this, but this is one of them.

- You and your coworker are working on the same file at the same time. What will
  happen when you push the changes?

    - [x] Git will try to merge the changes into one file.
          Git has some intelligence to merge code, even if it is changed at the
          same time. If it is not possible, you can fix it manually.
    - [ ] Access to the file your coworker is working on will be denied.
    - [ ] Git will throw an error when you try to save your changes.
    - [ ] Git will use only the changes that came in last.

- You have made a branch and are working on a file. What can you expect when you
  look at the file in the remote repository?

    - [ ] The file will show an error as the remote repository sees you are working
          on a different branch.
    - [ ] The file will have a remark that changes have been made.
    - [ ] The file will have your changes incorporated as edits are saved.
    - [x] The files will look just as they did when originally accessed.
          Unless and until changes are merged into the master repository, you work
          on your local repository, so those changes remain local.

2.How does Git work?

- When you use Git Pull, where can you view the old, new, and changes files?

      - [ ] They are in the local repository, where you can use Git pull --local to collect them.
      - [ ] They are in the staging area so you can commit to them directly.
      - [x] They are visible in the local folder.
            Pull adds the file to the local repository and directly to the local folder.
      - [ ] They can be shown by using git status.

- When you use Git push, what changes are pushed to the remote repository?

      - [x] the changes in the local repository
            Only changes in the local repository will be pushed.
      - [ ] the changes in the local folder
      - [ ] The changes you made in the last day
      - [ ] the changes in the staging area

- You are working on a Git repo but must do some work without an internet connection.
  What can you not do?

      - [x] Push your changes to the remote repository.
            To push the changes, you need to connect to it through the internet.
            All other actions can be performed even without internet.
      - [ ] Revert to some changes you made earlier.
      - [ ] Make snapshots so you can keep track of changes.
      - [ ] Go back to earlier versions of the files.

- What is the effect if a file in the main repository becomes corrupted?

      - [ ] Local copies are at risk, and all work on them should stop.
      - [ ] Local copies will become corrupted but can be reverted.
      - [x] There is no effect on users' local copies.
            Because Git is distributed, the file in users' repositories will be
            unaffected by any changes to the file in the main repository unless
            users attempt to retrieve the corrupted file.
      - [ ] Local copies must be deleted to avoid corruption.

- Which command do you need to use to add the staged changes to the local repository?

      - [ ] git status
      - [ ] git add
      - [x] git commit
            Git commit will add the staged changes to the local repository, don't
            forget to add a commit message!
      - [ ] git push

- What do you need to know to start working with Git?

      - [ ] You need to be familiar with every Git command.
      - [ ] You need to get the GIT certification.
      - [x] Just the basics, you can learn on the way.
            You can get started straight away, which will help you to understand
            how Git works.
      - [ ] You need to have knowledge of the Microsoft Azure cloud.

- Where is the repository information stored in your local folder?

      - [ ] in the .version folder
      - [x] in the .git folder
            The .git folder stores all information and configuration.
      - [ ] in the .code folder
      - [ ] in the .config folder

3.Install and Configure Git

- Which action is not a way to gain access to Git on a Mac?

      - [x] Install Git with the terminal utility command install git.
            The terminal utility on a Mac does not have an install command. HomeBrew
            commands can be used on the terminal command line instead.
      - [ ] Use the pre-installed version on newer Macs.
      - [ ] Install Git with the HomeBrew command brew install git.
      - [ ] Install Git with the MacPorts command: sudo port install git from git-scm.com.

- Which action will successfully install Git on any Linux system?

      - [ ] Use apt-get install git.
      - [ ] Download the package installer for the Linux distribution from git-scm.com.
      - [ ] Use dnf install git.
      - [x] Use the command specific to the Linux distribution, as listed on git-scm.com.
            The Git website lists commands for each distribution of Linux to ensure
            users can properly install Git on their specific system.

- What is the best way to find out what GUIs are available for your OS?

      - [ ] You try them and see if it works.
      - [x] There is a list on git-scm.com.
            You can find a list with the most well-known GUIs on git-scm.com. They
            are all third-party tools though.
      - [ ] There is only one GUI tool for each OS.
      - [ ] You can find a list on git.com.

- Why would you use a GUI for Git?

      - [ ] This is needed to work with a remote repository.
      - [ ] It helps you with finding errors in your code when you commit it.
      - [x] to help you keep track of what happens to files and what commands to use
            While a GUI isn't needed, it surely does help to visualize what is happening.
      - [ ] Git will not work from the command line only.

- A user is unsure of the version of Git installed. Which command should they use?

      - [ ] git -version
      - [x] git --version
            The user might also be able to type simply git version to learn the
            installed version of Git.
      - [ ] git
      - [ ] git help

- Which two settings are mandatory to start working with GIT and remote repositories?

      - [ ] core.editor and core.pager
      - [x] user.name and user.email
            You need to define the user.name and user.email setting to push to remote repositories.
      - [ ] No settings are mandatory.
      - [ ] user.key and user.name

- How can you check if Git has been correctly installed?

      - [ ] Open Visual Studio Code and check the settings.
      - [ ] Check your GitHub account.
      - [x] Open a terminal or PowerShell window and type either Git or Git --Version.
            This is the best way to check if Git installation has succeeded if you
            use --Version.
      - [ ] Run the wizard again. If Git was already installed it will tell you.

- What does "Add 'open with code action' to Windows Explorer File Context menu" do?

      - [x] It adds an option to the right-button-menu in the file explorer to open a file
            directly with Visual Studio Code.
            With this option you can open Visual Studio Code directly from a file.
      - [ ] It configures your computer to open all relevant files with Visual Studio Code.
      - [ ] It adds an option to open the file explorer from a file in VSCode.
      - [ ] It adds an option to the right-button-menu in the file explorer to open a folder
            directly with Visual Studio Code.

- What settings are necessary to change in the install wizard to use Git?

      - [ ] initial branch name
      - [x] none
            There are a lot of settings, but you can use the defaults on all of
            them if you want.
      - [ ] default editor
      - [ ] installation location

- Why would you use Visual studio code for Git?

      - [ ] When you use Visual studio code, you don't have to download Git.
      - [ ] It fixes errors in you Git commands.
      - [x] It gives a gui to help with basic Git operations.
            With Visual studio code, you can use buttons instead of commands. This
            can be very helpful when you are new to it.
      - [ ] It makes Git operations run faster.

- What scope does the git config --list command use if no scope is defined?

      - [ ] local
      - [ ] system
      - [x] global
            By default, Global is used. If you want to use another scope, you need
            to define it.
      - [ ] user

- How do you change the username in the global configuration to "John Doe"?

      - [ ] git config user.name "John Doe"
      - [x] git config --global user.name "John Doe"
            This will change the global username in the config.
      - [ ] git set --global user.name "John Doe"
      - [ ] git config --global username "John Doe"

4.Push your code with Git

- What is the purpose of the .git folder?

      - [ ] It shows you what has been committed but not pushed.
      - [ ] It shows you what is in the staging area.
      - [x] It stores all configuration and versions of the repository.
            The .git folder is what makes the folder a Git repository. All data
            and configuration is stored there.
      - [ ] You can read and copy your Git provider credentials from here.

- Who can view and commit to a private repository?

      - [ ] Everyone can view it, but only people you invite can commit.
      - [ ] only you and the people you have given access to your account at the
            Git Provider
      - [x] only you and people you have invited
            You can control who can commit and view to your repository by inviting
            their account.
      - [ ] only you

- You have committed new changes on your local device. You sign into the repository
  in the webinterface of the Git provider. What do you see?

      - [ ] the new versions you created

      - [ ] all files that you are working on are temporary not available
      - [x] the old versions of the files
            All your changes are only local, so the files in the Git provider will
            be the old unchanged versions.
      - [ ] a note that new commits are ready to push

- What is not an example of a remote Git provider?

      - [ ] GitLab
      - [x] git.scm
            git.scm is the official website for Git, but it is not a provider.
      - [ ] GitHub
      - [ ] Bitbucket

- What will git init write to a directory?

      - [ ] both repository files and the .gitconfig file
      - [ ] the .gitconfig file
      - [x] a .git directory
            Git init initializes the directory with a .git directory containing
            project-specific files.
      - [ ] the files of the named repository

-Say your repository is stored at https://git.com/user/repo.git. How do you make
 a local copy?

      - [ ] Git Clone --url https://git.com/user/repo.git
      - [x] Git Clone https://git.com/user/repo.git
            This will clone the repository as a new folder in the current one
      - [ ] Git Clone --https://git.com/user/repo.git
      - [ ] Git Get https://git.com/user/repo.git

- How can you recover data from a deleted .git directory?

      - [x] A deleted .git directory's contents cannot be recovered.
            Git keeps all project tracking data in the .git directory, and when
            it is deleted, all the tracking data goes with it.
      - [ ] Reconstruct it from the .git directory in a project's subdirectory.
      - [ ] Run git init and git config to recreate the contents.
      - [ ] Copy the project's .git contents from /etc/git/ or Program Files\Git\etc\.

- How do we get the URL we need to clone a local copy?

      - [ ] You type Git Clone --list to get a list of all available repositories.

      - [ ] You can find it in the global git config.

      - [ ] You can find it in your account settings on the Git providers website.
      - [x] It will be available at the Git provider's web interface of the repository.
            Depending on the provider you use, you can find some sort of " clone"
            button on the web interface of your repository.

- You have made changes to two files: example01.txt and example02.txt. You use git
  add example01.txt. What will happen when you commit the changes?

      - [ ] All changes will be committed.
      - [x] only the changes in example01.txt will be committed
            Since you have added example01.txt to the staging area, only this file
            will be committed.
      - [ ] The changes in example02.txt will be reverted.
      - [ ] Git will give an error.

- Which command do you use to push new code to the remote repository?

      - [x] git push
            Git Push takes the changes that have been committed and syncs them to
            the remote repository. No options are needed.
      - [ ] git push .
      - [ ] git push --global
      - [ ] git push -m "push new code"

- You have made changes to two files: example01.txt and example02.txt. You use git
  add example01.txt. You use 'git commit' What will happen?

      - [ ] Git will give an error.
      - [x] Your text editor will be open.
            You didn't add a commit message with -m. Because of that, a text editor
            will open to allow you to write a commit message.
      - [ ] Git will commit only the changes in example01.txt.
      - [ ] Git will commit all the changes.

- How do you connect your local repository to a remote repository?

      - [ ] git init
      - [x] git remote add
            You add the repository by using Git Remote add and then defining the remote repository.
      - [ ] git status
      - [ ] git commit

- How do you stage every file you have changed?

      - [ ] git add ,
      - [ ] git add --all
      - [ ] git add
      - [x] git add .
            The dot in this syntax stands for all files, so it will stage all of them.

5.Make changes to files

- Which command can you use to rename a file in Git?

      - [ ] git push
      - [x] git mv
            Git mv with the right options will rename a file.
      - [ ] git rv
      - [ ] git rename

- You change the name of a file in the file explorer. What happens when you run
  Git status?

      - [ ] Git will say the file has been renamed.
      - [ ] Git will have added these changes directly to the repository, so there
            will be nothing to commit.
      - [x] Git will say a new file has been added and a file has been removed.
            At first glance, Git will think there are two separate files. Once you
            add them to the staging area, Git will understand that the file has
            been renamed.
      - [ ] Git will run an error.

- What is the purpose of a .gitkeep file?

      - [ ] It keeps a backup of files that you want to always keep even if they are deleted.
      - [x] It serves as a placeholder so a folderstructure can be committed.
            While you can enter any placeholder file you want, this file is known
            for this purpose.
      - [ ] It is a list of files that you cannot delete from the repository.
      - [ ] It tells Git what files to ignore.

- You create a new folder in a repository. You add it with git add . You commit the
  changes. What will happen?

      - [x] Nothing, as Git doesn't keep track of empty folders.
            Git keeps track of files, not folders. The folder will only be saved if
            a file is in there.
      - [ ] The new folder is added to the staging area, but not to the local repository.
      - [ ] The folder is now part of the snapshot.
      - [ ] Git gives an error that you need to add files to the folder.

- How do you view the changes in all previous commits?

      - [ ] Git log -q
      - [x] Git log -p
            By adding the option -p, all changes are shown in the history.
      - [ ] Git log --all
      - [ ] Git log -c

- What key closes the commit log view?

      - [ ] tab
      - [ ] esc
      - [ ] X
      - [x] Q
            When you press Q, you will get to the prompt. The alternative is to keep
            pressing space, but that could take a long time!

- What happens when you delete a file from a Git repository and commit your changes?

      - [ ] It is removed from your history, but still visible in the remote repository.
      - [ ] It is deleted both from the current code and from the history.
      - [ ] You can't delete a file from a Git repository.
      - [x] It is deleted from the current code, but still visible in the history.
            While the code is no longer visible in the current files, it is saved in
            the history.

- How do you find all the commits with the phrase 'example' in them?

      - [ ] git log --find='example'
      - [x] git log --grep='example'
            You use grep to search strings. You can use Regex as well!
      - [ ] git log --list 'example
      - [ ] git log --get='example'

- How do you discard all changes you made in the working directory?

      - [ ] git restore --all
      - [x] git restore .
            This will remove all changes you have made.
      - [ ] git restore
      - [ ] git revert

- Git status tells you "Your branch is ahead of 'origin/main' by 1 commit. What
  does this mean?

      - [ ] The local repository is no longer connected to the remote repository.

      - [ ] You need to create a new branch.

      - [ ] There are changes in the remote repository that you don't have locally.
      - [x] You have committed changes that are not in the remote repository.
            You can fix this situation by using Git Push.

- You have staged some changes in the file example.txt, but you decide you don't want
  to commit them. Which command do you use?

      - [ ] git return --staged example.txt
      - [x] git restore --staged example.txt
            This will bring the file back to the working directory.
      - [ ] git return --cached example.txt
      - [ ] git restore --cached example.txt

- What is the most likely cause if git status results in the output "Not a Git repository"?

      - [ ] You need to change directory to the repository's top level.
      - [x] There is no .git directory in the current directory or in parent directories.
            Git will check parent directories to confirm the user is not in a subdirectory
            of a repository.
      - [ ] Git has not been installed on this system.
      - [ ] You need to use the command git config gc --depth 100.

- How can you view the changes in the staging area?

      - [ ] git diff
      - [x] git diff --cached
            Using --cached will show you the changes in the staging area specifically.
      - [ ] git diff --staged
      - [ ] git diff --add

- Considering the following output, if you decide you don't like the change shown
  in this diff, where should you go to find the output line(s)?

--- a/README.md
+++ b/README.md
@@ -1,3 +1,5 @@ 

-This is a new line
+This is a new line
+
+And another one

      - [ ] line 6
      - [x] line 1
            The information between the "@@" symbol pair is the starting point (preceded
            by the dash) and the ending point (preceded by the plus), in this case, line 1.
      - [ ] You can't tell.
      - [ ] line 7

- You have four commits in your project, and the HEAD is the most recent. What do
  the Git logs show after reverting the third commit?

      - [x] The logs show a fifth new commit indicating which commit was reverted.
            History will not be rewritten in Git; the log will show that a commit
            was reverted.
      - [ ] The logs show three commits, with the third as the HEAD.
      - [ ] The logs show four commits, but with the third as the HEAD.
      - [ ] The logs show one commit, indicating the commit chain was broken.

- Which part of Visual Studio Code do we use for Git?

      - [ ] Explorer
      - [ ] Run and Debug
      - [ ] Search
      - [x] Source Control
            Git is Source Control, so you can manage your Git files from this section.

- Which extensions do you need to install to work with Git in Visual studio code?

      - [ ] GitHub
      - [x] none
            While there are some extensions that can help with using Git, it is not
            needed to install them.
      - [ ] Git Graph
      - [ ] GitLens

- How do you go back to a specific commit?

      - [x] git checkout
            You use git checkout to look back at a specific commit.
      - [ ] git restore
      - [ ] git status
      - [ ] git push

- Which command do you use to view the changes in the files you are going to commit?

      - [x] git diff
            Git diff will show you the lines in the code that have been changed.
      - [ ] git commit
      - [ ] git add
      - [ ] git status

- In what way does the commit history change when git revert is executed?

      - [ ] The commit to be reverted is nullified and HEAD points to a new revert commit.
      - [ ] The commit to be reverted is deleted from the commit history.
      - [x] HEAD points to a new revert commit that is a descendent of the previous HEAD.
            Because Git prioritizes integrity of data, the ancestry of HEAD will not
            change -- a new commit that reverts the prior commit's changes is added.
      - [ ] A revert commit replaces the specific commit in the commit history.

- What does a detached state mean?

      - [ ] The staging area has changes that still need to be committed.
      - [x] The files you see are not connected to the current version of your code.
            You are in some part of the history of your git repository, so you cannot
            commit anything in the current branch.
      - [ ] You must pull before you can push.
      - [ ] Git got into an error and needs to be restarted.

- You have a file in the staging area. What changes will Git Status make to your
  repository?

      - [ ] All other changes in the folder are also added to the staging area.
      - [ ] The file will be committed.
      - [ ] The file will be reverted.
      - [x] Nothing. Git Status shows what your current state is, it will not change
            that state.

6.Important Concepts in Git

- What file do you need to add to make Git ignore certain files?

      - [ ] .getignore
      - [ ] .config
      - [x] .gitignore
            When you add a gitignore file, all files mentioned in there will no longer
            be tracked.
      - [ ] .git

- Which line in a .gitignore file would ignore all files ending in ".md" in a directory
  named logfiles, and nothing else?

      - [ ] *.md
      - [x] logfiles/*.md
            This is the correct syntax to reach the goal.
      - [ ] logfiles/
      - [ ] !logfiles/*.md

- You make some changes to your repository and push them to the remote repo. You get
  an error: "failed to push some refs to [url]". What went wrong?

      - [ ] You added some code that is not working to your file and need to fix that first.
      - [ ] You first need to run Git commit.
      - [ ] You first need to run Git merge.
      - [x] You first need to run git pull.
            This error means there is a difference between the remote repository and
            the local repository. When you run git pull, it will collect the changes
            from the remote repository.

- How many branches does a repository need to work?

      - [ ] 2
      - [ ] 3
      - [ ] 0
      - [ч] 1
            Every repository has 1 branch, as the main branch is also a branch!

- Why do you create a pull request?

      - [x] to get the code from a branch added to the main branch
            A pull request is used to get code to a main branch and enable automatic
            testing and reviews.
      - [ ] to see what would happen if you used git pull
      - [ ] to clone a new branch to the local repository
      - [ ] to create a new branch in a remote repository

- Which command helps to create a multiline git commit message?

      - [ ] git commit -m @'text here'@
      - [x] git commit
            When you use git commit without the m option, it will open a text editor
            for you to create a message.
      - [ ] git commit --longmessage 'text here'
      - [ ] git commit -l 'text here'

- Which single line commit message uses best practices?

      - [ ] form submission error on customer query contact form
      - [ ] Temporary change to user notice for PSM requirements -- needs follow-up
            after the new year.
      - [ ] You changed cookie expiration to eliminate a login timeout issue.
      - [x] adds dashboard feature to display client usage log summary as pie chart 
            This message is written in present tense, gives an overview of the change
            made in the commit, stays within character limits, and does not include
            unnecessary information.


