---
title: "Using GUIs and IDEs"
teaching: 20 # TODO
exercises: 20 # TODO
questions:
- "What other ways can I interact with Git other than at the command line?"
- "What tools are available for using Git?"
- "When is it better to use each method of interacting with Git?"
objectives:
- "TODO"
- "TODO"
keypoints:
- "TODO"
- "TODO"
---

## Background

As with any aspect of your development environment, the choice of when to use a GUI
frontend to Git -- if at all -- is a matter of personal taste. Like text editors, there
are a plethora of options out there and people often have strong opinions about the
superiority of one over the other. In short, there's no single "right" way to do it.

Accordingly, this section, more so than previous ones, is really just an illustration of
*one* way to use Git with *one* particular GUI program; the hope is that you will gain
an understanding of the kinds of tasks that GUIs can make easier, so that you can make
your own decision about whether it's worth the hassle.

There are many GUI interfaces for Git to choose from; the Git website has [a decent
list](https://git-scm.com/downloads/guis). For the purposes of this tutorial though, we
will stick to using [GitKraken](https://www.gitkraken.com/) as it is free,
cross-platform and has (by our own subjective measure) one of the prettier and more
intuitive interfaces. Once you have completed this section, you may want to return to
the list of GUIs and see if there are any that better suit your own taste. Another good
choice is [GitHub Desktop](https://desktop.github.com/), GitHub's own attempt at
building a GUI: it is polished and well integrated with GitHub. (There's no Linux
client, however.) In addition, many IDEs and editors nowadays (including Visual Studio
Code and Sublime Text, etc.) have built-in integration with Git.

Whether you decide to use a GUI or not, however, we suggest it is important that you
also understand how to use Git from the command line: firstly, it teaches you about the
underlying concepts and, secondly, it is a useful fallback for when your shiny GUI falls
over.

## Why would I want to use a GUI?

Or: Surely all the cool kids just use Git from the command line?

While programs can convey a lot of information via a simple command-line interface,
there are limits to what can be conveyed easily. Notably, in the case of Git, your
repository's history is really a graph (specifically, a directed acyclic graph) and a
text interface isn't a particularly good way of showing a graph, as some of you may have
found when trying to understand the output of your `git graph` alias in the previous
section.

So far, your `recipe` repository is fairly simple, but it is worth noting that
repositories can become complex, e.g.:

![]({{ site.baseurl }}/fig/gui_complex_repo.png "Example of a complex repository")

You wouldn't want to try to visualise this in your terminal, any more than you would a
Tube map.

(If you're wondering how a repository's history can end up looking so complicated, it's
because of a feature we aren't covering in this course in detail called branching. For
those who are interested, [it is covered in the intermediate-level Git
course][intermediate-branching].)

[intermediate-branching]: https://imperialcollegelondon.github.io/intermediate_grad_school_git_course/l1-02-branching-merging/index.html

## Getting started with GitKraken

Firstly, you will need to download and install GitKraken, which can be obtained
[here](https://www.gitkraken.com/download).

Next you need to create a GitKraken account, the main purpose of which is to link the
GitKraken app with your GitHub account, so that you can make use of its GitHub
integration. While this is technically optional, we strongly recommend it. So, when you
start GitKraken, click "Sign up with GitHub":

![]({{ site.baseurl }}/fig/gui_sign_up1.png "Sign up with GitHub")

This should open a browser window in which you will have to sign in with GitHub. Once
this is complete GitKraken should log in automatically. If not, you may have to copy the
OAuth token manually into GitKraken (like I did).

Next, GitKraken will ask you to supply information about who you are, as you did when
you first started with Git. Enter your name and email address, then click "Create
Profile". Here's what it looks like for me:

![]({{ site.baseurl }}/fig/gui_sign_up2_create_profile.png "Create a profile")

You're now ready to roll!

## Creating your first repository with GitKraken

Let's start by creating a repository like you did before, just so you can familiarise
yourself with the interface.

Click "File", then "Init Repo":
![]({{ site.baseurl }}/fig/gui_init_menu.png "Click Init Repo")

Choose the "GitHub.com" tab, which will also create a remote repository on GitHub for
you. I have called mine "recipe", though you may already have a repository by this name
if you have followed all the steps for the previous sections, in which case you should
pick another name. Note that you will want to specify your own account for the "Account"
option, not an organisation.

![]({{ site.baseurl }}/fig/gui_init_github.png "Create new repository on GitHub")

- Look at new repo
- You can see there's an "Initial commit"; click on it
- Notice that a README.md file has already been added (remember this from the "sharing
  your code" section?)

![]({{ site.baseurl }}/fig/gui_new_repo.png "Screenshot showing new repository")

- What other features do you notice in the window?
- Look at the panel on the left (you might have to click on some of the buttons to
  expose bits)
- Local branches (NB: NOT DISCUSSING BRANCHES)
- Remote branches
- GitHub issues (alright, there aren't any yet...)
- (Other bits are things we're not covering in this course)

- Extract the recipe.zip file into your repository, as you did before (if you've lost
  it, get it HERE)
- (Notice the green "+2", indicating that there are two unstaged changes)
- Look at the changes (you may have to click "View changes")

![]({{ site.baseurl }}/fig/gui_unstaged_changes.png "Unstaged changes")

- In the right-hand panel, click ingredients.md

![]({{ site.baseurl }}/fig/gui_view_changes.png "Changes to ingredients.md")

- The green lines indicate lines that have been added
- As this file is new to the repository, git treats all the lines as new

- Click "Stage all changes"

![]({{ site.baseurl }}/fig/gui_staged_files.png)

- Notice how the changes are now in the staging area (i.e. under "Staged files")
- Add a commit message and click "Commit changes to 2 files"

![]({{ site.baseurl }}/fig/gui_commit_message.png "Add a commit message")

- Notice that a new commit has been added!

![]({{ site.baseurl }}/fig/gui_post_commit.png "Repository after committing")

- Notice also that there are two labels saying "main" next to the commits
- Why do you think this is?
- (The one with the computer logo is your local branch and the one with the GitHub logo
  is the remote branch.)

- Click the push button!
- You have now successfully pushed to GitHub

![]({{ site.baseurl }}/fig/gui_post_push.png "Repository after pushing")

{% include links.md %}
