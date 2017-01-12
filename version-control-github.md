---
title: "Version control & GitHub"
tags: "version control history undo saving github use committing syncing undo saving history messages descriptions application"
desc: "Understanding the value of version control and how it helps us and using GitHub to store the code’s history and synchronize."
playlist: PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB
---

Version control is something all developers & designers should become intimately familiar with. It allows us to track changes in our code, over time, and rollback to older versions if we mess up.

---

## Version control solutions

There are a whack load of different version control solutions. In this program there are three major ones you’ll be working with:

- *GitHub* — for code, text files, small images
- *Dropbox* — for big files, Creative Suite
- *InVision* — for UX files, wireframes, prototypes

---

## Common terms

There’s a whole lot of jargon when it comes to version control here’s a few of the common terms:

- *Repository:* the system and database that stores the history of your files
- *Initialize:* turn your folder into a repository
- *Clone:* get a copy of the code and all its history; usually from another computer or server
- *Revision:* the version of a file (or files) in the history
- *Commit:* save the state of your files
- *Local:* your own copy of the repository
- *Remote:* a copy of the repository on another computer
- *Pull:* get commits from a remote repository
- *Push:* send your commits to a remote repository
- *Branch:* A copy of your code with a different series of changes
- *Merge:* combine your changes with another developers’ changes

---

## Basic workflow

The common workflow for working with version control software goes something like this:

1. Clone or initialize a repository
2. Make a significant change
3. Check the status and compare the changes
4. Stage and commit your change to the history
5. Repeat steps 2–4 as needed
6. If you’re working with other people, pull and merge their remote commits
7. Push your commits to the remote repository

That’s it—but, there is so much more you can do.

---

## GitHub

[GitHub](https://github.com) is one of the most common places to hold open-source (and closed-source) code. It offers a place to put the code for free and has fully integrated version control.

GitHub is based entirely on top of Git, the version control system, and integrated around its features while adding more hosting and project management tools.

*You’ll need to get a [GitHub](https://github.com) account before we go any further.*

### Installing the GitHub Desktop application

We’ll need to install the GitHub Desktop application so we can interact with GitHub and Git form our computer.

1. Download the app from the [GitHub Desktop](https://desktop.github.com/) website.
2. When it asks you to move it to the applications folder—press “Move to Applications Folder”.
3. Sign in with your GitHub username, email address, and password.
4. When it asks you to look for repositories—press “Skip”.
5. *It will try to get you to do a tutorial with these little pop-up bubbles—don’t bother, press the little “x” icon on the bubble.*

### Creating a new project

The first thing to do after creating your GitHub account is signing in. Then we can start creating new projects.

Before starting this project we need to create a repository on GitHub. The repository will hold all of our website code, all the history of our project, and be our host.

![](repo.jpg)

When we get to the new repository page there’s a few fields to complete.

![](repo-new.jpg)

- **Repository name** — create a unique name for the repo, make sure it follows the [naming conventions](/topics/naming-paths-cheat-sheet/#naming-conventions).
- **Description** — come up with a short description describing the purpose of the project.
- **Public/Private** — choose “Public” because we don’t have a paid accounts.
- **Initialize this repository with a README** — always make sure this is enabled.

### Setting up hosting with GitHub Pages

There are different ways to set up hosting on GitHub Pages, the most common way is using a branch called `gh-pages`.

[**☛ See a whole GitHub hosting setup tutorial from Web Dev 1**](/courses/web-dev-1/website-on-github/#step-3)

---

## Using GitHub Desktop

The GitHub Desktop application will detect any changes we make to our code and allow us to save the state, like a permanent undo—this process is called committing.

### Commits & commit messages

Commits are one of the most important things you do with your version control system. Every time you commit, you are saving the current state of your code. You are making a breadcrumb that you can go back in time to.

#### Committing some code

Whenever you’ve changed something significant in your code and you want to save its state, go to the GitHub Desktop application.

It will detect whatever file in your code you’ve changed and show you a screen to commit the changes.

![](commit.jpg)

**Make sure to write a descriptive message!**

![](sync.jpg)

Then sync it to the GitHub website—allowing anybody to see your website live on the Web.

#### Commit early, commit often

The idea is to commit frequently. As soon as you’ve added a small function or significant piece of code.

- You don’t need to commit for every line of code
- You should commit when you add a new function
- You shouldn’t commit—only once—when everything is done
- Your code doesn’t need to be “done” to commit
- Think of your project in small blocks, and then in smaller blocks—those smallest blocks are your commits

#### Commit messages

Every time you commit you must write a commit message describing what you changed. Some examples:

- “Bug fix: the dinosaur name function was always returning Tyranosaurus Rex”
- “New feature: added the ability to track the length of a dinosaur”

**Your commit messages must be descriptive and specific.** If you ever need to go back in time on your project, they describe the state of the project for that commit. **Commit messages are for you and other developers.**

---

## Ignoring files

To ignore files that you don’t want committed to your repository—like passwords—use a `.gitignore` file.

Just create a file in your repository named `.gitignore` and put the names of the files you want to ignore inside it.

### Ignore my database connection file

```
db-conn.php
```

### A default .gitignore

```
._*
.DS_Store
Thumbs.db
```

[**☛ Git ignore templates on GitHub**](https://github.com/github/gitignore)

---

## Branching

Think about how you generally work on a project: you do one thing then decide you want to try something else, so you make a copy, maybe you name it `version-2`. Then you decide you want to try something else, you copy and name it `version-3`.

Now you have a litter of different files for different features you’ve tried out.

Git branching solves this problem by providing a clean way to make copies of your code to work on a specific feature.

[**☛ Git Branching + GitHub Flow**](/topics/branching-github-flow/)

---

### Video list

1. [GitHub: setting up & creating projects](https://www.youtube.com/watch?v=P6SOVdNVylY&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=1)
2. [GitHub: setting up hosting with GitHub Pages](https://www.youtube.com/watch?v=pc3jwarJxuU&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=2)
3. [GitHub: saving state and syncing](https://www.youtube.com/watch?v=wDn7iwORSLY&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=3)
4. [GitHub: syncing remote edits](https://www.youtube.com/watch?v=axPqGTjT52c&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=4)
5. [GitHub: ignoring files from your project](https://www.youtube.com/watch?v=ck-J4nZeLtI&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=5)
6. [GitHub: branching and merging](https://www.youtube.com/watch?v=mHl91Udzljw&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=6)
7. [GitHub: handling conflicts with team members](https://www.youtube.com/watch?v=plm4x_DjDa8&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=7)
8. [GitHub: using Issues](https://www.youtube.com/watch?v=J3STGo6ZwYA&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=8)
9. [GitHub: enabling the Issues tab](https://www.youtube.com/watch?v=vTULg-7xycs&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=9)

---

## Supplemental links

- [Git + GitHub](https://www.youtube.com/playlist?list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB)
- [Replacing FTP with Git + GitHub](https://www.youtube.com/watch?v=24NGu1vGBiw)
- [GitHub Guides](https://www.youtube.com/user/GitHubGuides)
- [A Visual Guide to Version Control](http://betterexplained.com/articles/a-visual-guide-to-version-control/)
- [Intro to Distributed Version Control Illustrated](http://betterexplained.com/articles/intro-to-distributed-version-control-illustrated/)
- [Git Book](http://book.git-scm.com/)
- [Git Documentation](http://git-scm.com/documentation)
- [Git Immersion: Git Fundamentals](http://gitimmersion.com/)
- [GitHub Help](http://help.github.com/)
- [Git Reference](http://gitref.org/)
