## Init First Repository
<pre>
create a new folder anywhere (I personally use my documents folder)
copy folder's path

open powershell
(keep a good habit of not closing your powershell window until signing out, since it's important to keep a log of your past commands)
(use up and down arrow keys to traverse through command history)

type this (the words in parentheses explain what each command does):
cd C:\whatever\path\you\just\copied         (changes active directory)
git init                                    (creates git repository in directory)

you just made your first repository!

creates a hidden .git folder you can see by enabling hidden files in the view dropdown  
DON'T DELETE .GIT OR ELSE ALL YOUR REVISION HISTORY WILL GO BYE BYE  
</pre>

[exampleImages\ex2.png](exampleImages\ex2.png)


## First Commit
<pre>
next text will show a small practice example to get you started with making commits:

create a txt file
open in text editor
type in whatever
SAVE

go back to powershell
make sure you're in the same directory you initialized git in

then type:
git status              (shows everything important)

your file should be in red
this file is not tracked by git yet

to track it, simply type:
git add filename        (adds/stages file to git repo (aka repository))
                        (adding a file and staging a file are the same thing)

your file is now tracked by git AND checked into the index (the stage)

to see this, type it again:
git status

your file should be green now

now that your file is staged, you can commit your file to the repository:
git commit -m "whatever you want your commit message to be"             (commits a file to a repo with a message - be descriptive! ; -m denotes a parameter, ie a string)

then type:
git status              (type this often - whenever you're not sure what git is doing)
                        (also can fix a few errors with gitk but that's later)

It should say:
On branch master
nothing to commit, working tree clean

you made your first commit!
now, check your commit history

type:
gitk

this should open a window that looks somewhat like this:
</pre>

[exampleImages\ex3.png](exampleImages\ex3.png)

<pre>
eventually, with enough commits and connection to github, your window will look a lot more like mine,
but right now there should be only one commit, shown in the top-left-corner, next to "master" 
</pre>


## Commiting again
<pre>
a few more steps to take after this

edit your text file however you want it, enough to be recognizably different
SAVE

powershell:
git status

your file should be in red
the file is still tracked, but it's now different, and not checked in

same drill:
git add filename
git commit -m "don't swear in your commit messages"
git status
gitk

there should now be two commits in your history

a few other things:
you can type this to simply commit all tracked files, whether they're staged or not:
git commit -a -m "whatever message you want"

the -a parameter indicates --all, shorthand for all tracked files

****However, it does not add untracked files. Use git add for that instead.

Leading up on that, if you need to add all of your tracked and untracked files to the staging environment (ie a file dump) use this command:
git add -A

this adds all of your files to the index, tracked and untracked
</pre>


## Important Keywords
<pre>
here's some keywords that I found are important to search up (prefacing each with "git"):
branch
merge conflict                      (can be pretty scary)
how to prevent merge conflicts
revert
reset                               (be careful, this deletes revision history - but not your files)
checkout
commit hash


you can also add "-help" as a parameter to commands, and documentation will print for you:
git branch -help
</pre>



[yes i learned all of this from a w3schools tutorial please don't judge](https://www.w3schools.com/git/)


next tutorial is in [connectGitToGithub.md](connectGitToGithub.md)
