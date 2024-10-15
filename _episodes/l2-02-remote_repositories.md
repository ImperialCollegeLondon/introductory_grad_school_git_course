---
title: "Remote repositories"
teaching: 15
exercises: 20
questions:
- "Is my local repository the same as the remote one?"
- "How can I send my local changes to the remote one?"
- "How can I get the changes others have made?"
objectives:
- "Explain the differences between a local and a remote repository."
- "Explain what *tracking* and *upstream* mean."
- "Use the push command to send changes on the local branch to the remote one."
- "Use the pull command to update your local branch with the remote one."
keypoints:
- "origin is typically the name of the remote repository used by GitHub."
- "Local and remote repositories are not identical, in general."
- "Local and remote repositories are not synchronized automatically."
- "push and pull commands only affect the branch currently checked out."
---

## Remote and local repositories

- The ``example`` repository you just created is a **remote repository**: it is
  hosted by a third party hosting system - GitHub in this case.
- The ``recipe`` repository you created earlier was a **local repository**: it
  was just a directory on your hard drive using git for version control.
- Local and remote repositories can be synchronized, so changes are accessible
  by other contributors.
- **This synchronisation is not automatic**: it has to be done explicitly for
  each branch you want to keep up to date (see **pull** and **push** below ).
- The default name for a remote repository synchronised with a local one is
  ``origin``.

### Tracking and upstream

- A local branch synchronised with a remote one is said to be **tracking** that
  remote branch.
- The remote branch being tracked is called the **upstream branch**.
- As mentioned, **we will be working in this course with the main branch only**, but the
  concepts are applicable to all branches.

## Configuring repositories

Depending on whether you are starting from a remote repository and want to get a
local one out of it or the other way around, the steps are different.

> ## Configuring a remote repository from a local one
>
> In this case, you have a local repository and you want to synchronise it with
> a new, remote one. Let's create a remote for the ``recipe`` repository you
> worked on earlier.
>
> - Create a new repository in GitHub, as in the last episode. Give it a name,
>   description and choose if it should be public or private, but **do not add any
>   other file** (no README or licence).
> - You will be offered a few options to populate the remote repository. We are
>   interested in the third one. You will need to make sure HTTPS is selected
>   (not SSH) for your personal access token to work.
> - Launch a new command line interface and run `cd recipe` to navigate to the
>   directory where you have your local repository - then execute:
>
> ```bash
> git remote add origin ADDRESS_OF_YOUR_REMOTE_REPO
> git push --set-upstream origin main
> ```
>
> For example, for this course's repository, the address would be:
> `https://github.com/ImperialCollegeLondon/introductory_grad_school_git_course.git`
> In general, it is something like: `https://github.com/USERNAME/REPO_NAME.git`
>
> **macOS and Linux users:** You will be asked to provide your GitHub username and password.
> Enter your personal access token (PAT) as your password.
> **Windows users:** You will be presented with a ``CredentialHelperSelector`` dialog box.
> Ensure "manager-core" is selected and check the box for "Always use this from now
> on". Press Select. From the next dialog select "Token" then paste the PAT you saved
> earlier and press "Sign in". On subsequent interactions with GitHub your credentials
> will be remembered and you will not be prompted.
>
> - The first line above will set the GitHub repository as the remote for your
>   local one, calling it `origin`.
> - The second line will push your main branch to a remote one called
>  `origin/main`, setting it as its upstream branch.
> - You can check if things went well by going to GitHub: the repository there
>   should contain all the files of your local repository.
{: .challenge}

> ## Configuring a local repository from a remote
>
> This involves the git command **clone**. Let's create a local copy of the
> `example` repository you created remotely in the last episode.
>
> - On GitHub, press the down arrow in the far top right, next to your picture, and choose
>   "Your repositories" from the drop-down menu.
> - Choose the `example` repository from the list.
> - In the main screen of your repository, click on the green button on the
>   right, **Code**, and copy the address that appears in the `Clone` section. This
>   should look similar to `https://github.com/YOUR_USERNAME/example.git`.
> - Open a new command line interface and execute the commands:
>
> ```bash
> cd $HOME
> git clone ADDRESS_OF_YOUR_REMOTE_REPO
> cd example
> ```
>
> - This will download the remote repository to a new `example` directory, in
>   full, with all the information on the branches available in `origin`, if any, and
>   all the git history.
> - By default, a local `main` branch will be created tracking the
>   `origin/main` branch.
> - You can find some information on the repository using the commands already
>   discussed, like `git log`.
> ![Effect of cloning a remote repository]({{ site.baseurl }}/fig/clone.png "Effect of cloning a remote repository"){:class="img-responsive"}
{: .challenge}

## Pushing

- Its basic use is to synchronize **any committed changes** in your current
 branch to its upstream branch: `git push`.
- Changes in the staging area will not be synchronized.
![Effect of pushing a branch]({{ site.baseurl }}/fig/push.png "Effect of pushing a branch"){:class="img-responsive"}
- If the upstream branch has changes that you do not have in the local branch, the
 command will fail, requesting you to `pull` those changes first (see below).

> ## Pushing an updated README
>
> You want to update the README file of the `example` repository with more
> detailed information of what the repository is about and then push
> the changes to the remote.
>
> Modify the README file of your local copy of `example` with your preferred
> editor (any change is good enough, but better if they are useful - or at
> least, funny!) and synchronise the changes with the remote. Check on GitHub
> that you can view the changes you made.
>
> > ## Solution
> >
> > ```bash
> > git stage README.md
> > git commit -m COMMIT_MESSAGE
> > git push
> > ```
> >
> {: .solution}
{: .challenge}

## Pulling

- Opposite to `git push`, `git pull` brings changes in the upstream branch to the local
 branch.
- You can check if there are any changes to synchronize in the upstream
 branch by running `git fetch`, which only checks if there are changes, and then
  `git status` to see how your local and remote branches compare in terms of
   commit history.
- It's best to make sure your repository is in a clean state with no staged or
  unstaged changes - so, all changes committed.

![Effect of pulling remote changes]({{ site.baseurl }}/fig/pull.png "Effect of pulling remote changes"){:class="img-responsive"}

> ## Conflicts
>
> If the local and upstream branches have diverged - for example if you edited
> something directly in the repository and also locally - the command will attempt to
> merge both. This merging might be a smooth, transparent process - Git is pretty smart
> when it comes to merging branches - but might also result in **conflicts** that need
> to be resolved before proceeding.
>
> This is part of the scope of the intermediate Git and GitHub course that you can find
> in <https://imperialcollegelondon.github.io/intermediate_grad_school_git_course/>
{: .callout}

> ## Pulling an updated README
>
> When reviewing your new README file online, you have discovered a typo and
> decided to correct it directly in GitHub. Modify the README file online and
> then synchronise the changes with your local repository (tip: you can edit
> any text file directly in GitHub by clicking in [the little pencil button](https://help.github.com/en/github/managing-files-in-a-repository/editing-files-in-your-repository)
> in the upper right corner).
>
> > ## Solution
> >
> > ```bash
> > git fetch
> > git status
> > ```
> >
> > This will indicate that the remote branch is ahead of your local branch
> by 1 commit. Since there are no diverging commits, it is safe to pull.
> >
> > ```bash
> > git pull
> > ```
> >
> {: .solution}
{: .challenge}

{% include links.md %}
