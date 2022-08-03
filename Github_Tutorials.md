# Github Tutorials

## Introduction

This tutorial uses Github as example for the code sharing platform, but the main concept and tools are available in other Git platforms such as GitLab or Bitbucket. 

Github, like other hosting platform for software development and version control, uses Git as its primary version control and source code management tool. 

## Git, and Related Graphical User Interfaces

**Git** is the primary tool that handles all the version control. It is often being distributed as a standard tool in Linux distributions. However, it uses command-line interface (CLI) and is not easily navigated by fresh users. Often time, users will use 3rd-party tool such as [GitKraken](https://www.gitkraken.com/), [SmartGit](https://www.syntevo.com/smartgit/), or other graphical user interfaces (GUI) to help them manage git commands and utilities. 

- *NOTE*: [Github Desktop](https://desktop.github.com/) is a tool develop by GitHub to be used with Github. It is a very basic GUI tool that does its job, but other 3rd-party tool will have better utilities and easier to migrate to other Git platform such as GitLab or Bitbucket in the future if needed. It is also only available for Windows and MacOS.

For the most part, most users do not need to install git directly on their own, as it will be installed along with the above mentioned 3rd-party tool. In this tutorial, I may use GitKraken as screenshot example but the concept is the same for all 3rd-party tools.

## Repository

All codes are organized among Repositories. A repository is essentially a standalone project directory that host all source codes, documentations, and resources required to ensure a certain software works. 

In Fixel Institute Organization, repositories can be Public or Private. 
- A public repository (such as this [Tutorial](https://github.com/Fixel-Institute/Tutorials) page) is open to public in which everyone with link to your repository can view and download contents available on the repository. 
- A private repository is considered as internal projects not yet released to the public. Only members of the Fixel Institute organization have access to the repository. 

<mark>As of Aug 2022, all members of Fixel Institute will have base permission of **Read/Write** in all repositories.</mark>

### Branches

Within repository, there can be multiple version of the same project, and they are called Branches. 

Below is an example of how branches are viewed through GitHub website. In top left of the Repository Code window, there is a dropdown menu that you can click to view available branches in this repository. 
![Example for Branches](/images/Github_Tutorials/Branches.png "Example for Branches")

By default, all repositories created in Fixel-Institute will have a default branch called "**main**", but it is highly recommended to create additional branches for each repository. 

A standard is to keep the *default* branch as the latest stable software version (not neccessarily 100% BUG-free but at least 100% functional and perform all intended functions properly). Keep a secondary branch called "**development**", where active modifications and commits are being done on a daily-basis. 

Everyone working on the repository should only pull/commit on the *development* branch until new features are being tested out and is considered 100% functional. Then the current *development* branch should be renamed to a release version number (as the picture example, 0.1.0 or however you number your software) and is considered as a "**stable**" branch. After that, create a new branch from the *branch* branch and call that the new "**development**" branch.

- You can access "branch overview" via "View all branches" in GitHub Web Interface. 

- In Overview, click top right "New branch" for creating new branch.

![Interface for New Branch](/images/Github_Tutorials/NewBranch.png "Interface for New Branch")

- In configuration for new branch, set the Branch source as latest stable branch, and Branch name should be "development".

![Configure for New Branch](/images/Github_Tutorials/ConfigureNewBranch.png "Configure for New Branch")

- In Setting tab of Github Web Interface, user owner of the repository can set default branch to another branch if a new "stable" release branch is available.

![Set Default Branch](/images/Github_Tutorials/SetDefaultBranch.png "Set Default Branch")

- In 3rd-party tool, make sure you "**checkout**" the right branch when starting the development so you can make modifications on developmental files and not the stable release version. In GitKraken, all Branches in GitHub are listed in the "Remote" section, you may right-click the desire branch (*development*) and select "checkout origin/development" to retrieve the *development* branch. Then locally you can swich between main branch and development branch via the toggle in "Local" tab. 

![Set Default Branch](/images/Github_Tutorials/GitKrakenCheckout.png "Set Default Branch")


### Add, Commit, Push, Pull, and Merge Conflicts

This section will go over the most common activity you do with Github repository, such as Add, Commit, Push, and Pull. 

When you clone the development repository to a local folder, and checked out the correct branch, you can see all files inside folder. Now, you can make modifications on files such as adding functions, changing functions, or however you see fit. 

When changes are made, **Git** program will automatically compute a **diff** function on the file and the last stored version of the file. Often time, you will see the 3rd-party tool will tell you if any new files are created (Green), deleted (Red), or changed (orange). 

![Git Commit Interface](/images/Github_Tutorials/GitCommitInterface.png "Git Commit Interface")

<mark>Add (or Stash)</mark> will include files selected into commit list. This is to tell Git which files (or portion of the files, if the 3rd-party tool support chunk commit) should be updated in the version control system. This is useful when you made modifications to multiple file but only some of them will be updated while others will remain in development until you are ready to share with the group. 

Once selected, the user can enter a commit message and <mark>commit</mark> the files to the Git versioning system. This message essentially tell user what major change you made. This is helpful to revert commit back to previous time-point and you want to figure out which commit broke the software. 

Once commited, you must <mark>push</mark> your commits to the server (GitHub) so that your changes are shared with others on GitHub repository. Otherwise the changes will only live in your local hard-drive. 

For other users, they can <mark>pull</mark> your changes to their local disk if new commits are made. 

One important thing to note is that while you are making edits, others may be editing the file as well. If someone else commit a change and push to the server before you do, and now you are trying to commit the same changes, there could a **conflict** in commits. In scenario like this, you must perform **merge conflict** action to resolve them, such as to select what part of the file should be kept and what should be removed when conflicts are found. 

TODO: We must develop a standard conflict resolving procedure internally in Fixel Institute. 

One last note is that, in my opinion, users should commit often in development branch (with precise description on commits) and pull/push often to avoid extensive conflict resolving process. This is unless if you know for sure your codes have BUG that still need resolving. 