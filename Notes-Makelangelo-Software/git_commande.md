
# Basic 

(fr) https://www.atlassian.com/fr/git/tutorials/undoing-changes/git-reset

(en) https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/

```
export AUserEmailForGit=...@....com
export AUserNameForGit=... 
```

```
git config --global user.name "$AUserNameForGit"
git config --global user.email "$AUserEmailForGit"
```

```
git config --global --list
```
## Certificat pour utiliser ssh

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account


```
ls -al ~/.ssh
```

```
drwx------  2 q6 q6 4096 janv. 25  2021 .
drwxr-xr-x 68 q6 q6 4096 nov.  25 00:08 ..
-rw-------  1 q6 q6  888 mai    3  2021 known_hosts
-rw-------  1 q6 q6  444 mars  29  2019 known_hosts.old
```

```
ssh-keygen -t ed25519 -C "$AUserEmailForGit"
```


```
enerating public/private ed25519 key pair.
Enter file in which to save the key (/home/q6/.ssh/id_ed25519): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/q6/.ssh/id_ed25519.
Your public key has been saved in /home/q6/.ssh/id_ed25519.pub.
The key fingerprint is:
SHA256:...
The key's randomart image is:
...
```


```
eval "$(ssh-agent -s)"
```

```
Agent pid 5357
```
```
ssh-add ~/.ssh/id_ed25519
```
```
Enter passphrase for /home/q6/.ssh/id_ed25519: 
Identity added: /home/q6/.ssh/id_ed25519 (...)
```



## Creer un depot local ou distant
### …or create a new repository on the command line
```
echo "# Impressions-3D-Notes-en-vrac" >> README.md
git init 
git add README.md
git commit -m "first commit"
git branch -M main
```
```
git remote add origin git@github.com:PPAC37/Impressions-3D-Notes-en-vrac.git
git push -u origin main
```
## Cloner un depot distant
```
export localParentDir=.
export depotUrl=https://github.com/PPAC37/ELEGOO-Jupiter.git
mkdir $localParentDir
cd $localParentDir
git clone $depotUrl
```

```
git status
git add .
git status
git commit -m "First commit"
```

## Uncommit Changes you just made to your Git Repo
### Remove the most recent commit# Commit again!
```
git reset HEAD~1
```

## Add a remote origin and Push:

### sets the new remote
```
git remote add origin remote_repository_URL
```
### List the remote connections you have to other repositories.
```
git remote -v
```

```
git push
```
```
git push -u origin master # pushes changes to origin
```

## récupérer une branche d'un autre depost (fork) d'un autre
https://stackoverflow.com/questions/9153598/how-do-i-fetch-a-branch-on-someone-elses-fork-on-github
```
git remote add theirusername git@github.com:theirusername/reponame.git
git fetch theirusername
git checkout -b mynamefortheirbranch theirusername/theirbranch
```

## Usage de la commande git
```
git
```
```
usage : git remote [-v | --verbose]
   ou : git remote add [-t <branche>] [-m <master>] [-f] [--tags | --no-tags] [--mirror=<fetch|push>] <nom> <url>
   ou : git remote rename <ancienne> <nouvelle>
   ou : git remote remove <nom>
   ou : git remote set-head <nom> (-a | --auto | -d | --delete | <branche>)
   ou : git remote [-v | --verbose] show [-n] <nom>
   ou : git remote prune [-n | --dry-run] <nom>
   ou : git remote [-v | --verbose] update [-p | --prune] [(<groupe> | <distante>)...]
   ou : git remote set-branches [--add] <nom> <branche>...
   ou : git remote get-url [--push] [--all] <nom>
   ou : git remote set-url [--push] <nom> <nouvelle-URL> [<ancienne-URL>]
   ou : git remote set-url --add <nom> <nouvelle-URL>
   ou : git remote set-url --delete <nom> <url>

    -v, --verbose         être verbeux : doit être placé avant une sous-commande
```
