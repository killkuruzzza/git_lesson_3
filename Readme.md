# The git initial working process

> There are description for starting workspace with git technologies

### Installing git

1. At first you may visit the `download` page

   - Check it on the Git resource [direct link](https://git-scm.com/downloads).

2. Next step lays in choosing correct installation build for your own operating system

3. After installation was successfully you must run OS bash(terminal) to the checking if git was installed correctly

   - Type command for git version checking:
		```
		git --version
		```
	
> Okay! If you see the gits' version, that's all.. 
> Git was installed. Otherwise something was broken under installation process.

### Git branching

1. Write down the command
	```
	git branch <your new branch name>
	```
2. Switch your currently branch subscription to the new branch, follow by command
	```
	git checkout <created branch>
	```
	
### Git merging

1. Use command below on main branch
	```
	git merge <merged branch>
	```
	
### Add remote origin into repository

1. For adding remote repository into your local repo usage
	```
	git remote add origin <url>
	```

### Remote branch forking

To the obtaining source copy of remote branch into your repository follow directions below

1. Go to <url> repository and press fork button on top left corner
2. Open terminal and add remote origin into your repository
3. Clone remote repository into your local copy
