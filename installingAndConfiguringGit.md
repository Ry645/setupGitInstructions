## Installation
<pre>
Search up: "Git - Downloading Package"

click on first result

click on "Click here to download" (important part should have a red box around it)
</pre>

[example image 1 (ex1.png)](exampleImages\ex1.png)

<pre>
this should download a file named "Git-2.46.0-64-bit.exe"

run file

choose preferred options, but mine are listed here:

Select Components - default
Default editor - VS Code
let git decide (most stable)
git from command line (to use with powershell, recommended)
bundled OpenSSH (important for connection with github)
openssl lib
checkout windows style
MinTTY
fast-forward or merge
git credential manager (convenient whenever you need a licence)
enable file system caching
no experimental stuff

click finish
should install correctly in C:\Users\USER_HERE\AppData\Local\Programs\Git
(or wherever else you want it)

not done yet!
open windows powershell (use start menu search bar)

type in:
git config --global user.name "FIRST_NAME LAST_NAME"
git config --global user.email "MY_NAME@example.com"

don't use your school email since the school blocks pushing to git hosting websites (GitHub, GitLab, etc.)
i would recommend making a separate "developer" email account to separate your work life from personal life
but that's just me
</pre>

ok, you got git set up!  
next tutorial is in [createFirstRepository.md](createFirstRepository.md)  

if you've already went through [createFirstRepository.md](createFirstRepository.md) and [connectGitToGitHub.md](createFirstRepository.md),  
skip to [workingWithGitHubRepository.md](workingWithGitHubRepository.md)  

