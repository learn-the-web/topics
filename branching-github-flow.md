---
title: "Branching & GitHub Flow"
tags: "github hosting system branches master gh pages flow issues pull requests"
desc: "Understanding the GitHub Flow when using branches and pull requests with your team."
playlist: version-control-github
video: 6-branching
flowchart: branching-flowchart
extra_practice:
  activities:
    - title: "Git Graduator"
      url: "git-graduator"
  slides:
    - title: "Many people, one codebase"
      url: "/courses/web-dev-6/many-people-one-codebase/"
  lessons:
    - title: "Branch & pull request"
      url: "/courses/web-dev-6/branch-and-pull-request/"
---

Think about how you generally work on some code. You write some code then decide you want to try something else, so you make a copy, maybe you name it `version-2`. Then you decide you want to try something else, you copy and name it `version-3`.

Now you have a litter of different files for different features you’ve tried out.

**Git branching solves this problem by providing a clean way to make copies of your code to work on a specific feature.**

---

## Working smoothly with teams

Branches help facilitate working on teams a little better, because we can have a pristine version of the website: `master` and then we work on separate branches.

Most often, on teams, we protect the `master` branch: the prevent erroneous commits going onto `master`—which also means they will go onto the live website.

- `master` is the exact replica of what’s online.
- Only approved code should be put onto `master` because it will show on the website for real users.
- We don’t directly commit to `master` because we want our code vetted before launching to users.

### Branches for every feature

Each new feature we want to add to our website get its own branch. **When a feature is complete the branch is discarded & not used again.** Of course it’s important to merge the code into master first.

We can even use branches for testing something out, if it fails, we can just discard the branch and we don’t accidentally affect the live website.

#### Branches for bug fixes

Even a small typo or bug fix will get its own branch. Creating a pull request for a small typo is a little annoying, yes, but it keeps us all accountable for changes that get deployed to the live website.

### Code reviews for everybody

As part of working on teams it’s always important that we get our code reviewed by our peers.

As part of GitHub’s systems we can prevent code from showing on our `master` branch until it has been approved by someone else. It makes everyone accountable for what’s on the live website—and helps us improve by getting our code looked at by others.

[**☛ Follow a step-by-step lesson on setting up your repository.**](/courses/web-dev-6/github-project-setup/)

---

## GitHub Flow

There’s a process called GitHub Flow that’s very popular for working on teams.

The process follows these steps:

1. Pull `master` to your computer to get the newest version
2. Make a new branch, from `master`, naming it after the new feature
3. Make lots of commits
4. Publish the branch to GitHub & make a pull request
5. Get a teammate to approve or reject the code
6. If changes are needed make more commits to the branch
7. After approval the branch gets merged into `master`
8. Your local branch can be deleted and `master` pulled again

[**☛ See the branching flowchart for a more detailed explanation.**](/topics/branching-flowchart/)
[**☛ Learn how to update your code after branching.**](/topics/updating-from-master-flowchart/)

[**☛ Follow a step-by-step branching lesson.**](/courses/web-dev-6/branch-and-pull-request/)

---

## Video list

1. [GitHub: Branching and merging](https://videos.learntheweb.courses/playlists/version-control-github/#6-branching)

## Supplemental links

- [GitHub: Mastering GitHub Flow](https://guides.github.com/introduction/flow/index.html)
- [GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html)
- [Emoji Cheat Sheet](http://www.emoji-cheat-sheet.com/)
