## What is GIT?

It's a version control system</br>

- It records changes to files
- Used for coordinating work among a Team collaboratively
- Handles large projects efficiently
- Easy to learn
- Opensource(free)

Step One
You can download it on any operating system at:

_git-scm.com/downloads_

Step Two
Tell git who you are, it's important because every GIT commit uses this information.

```
git config ---global user.name <username>
git config --global user.email <email>
```

Step Three

```
Git init
```

This command creates a new repository

(=A repository is a central location where data is stored)

## 
Congrats you are ready to get started.

**So what's next?**

```
git clone /path/to/repository
```

This crates a working copy of a local repository.

```
git clone user@host:/repository
```

This creates a working copy of a remote repository.

```
git add <filename>
```

This states the quested file to the commit.

```
git add -A
```

Stages files are committed to your local working branch.

```
git commit -m "commit message"
```

stages files are committed to your local working branch.

```
git push origin master
```

This sends your committed files to your remote repository.

PS: Change "master" to whatever branch you want to pyour changes to.

## Have you ever used GIT, and if yes what is your experience with it.



