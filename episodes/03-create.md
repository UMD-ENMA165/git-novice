---
title: Creating a Repository
teaching: 10
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- Create a local Git repository.
- Describe the purpose of the `.git` directory.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- Where does Git store information?

::::::::::::::::::::::::::::::::::::::::::::::::::

Once Git is configured,
we can start using it.

We will help Alfredo with his new project, create a repository with all his recipes.

First, let's create a new directory in the `Desktop` folder for our work and then change the current working directory to the newly created one:
![[Screen Shot 2025-02-01 at 8.21.18 PM.png]]
![[Pasted image 20250201202611.png]]
![[Pasted image 20250201202627.png]]
![[Pasted image 20250201202659.png]]
Then we tell Git to make `recipes` a [repository](../learners/reference.md#repository)
\-- a place where Git can store versions of our files:
### New > Create Local Repository
![[Pasted image 20250201204725.png]]

![[Pasted image 20250201203957.png]]
:::::::::::::::::::::::::::::::::::::::::  callout
## Drag and Drop

It is also possible to create a local repository by dragging and dropping the `recipes` folder from the `Desktop` folder onto the [Bookmarks window](https://confluence.atlassian.com/get-started-with-sourcetree/bookmarks-window-847359137.html) in Sourcetree.

![[Pasted image 20250201203227.png]]
::::::::::::::::::::::::::::::::::::::::::::::::::

In the **Create a local repository** dialog, check that the **Destination Path** is correct and that the **Name** is `recipes`.
![[Pasted image 20250201203554.png]]
If **Also create remote repository** is not grayed out, do not select it at this time.

if the **Destination Path** does not already describe your `recipes/` directory, click the ellipsis (**`...`**) button and use the file browser to navigate into and select it.
![[Pasted image 20250202060358.png]]

If a dialog reports that the destination path already exists, click **Yes** to continue and create a repository in this folder.
![[Pasted image 20250202063348.png]]

You should see new `recipes` bookmark [Bookmarks window](https://confluence.atlassian.com/get-started-with-sourcetree/bookmarks-window-847359137.html).
![[Pasted image 20250201203640.png]]
It is important to note that **Create Local Repository** will create a repository that
can include subdirectories and their files---there is no need to create
separate repositories nested within the `recipes` repository, whether
subdirectories are present from the beginning or added later. Also, note
that the creation of the `recipes` directory and its initialization as a
repository are completely separate processes.

If we return to the file manager (Finder, Windows File Explorer, KDE Desktop, ...) to show the directory's contents,
it appears that nothing has changed:
![[Pasted image 20250202061308.png]]
If we show hidden files (in macOS Finder, press **Command+Shift+period** (using the "`.`" key);  in Windows File Explorer, select **View > Hidden Items**) we can see that Git has created a hidden directory within `recipes` called `.git`:

![[{C81044EF-DCC1-4A64-A416-FF80EB1578FF}.png]]

Git uses this special subdirectory to store all the information about the project,
including the tracked files and sub-directories located within the project's directory.
If we ever delete the `.git` subdirectory,
we will lose the project's history.

Return to Sourcetree and double-click the `recipes` bookmark in the [Bookmarks window](https://confluence.atlassian.com/get-started-with-sourcetree/bookmarks-window-847359137.html). A window will open displaying information about the `recipes` repository.

We can now start using one of the most important Sourcetree representations of a Git repository, which is particularly helpful to beginners. Select **File status** from the [Sidebar](https://confluence.atlassian.com/get-started-with-sourcetree/sidebar-847359144.html). **File status** tells us the status of our project, and better, a list of changes in the project and options on what to do with those changes. We can view it as often as we want, whenever we want to understand what is going on.
![[Pasted image 20250201203713.png]]
In the middle of the window, you should see the message "Nothing to commit".

:::::::::::::::::::::::::::::::::::::::  challenge

## Places to Create Git Repositories

Along with tracking information about recipes (the project we have already created),
Alfredo would also like to track information about desserts specifically.
Alfredo creates a `desserts` project inside his `recipes`
project with the following sequence of actions:

- navigate to the `Desktop` directory using the file manager
- open the `recipes` directory, which is already a Git repository
- show hidden files to ensure the `.git` subdirectory is still present in the `recipes` directory
- make a sub-directory `recipes/desserts`
- use Sourcetree to **Create Local Repository** for the `desserts` subdirectory
- open the `desserts` subdirectory in the file manager
- show hidden files to ensure the `.git` subdirectory is present indicating we have created a new Git repository

Is **Create Local Repository**, run inside the `desserts` subdirectory, required for
tracking files stored in the `desserts` subdirectory?

:::::::::::::::  solution

## Solution

No. Alfredo does not need to make the `desserts` subdirectory a Git repository
because the `recipes` repository will track all files, sub-directories, and
subdirectory files under the `recipes` directory.  Thus, in order to track
all information about desserts, Alfredo only needed to add the `desserts` subdirectory
to the `recipes` directory.

Additionally, Git repositories can interfere with each other if they are "nested":
the outer repository will try to version-control
the inner repository. Therefore, it's best to create each new Git
repository in a separate directory.

:::::::::::::::::::::::::

## Correcting **Create Local Repository** Mistakes

Jimmy explains to Alfredo how a nested repository is redundant and may cause confusion
down the road. Alfredo would like to go back to a single git repository. How can Alfredo undo
his last **Create Local Repository** in the `desserts` subdirectory?

:::::::::::::::  solution

## Solution -- USE WITH CAUTION!

### Background

Removing files from a Git repository needs to be done with caution. But we have not learned
yet how to tell Git to track a particular file; we will learn this in the next episode. Files
that are not tracked by Git can easily be removed like any other "ordinary" files by moving them to the **Trash** or **Recycle Bin** using the file manager.

If the files or folder being removed in this fashion are tracked by Git, then their removal
becomes another change that we will need to track, as we will see in the next episode.

### Solution

Git keeps all of its files in the `.git` directory.
To recover from this little mistake, Alfredo can remove the `.git`
folder in the `desserts` subdirectory by moving `desserts/.git` to the **Trash**/**Recycle Bin**.

But be careful! Removing the `.git` directory from the wrong directory will remove
the entire Git history of a project you might want to keep. While items can be retrieved from the **Trash**/**Recycle Bin**, at least until it is emptied, in general the `.git` directory should be left alone.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- **Create Local Repository** initializes a repository.
- Git stores all of its repository data in the `.git` directory.

::::::::::::::::::::::::::::::::::::::::::::::::::
