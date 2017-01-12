---
title: "Branching & GitHub Flow"
tags: "github hosting system branches master gh pages flow issues pull requests"
desc: "Understanding the GitHub Flow when using branches and pull requests with your team."
video: mHl91Udzljw
---

Think about how you generally work on some code. You write some code then decide you want to try something else, so you make a copy, maybe you name it `version-2`. Then you decide you want to try something else, you copy and name it `version-3`.

Now you have a litter of different files for different features you’ve tried out.

**Git branching solves this problem by providing a clean way to make copies of your code to work on a specific feature.**

---

## GitHub Flow

There’s a process called GitHub Flow that’s very popular for working on teams.

The idea is that your `master` branch should never be coded on directly. Instead you should create a new branch for each feature you’re adding.

When you are satisfied with your changes you sync to GitHub, make a pull request, get feedback and merge.

### 1. Make a new branch in the GitHub app

![](create.jpg)

### 2. Publish the branch

![](publish.jpg)

### 3. Add new features to your code and commit regularly

![](commit.jpg)

### 4. Sync the branch to GitHub

![](sync-up.jpg)

### 5. Press the compare & review button

![](compare-review.jpg)

### 6. Select the new branch

![](choose-branch.jpg)

### 7. Create a pull request

![](pull-request.jpg)
![](send-pull-request.jpg)

### 8. Request feedback

![](get-feedback.jpg)

### 9. Merge the new branch with master

![](merge.jpg)
![](confirm-merge.jpg)

### 10. Delete the branch

![](delete-remote.jpg)

### 11. In the GitHub app, switch to master

![](switch-branch.jpg)

### 12. Sync

![](sync-down.jpg)

### 13. Delete the local branch

![](delete-local.jpg)

---

## Video list

1. [GitHub: branching and merging](https://www.youtube.com/watch?v=mHl91Udzljw&list=PLWjCJDeWfDdfSZOQYvsy_jJiAvx4uaJLB&index=6)

## Supplemental links

- [GitHub: Mastering GitHub Flow](https://guides.github.com/introduction/flow/index.html)
- [GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html)
- [Emoji Cheat Sheet](http://www.emoji-cheat-sheet.com/)
