# **IMPORTANT: REQUIRES ADMIN PASSWORD FOR SOME PARTS**

## Connecting Account
<pre>
create github account using dev or personal email (whatever email you put in your git config)
link to github account creation tutorial:
</pre>

[https://www.youtube.com/watch?v=Gn3w1UvTx0A](https://www.youtube.com/watch?v=Gn3w1UvTx0A)

<pre>
create a new repository in github
i guess name it hello-world idk

you're soon going to upload your recently made repository to this one in github

but first, you have to authenticate with github
you'll need an ssh (Secure Shell) key for that

you can't just input your github username and password into powershell anymore since it just doesn't let you for some reason
also don't bother with https and PATs (Personal Access Tokens), i couldn't get them to work

anyways

time to generate an ssh key!
</pre>


## Powershell Stuff
<pre>
go to powershell and type this:
ssh-keygen -t ed25519 -C "ry645.dev@gmail.com"          (generates an ssh key)

log:
Generating public/private ed25519 key pair.
Enter file in which to save the key (C:\Users\Ryan/.ssh/id_ed25519):           ((just hit enter for this part; that makes the default directory load in your user folder))
Created directory 'C:\Users\Ryan/.ssh'.
[more text prints here that I won't show]

when prompted to create a passkey, I would just leave it blank, which means no passkey
I keep my computer locked while I'm away at all times, so it shouldn't matter

the passkey does give an extra layer of security though, so it's up to you


you created an ssh key
now you need to add it to an ssh agent

but before you can even add it to the ssh agent, you need to run it first

</pre>

# ******THIS NEXT SECTION REQUIRES ADMIN PASSWORD**
<pre>
open up an admin powershell window and enter this to start up ssh agent:
Get-Service -Name ssh-agent | Set-Service -StartupType Manual
Start-Service ssh-agent

even though there's no output, the ssh agent is now running
you only have to do this once for each ssh key, so thankfully you won't need to use admin over and over again

DO NOT CLOSE THE ADMIN POWERSHELL WINDOW

</pre>

# ******ADMIN PASSWORD SECTION ENDS HERE**


## Adding SSH Key
<pre>
now, add your ssh key:
ssh-add C:\Users\USER_HERE\.ssh\id_ed25519

log:
Identity added: C:\Users\Ryan\.ssh\id_ed25519 (ry645.dev@gmail.com)
</pre>

go back to github  

click on your profile photo (top right corner)  
[exampleImages\ex4.png](exampleImages\ex4.png)  

go to settings (ex5.png)  
[exampleImages\ex5.png](exampleImages\ex5.png)  

SSH and GPG keys (ex6.png)  
[exampleImages\ex6.png](exampleImages\ex6.png)  

New SSH key  

<pre>
make a descriptive, but brief title (for example: Ryan's Laptop)
key type is Authentication Key

go to C:\Users\USER_HERE\.ssh
open id_ed25519.pub SPECIFICALLY in a raw text editor (use notepad or vscode)
copy ALL of its contents (click, ctrl+a, ctrl+c)
****DO NOT EDIT IT
****DO NOT SAVE IT

go back to your github tab and paste it in the last text box
do not edit any part of the pasted text (i didn't, and it works perfectly for me)

then click "Add SSH Key"
</pre>
### Other Thing
<pre>
one small thing
go to your settings (ex4 and 5)
Repositories
find "Repository default branch"

change "main" to "master"

this makes it so github's default branch is the same as git's default branch
makes things easier
</pre>



## Testing Connection
<pre>
now, you'll have to test the connection
this test is required
powershell needs your approval before it can actually connect to github

type this command:
ssh -T git@github.com

log:
The authenticity of host 'github.com (140.82.112.3)' can't be established.
ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.                (for security reasons, check here to make sure this ECDSA is github's: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints)
Are you sure you want to continue connecting (yes/no/[fingerprint])?

type this:
yes

log:
Warning: Permanently added 'github.com,140.82.112.3' (ECDSA) to the list of known hosts.    (this warning is fine)
Hi Ry645! You've successfully authenticated, but GitHub does not provide shell access.      (it actually does provide shell access with an ssh key idk why it says that)

there you go!
you have successfully and completely connected to github!
</pre>

next tutorial is in [workingWithGitHubRepository.md](workingWithGitHubRepository.md)  

*********You can now close the Admin Powershell Window.
