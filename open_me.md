## - What is Git and why is it needed?
Git is a console utility for tracking and maintaining a history of file changes in your project. Most often it is used for code, but it can be used for other files as well. For example, for pictures - useful for designers

<br>

## - How it works?
If you look at the picture, it becomes a little easier with understanding. Each circle is a commit. The arrows show the direction from which commit the next is made. For example, C3 is made from C2, etc. All these commits are in a branch called main. This is the master branch, most commonly referred to as master . The main* rectangle shows which commit we are currently in, in other words, a pointer.

<br>

<br>

![Picture1](https://habrastorage.org/getpro/habr/upload_files/81d/ab6/de0/81dab6de02b4179fc1bc8c119dfce9ca)

<br>

<br>

The result is a very simple graph consisting of one branch (main) and four commits. All this can turn into a more complex graph, consisting of several branches that merge into one

<br>

<br>

![Picture2](https://habrastorage.org/getpro/habr/upload_files/137/e03/4ea/137e034eadd3c4459a734354a029fb1a)

<br>

<br>

## - Setting
You have Git installed and you can use it. Let's now set it up so that when you create a commit, the author is indicated who created it.

Open a terminal (Linux and MacOS) or console (Windows) and enter the following commands.

<br>

     Set a name for your user
     #Instead of <your_name> you can enter, for example, Grisha_Popov
     #We leave quotes
     git config --global user.name "<your_name>"
<br>

     #Now set email. The principle is the same.
     git config --global user.email "<email_address@email.com>"

<br>

<br>

     #Now creating a commit. Be sure to specify a comment.
     #And don't forget about the quotes
      git commit -m "<comment>"
<br>

Fine. You created your first repository and filled it with the first commit.
<br>

<br>

## - Creating a repository
Now you are ready to work with Git locally on your computer.

Let's create our first repository. To do this, go to your project folder.

     #For Linux and macOS, the path may look like this /Users/UserName/Desktop/MyProject
     #For Windows, for example with://MyProject
     cd <path to your_project>

     #Initializing/creating a repository
     git init

<br>
Git now tracks changes to your project's files. But, since you just created the repository, your code is not in it. To do this, you need to create a commit.

<br>

     #We will add all the project files to our future commit
     git add .
     # Or so
     git add --all

     #If we want to add a specific file, we can do this
     git add <file_name> 

     ## - The process of working with Git
It is not necessary to commit after each file change. Most often they are created when:

* New functionality has been created
* Added a new block on the layout
* Fixed code errors
* You have completed the working day and want to save the code

This will help keep your branches clean and tidy. Thus, you will see the history of changes for each innovation in your project, and not for each file.

<br>

## - Collaboration
Let's imagine that you and your friends have come up with a project with "blackjack" and ... You have shared responsibilities. Someone will do authorization and registration, and someone will do the news output functionality. To do this, you will need branching.

![Picture3](https://habrastorage.org/r/w1560/getpro/habr/upload_files/753/f85/4b2/753f854b2ca82a2a5112e9717d1a5856.png)

A branch is a set of commits (circles) that follow each other. The branch has a name, the main branch is most often called master (in the pictures it will be called main). In simple terms, the master branch is our project.

Other branches are a separate place for implementing new functionality or fixing bugs (errors) of our project. That is, with a separate branch, you do whatever you want, and then merge these changes into the main master branch.

? I do not recommend creating commit directly in master. It is better to start a new branch for this and write all the changes there.

<br>
In order to create a new branch, enter:

     git branch <branch name>
     #or like this
     git checkout -b <branch name>
    
![Picture3](https://habrastorage.org/r/w1560/getpro/habr/upload_files/2c3/0a1/699/2c30a16996c18d3c2496bb6bde28cc90.png)

These commands do the same thing, only the second option allows you to immediately switch to a new branch. You can make changes to a new branch immediately after it is created.

When creating a new branch, try to call it by a short and succinct name. So that it is immediately clear what exactly was changed by the project. If you use some kind of task management system, you can specify the task ID at the beginning of the branch name so that you can easily find out which task the branch was created on. For example like this:

     3424_fix_catalog_ajax

In each new commit, you should leave a comment and describe the essence of the changes in it.

You can switch between branches with this command:

     git checkout <branch name>

After you have finished working on your task, the branch can be merged into master. To do this, switch to the master branch and run the following command:

     # Switch to master
     git checkout master
     # Updating the local branch from the server
     git pull origin master
     
     # Doing a merge of your branch into the branch you are in
     # In this example it is master
     git merge <branch name>

![Picture3](https://habrastorage.org/r/w1560/getpro/habr/upload_files/574/bb2/a87/574bb2a8719a01dad2f63e803f550a66.png)

❗️ Before merging a new merge, it is worth updating the local master branch, in order to avoid further problems.

The merge command takes all the changes from the branch (for example bugFix) and adds them to the master branch.

In order to see the current state of the branch, for example, which files were added or not added to create commit, you can run the command:

     git status
Other users will not see your branch until it is sent to a remote repository. Therefore, after you have merged all the changes to master, you need to send them to GitHub. To do this, you must be in the master branch :

     git checkout master
     # send our changes to GitHub
     git push origin master

Now all your changes in the master branch have flown to GitHub. In the same way, you can send any other branch:

     git checkout <branch name>
     git push origin <branch name>

? The Council. It is better to upload each commit directly to the remote repository. No one is insured against the breakdown of their own PC. Therefore, in order not to lose all the developments, do not forget to merge your changes on GitHub.

<br>

<br>

# -Basic Branching and Merging

Let’s go through a simple example of branching and merging with a workflow that you might use in the real world. You’ll follow these steps:

1. Do some work on a website.
2. Create a branch for a new user story you’re working on.
3. Do some work in that branch.

At this stage, you’ll receive a call that another issue is critical and you need a hotfix. You’ll do the following:

1. Switch to your production branch.
2. Create a branch to add the hotfix.
3. After it’s tested, merge the hotfix branch, and push to production.

Switch back to your original user story and continue working.

<br>

## -Basic Branching

First, let’s say you’re working on your project and have a couple of commits already on the master branch.

![Picture4](https://git-scm.com/book/en/v2/images/basic-branching-1.png)

You’ve decided that you’re going to work on issue #53 in whatever issue-tracking system your company uses. To create a new branch and switch to it at the same time, you can run the git checkout command with the -b switch:

     $ git checkout -b iss53

Switched to a new branch "iss53"
This is shorthand for:

     $ git branch iss53
     $ git checkout iss53

![Picture5](https://git-scm.com/book/en/v2/images/basic-branching-2.png) 

You work on your website and do some commits. Doing so moves the iss53 branch forward, because you have it checked out (that is, your HEAD is pointing to it):

     $ vim index.html
     $ git commit -a -m 'Create new footer [issue 53]'

![Picture5](https://git-scm.com/book/en/v2/images/basic-branching-3.png) 

Now you get the call that there is an issue with the website, and you need to fix it immediately. With Git, you don’t have to deploy your fix along with the iss53 changes you’ve made, and you don’t have to put a lot of effort into reverting those changes before you can work on applying your fix to what is in production. All you have to do is switch back to your master branch.

However, before you do that, note that if your working directory or staging area has uncommitted changes that conflict with the branch you’re checking out, Git won’t let you switch branches. It’s best to have a clean working state when you switch branches. There are ways to get around this (namely, stashing and commit amending) that we’ll cover later on, in Stashing and Cleaning. For now, let’s assume you’ve committed all your changes, so you can switch back to your master branch:

     $ git checkout master
     Switched to branch 'master'

At this point, your project working directory is exactly the way it was before you started working on issue #53, and you can concentrate on your hotfix. This is an important point to remember: when you switch branches, Git resets your working directory to look like it did the last time you committed on that branch. It adds, removes, and modifies files automatically to make sure your working copy is what the branch looked like on your last commit to it.

Next, you have a hotfix to make. Let’s create a hotfix branch on which to work until it’s completed:

     $ git checkout -b hotfix
     Switched to a new branch 'hotfix'
     $ vim index.html
     $ git commit -a -m 'Fix broken email address'\[hotfix 1fb7853] Fix broken email address
     1 file changed, 2 insertions(+)

![Picture6](https://git-scm.com/book/en/v2/images/basic-branching-4.png) 

You can run your tests, make sure the hotfix is what you want, and finally merge the hotfix branch back into your master branch to deploy to production. You do this with the git merge command:

     $ git checkout master
     $ git merge hotfix
     Updating f42c576..3a0874c
     Fast-forward
      index.html | 2 ++
      1 file changed, 2 insertions(+)

You’ll notice the phrase “fast-forward” in that merge. Because the commit C4 pointed to by the branch hotfix you merged in was directly ahead of the commit C2 you’re on, Git simply moves the pointer forward. To phrase that another way, when you try to merge one commit with a commit that can be reached by following the first commit’s history, Git simplifies things by moving the pointer forward because there is no divergent work to merge together — this is called a “fast-forward.”

Your change is now in the snapshot of the commit pointed to by the master branch, and you can deploy the fix.

![Picture7](https://git-scm.com/book/en/v2/images/basic-branching-5.png) 

After your super-important fix is deployed, you’re ready to switch back to the work you were doing before you were interrupted. However, first you’ll delete the hotfix branch, because you no longer need it — the master branch points at the same place. You can delete it with the -d option to git branch:

     $ git branch -d hotfix
     Deleted branch hotfix (3a0874c).

Now you can switch back to your work-in-progress branch on issue #53 and continue working on it.

     $ git checkout iss53
     Switched to branch "iss53"
     $ vim index.html
     $ git commit -a -m 'Finish the new footer [issue 53]'
     [iss53 ad82d7a] Finish the new footer [issue 53]1 file changed, 1 insertion(+)

![Picture8](https://git-scm.com/book/en/v2/images/basic-branching-6.png) 

It’s worth noting here that the work you did in your hotfix branch is not contained in the files in your iss53 branch. If you need to pull it in, you can merge your master branch into your iss53 branch by running git merge master, or you can wait to integrate those changes until you decide to pull the iss53 branch back into master later.

<br>

## -Basic Merging

Suppose you’ve decided that your issue #53 work is complete and ready to be merged into your master branch. In order to do that, you’ll merge your iss53 branch into master, much like you merged your hotfix branch earlier. All you have to do is check out the branch you wish to merge into and then run the git merge command:

     $ git checkout master
     Switched to branch 'master'
     $ git merge iss53
     Merge made by the 'recursive' strategy.
     index.html |    1 +
     1 file changed, 1 insertion(+)

This looks a bit different than the hotfix merge you did earlier. In this case, your development history has diverged from some older point. Because the commit on the branch you’re on isn’t a direct ancestor of the branch you’re merging in, Git has to do some work. In this case, Git does a simple three-way merge, using the two snapshots pointed to by the branch tips and the common ancestor of the two.

![Picture9](https://git-scm.com/book/en/v2/images/basic-branching-7.png) 

Instead of just moving the branch pointer forward, Git creates a new snapshot that results from this three-way merge and automatically creates a new commit that points to it. This is referred to as a merge commit, and is special in that it has more than one parent.

![Picture9](https://git-scm.com/book/en/v2/images/basic-branching-8.png) 

Now that your work is merged in, you have no further need for the iss53 branch. You can close the issue in your issue-tracking system, and delete the branch:

     $ git branch -d iss53

<br>
<br>

## -Basic Merge Conflicts

Occasionally, this process doesn’t go smoothly. If you changed the same part of the same file differently in the two branches you’re merging, Git won’t be able to merge them cleanly. If your fix for issue #53 modified the same part of a file as the hotfix branch, you’ll get a merge conflict that looks something like this:

     $ git merge iss53
     Auto-merging index.html
     CONFLICT (content): Merge conflict in index.html
     Automatic merge failed; fix conflicts and then commit the result.

Git hasn’t automatically created a new merge commit. It has paused the process while you resolve the conflict. If you want to see which files are unmerged at any point after a merge conflict, you can run git status:

  $ git status
  On branch master
  You have unmerged paths.
    (fix conflicts and run "git commit")

  Unmerged paths:
    (use "git add <file>..." to mark resolution)

      both modified:      index.html

  no changes added to commit (use "git add" and/or "git commit -a")
  
Anything that has merge conflicts and hasn’t been resolved is listed as unmerged. Git adds standard conflict-resolution markers to the files that have conflicts, so you can open them manually and resolve those conflicts. Your file contains a section that looks something like this:

     <<<<<<< HEAD:index.html
     <div id="footer">contact : email.support@github.com</div>
     =======
     <div id="footer">
      please contact us at support@github.com
     </div>
     >>>>>>> iss53:index.html

This means the version in HEAD (your master branch, because that was what you had checked out when you ran your merge command) is the top part of that block (everything above the =======), while the version in your iss53 branch looks like everything in the bottom part. In order to resolve the conflict, you have to either choose one side or the other or merge the contents yourself. For instance, you might resolve this conflict by replacing the entire block with this:

     <div id="footer">
     please contact us at email.support@github.com
     </div>

This resolution has a little of each section, and the <<<<<<<, =======, and >>>>>>> lines have been completely removed. After you’ve resolved each of these sections in each conflicted file, run git add on each file to mark it as resolved. Staging the file marks it as resolved in Git.

If you want to use a graphical tool to resolve these issues, you can run git mergetool, which fires up an appropriate visual merge tool and walks you through the conflicts:

     $ git mergetool
    
     This message is displayed because 'merge.tool' is not configured.
     See 'git mergetool --tool-help' or 'git help config' for more details.
     'git mergetool' will now attempt to use one of the following tools:
     opendiff kdiff3 tkdiff xxdiff meld tortoisemerge gvimdiff diffuse diffmerge ecmerge p4merge araxis bc3 codecompare vimdiff emerge
     Merging:
     index.html
     
     Normal merge conflict for 'index.html':
      {local}: modified file
      {remote}: modified file
      Hit return to start merge resolution tool (opendiff):
      
If you want to use a merge tool other than the default (Git chose opendiff in this case because the command was run on macOS), you can see all the supported tools listed at the top after “one of the following tools.” Just type the name of the tool you’d rather use.

<br>

<br>

### -Note
 If you need more advanced tools for resolving tricky merge conflicts, we cover more on merging in Advanced Merging.

After you exit the merge tool, Git asks you if the merge was successful. If you tell the script that it was, it stages the file to mark it as resolved for you. You can run git status again to verify that all conflicts have been resolved:

     $ git status
     On branch master
     All conflicts fixed but you are still merging.
      (use "git commit" to conclude merge)

     Changes to be committed:
        modified:   index.html

If you’re happy with that, and you verify that everything that had conflicts has been staged, you can type git commit to finalize the merge commit. The commit message by default looks something like this:

   Merge branch 'iss53'
   
   Conflicts:
    index.html
   .#
   .# It looks like you may be committing a merge.
   .# If this is not correct, please remove the file
   .#	.git/MERGE_HEAD
   .# and try again.
   
   .# Please enter the commit message for your changes. Lines starting
   .# with '#' will be ignored, and an empty message aborts the commit.
   .# On branch master
   .# All conflicts fixed but you are still merging.
   .#
   .# Changes to be committed:
   .#	modified:   index.html
   .#

If you think it would be helpful to others looking at this merge in the future, you can modify this commit message with details about how you resolved the merge and explain why you did the changes you made if these are not obvious.

//  LECTION NUMBER 3 
# - Working with Remotes

To be able to collaborate on any Git project, you need to know how to manage your remote repositories. Remote repositories are versions of your project that are hosted on the Internet or network somewhere. You can have several of them, each of which generally is either read-only or read/write for you. Collaborating with others involves managing these remote repositories and pushing and pulling data to and from them when you need to share work. Managing remote repositories includes knowing how to add remote repositories, remove remotes that are no longer valid, manage various remote branches and define them as being tracked or not, and more. In this section, we’ll cover some of these remote-management skills.

## - Showing Your Remotes

To see which remote servers you have configured, you can run the git remote command. It lists the shortnames of each remote handle you’ve specified. If you’ve cloned your repository, you should at least see origin — that is the default name Git gives to the server you cloned from:

     $ git clone https://github.com/schacon/ticgit
     Cloning into 'ticgit'...
     remote: Reusing existing pack: 1857, done.
     remote: Total 1857 (delta 0), reused 0 (delta 0)
     Receiving objects: 100% (1857/1857), 374.35 KiB | 268.00 KiB/s, done.
     Resolving deltas: 100% (772/772), done.
     Checking connectivity... done.
     $ cd ticgit
     $ git remote
     origin

You can also specify -v, which shows you the URLs that Git has stored for the shortname to be used when reading and writing to that remote:

     $ git remote -v
     origin	https://github.com/schacon/ticgit (fetch)
     origin	https://github.com/schacon/ticgit (push)

If you have more than one remote, the command lists them all. For example, a repository with multiple remotes for working with several collaborators might look something like this.

     $ cd grit
     $ git remote -v
     bakkdoor  https://github.com/bakkdoor/grit (fetch)
     bakkdoor  https://github.com/bakkdoor/grit (push)
     cho45     https://github.com/cho45/grit (fetch)
     cho45     https://github.com/cho45/grit (push)
     defunkt   https://github.com/defunkt/grit (fetch)
     defunkt   https://github.com/defunkt/grit (push)
     koke      git://github.com/koke/grit.git (fetch)
     koke      git://github.com/koke/grit.git (push)
     origin    git@github.com:mojombo/grit.git (fetch)
     origin    git@github.com:mojombo/grit.git (push)

This means we can pull contributions from any of these users pretty easily. We may additionally have permission to push to one or more of these, though we can’t tell that here.

## -Adding Remote Repositories

We’ve mentioned and given some demonstrations of how the git clone command implicitly adds the origin remote for you. Here’s how to add a new remote explicitly. To add a new remote Git repository as a shortname you can reference easily, run git remote add <shortname> <url>:

     $ git remote
     origin
     $ git remote add pb https://github.com/paulboone/ticgit
     $ git remote -v
     origin	https://github.com/schacon/ticgit (fetch)
     origin	https://github.com/schacon/ticgit (push)
     pb	https://github.com/paulboone/ticgit (fetch)
     pb	https://github.com/paulboone/ticgit (push)

Now you can use the string pb on the command line in lieu of the whole URL. For example, if you want to fetch all the information that Paul has but that you don’t yet have in your repository, you can run git fetch pb:

     $ git fetch pb
     remote: Counting objects: 43, done.
     remote: Compressing objects: 100% (36/36), done.
     remote: Total 43 (delta 10), reused 31 (delta 5)
     Unpacking objects: 100% (43/43), done.
     From https://github.com/paulboone/ticgit
     * [new branch]      master     -> pb/master
     * [new branch]      ticgit     -> pb/ticgit

Paul’s master branch is now accessible locally as pb/master — you can merge it into one of your branches, or you can check out a local branch at that point if you want to inspect it.

<br>

## -Fetching and Pulling from Your Remotes

As you just saw, to get data from your remote projects, you can run:

     $ git fetch <remote>

The command goes out to that remote project and pulls down all the data from that remote project that you don’t have yet. After you do this, you should have references to all the branches from that remote, which you can merge in or inspect at any time.

If you clone a repository, the command automatically adds that remote repository under the name “origin”. So, git fetch origin fetches any new work that has been pushed to that server since you cloned (or last fetched from) it. It’s important to note that the git fetch command only downloads the data to your local repository — it doesn’t automatically merge it with any of your work or modify what you’re currently working on. You have to merge it manually into your work when you’re ready.

If your current branch is set up to track a remote branch (see the next section and Git Branching for more information), you can use the git pull command to automatically fetch and then merge that remote branch into your current branch. This may be an easier or more comfortable workflow for you; and by default, the git clone command automatically sets up your local master branch to track the remote master branch (or whatever the default branch is called) on the server you cloned from. Running git pull generally fetches data from the server you originally cloned from and automatically tries to merge it into the code you’re currently working on.

### -Note
    From Git version 2.27 onward, git pull will give a warning if the pull.rebase variable is not set. Git will keep warning you until you set the variable.
    
    If you want the default behavior of Git (fast-forward if possible, else create a merge commit): git config --global pull.rebase "false"
    
    If you want to rebase when pulling:
     git config --global pull.rebase "true"
<br>

<br>

## -Pushing to Your Remotes

When you have your project at a point that you want to share, you have to push it upstream. The command for this is simple: git push <remote> <branch>. If you want to push your master branch to your origin server (again, cloning generally sets up both of those names for you automatically), then you can run this to push any commits you’ve done back up to the server:

     $ git push origin master

This command works only if you cloned from a server to which you have write access and if nobody has pushed in the meantime. If you and someone else clone at the same time and they push upstream and then you push upstream, your push will rightly be rejected. You’ll have to fetch their work first and incorporate it into yours before you’ll be allowed to push. See Git Branching for more detailed information on how to push to remote servers.
<br>

<br>

## -Inspecting a Remote

If you want to see more information about a particular remote, you can use the git remote show <remote> command. If you run this command with a particular shortname, such as origin, you get something like this:

     $ git remote show origin
     * remote origin
       Fetch URL: https://github.com/schacon/ticgit
       Push  URL: https://github.com/schacon/ticgit  HEAD branch: master
       Remote branches:
         master                               tracked
         dev-branch                           tracked
       Local branch configured for 'git pull':
         master merges with remote master
       Local ref configured for 'git push':
         master pushes to master (up to date)

It lists the URL for the remote repository as well as the tracking branch information. The command helpfully tells you that if you’re on the master branch and you run git pull, it will automatically merge the remote’s master branch into the local one after it has been fetched. It also lists all the remote references it has pulled down.

That is a simple example you’re likely to encounter. When you’re using Git more heavily, however, you may see much more information from git remote show:

     $ git remote show origin
     * remote origin
     URL: https://github.com/my-org/complex-project
     Fetch URL: https://github.com/my-org/complex-project
     Push  URL: https://github.com/my-org/complex-project
     HEAD branch: master
     Remote branches:
       master                           tracked
       dev-branch                       tracked
       markdown-strip                   tracked
       issue-43                         new (next fetch will store in remotes/origin)
       issue-45                         new (next fetch will store in remotes/origin)
       refs/remotes/origin/issue-11     stale (use 'git remote prune' to remove)
       Local branches configured for 'git pull':
       dev-branch merges with remote dev-branch
       master     merges with remote master
     Local refs configured for 'git push':
       dev-branch                     pushes to dev-branch                     (up to date)
       markdown-strip                 pushes to markdown-strip                 (up to date)
       master                         pushes to master                         (up to date)

This command shows which branch is automatically pushed to when you run git push while on certain branches. It also shows you which remote branches on the server you don’t yet have, which remote branches you have that have been removed from the server, and multiple local branches that are able to merge automatically with their remote-tracking branch when you run git pull.
<br>

<br>

## -Renaming and Removing Remotes

You can run git remote rename to change a remote’s shortname. For instance, if you want to rename pb to paul, you can do so with git remote rename:

     $ git remote rename pb paul
     $ git remote
     origin
     paul

It’s worth mentioning that this changes all your remote-tracking branch names, too. What used to be referenced at pb/master is now at paul/master.

If you want to remove a remote for some reason — you’ve moved the server or are no longer using a particular mirror, or perhaps a contributor isn’t contributing anymore — you can either use git remote remove or git remote rm:

     $ git remote remove paul
     $ git remote
     origin

Once you delete the reference to a remote this way, all remote-tracking branches and configuration settings associated with that remote are also deleted.


It was full instruction for beginners. Bye!