## Connect Both Repositories
<pre>
now, all you need to do is to connect the repository in your computer to the repository in github

first, open up powershell:
cd C:\wherever\your\repo\is
git status                      (just to make sure it's the correct repo)

now you're going to need to add an ssh url

go back to github
find your repository (go here: https://github.com, and it should be in the left sidebar)

once you get there, the website address should be like: https://github.com/GITHUB_USERNAME_HERE/REPO_NAME_HERE

click on big green "<> Code" button and click on "SSH"
</pre>
[exampleImages/ex7.png](https://github.com/Ry645/setupGitInstructions/blob/master/exampleImages/ex7.png)
<pre>
copy url

you got the ssh url

now it's time to sync your two repositories together

type this in powershell (paste your url in place of example@url.com):
git remote add origin example@url.com

and import from your computer:
git push -u origin master               (this "pushes" the code into the new repository)
                                        (the -u means it will default to that branch now, and you now just have to type "git push", same applies to "git pull")

if you refresh github, you should see your imported files!
</pre>


## Pulling and Pushing Commits
<pre>
now, anyone with access can run this command:
git pull -u origin master

and they will download the entire filesystem, revision history included!
this is perfect for collaboration, especially when file history is important

if you don't want the pulled branch to merge with your current work and wipe it,
make sure to create a new branch:
git branch myBranch

and switch to it:
git checkout myBranch

you can then run
git pull
to load the files onto "myBranch", without messing with "master"
git always tries to merge with the current branch when using "git pull", so be careful to not lose any of your work (i.e. backup your .git folder someplace safe)
</pre>

## you dun did it
<pre>
i think that's everything
you'll need to repeat the process explained in this text file for each and every repository you'll make

it really doesn't take that long though

it's just:
git remote add origin example@url.com
git push -u origin master

ez
</pre>
