---
layout: flowchart
title: "Branching flowchart"
tags: "git github feature branches branching merge pull request conflict flowchart"
desc: "A flowchart describing the steps necessary for executing a proper GitHub Flow branching process."

tasks:
  - title: "Determine the small feature to be coded"
    desc: |
      Each new feature should be as small as possible, so that a single person can undertake the challenge.
  - title: "Make a detailed Issue for the task"
    desc: |
      Make a detailed Issue including adding it to a Sprint, assigning it to a single person & giving it appropriate labels. [See Agile project planning for more details.](/courses/web-dev-6/agile-project-planning/)
  - title: "Pull"
    desc: |
      Before branching, make sure you’re viewing the `master` branch, then you must pull the most recent code from the GitHub website so yours is up-to-date.
      <br>`⌘⇧P`
  - title: "Make a new branch for the task"
    desc: |
      Make a new branch specifically for this feature, named after the task & Issue.
      <br>`⌘⇧N`
  - title: "Write code & commit regularly"
    repeat: true
    desc: |
      Write code and commit regularly. Be sure to follow the [Git commit best practices](/topics/commit-message-cheat-sheet). *It’s okay if the commits are incomplete because we’re coding on a separate branch it’s not going to affect the live website.*
      <br>`⌘ Return`
  - title: "Publish branch"
    desc: |
      You can publish the branch to the GitHub website whenever you’re ready. Without a pull request the published branch just kinda sits there.
      <br>`⌘P`
  - title: "Create a detailed pull request"
    desc: |
      When you’re ready for someone else to look at the code—even if it isn’t complete—make a pull request. Use pull requests as a discussion board. Follow the Sprint best practices and use labels, projects, milestones & assignees.
  - title: "Resolve any conflicts"
    optional: true
    desc: |
      If there are any conflicts, because someone else edited the same code, resolve them using GitHub’s interface.
  - title: "Pull conflict resolution merge"
    optional: true
    desc: |
      Because of the conflict resolution, code changed, so we need to make sure that your local feature branch is the most up-to-date version of the code. So pull again.
      <br>`⌘⇧P`
  - title: "Get a teammate’s review"
    desc: |
      A teammate should now look of the code and decide whether to approve or reject the code.

      - If the code isn’t good enough make detailed comments, even comment on specific lines.
      - If the code is good, write a nice, positive message.
  - title: "Make more commits"
    optional: true
    repeat: true
    desc: |
      If the pull request was rejected, you (as the original author), must fix the code and create new commits. *You do not have to create a new branch, work on the same branch until this pull request is resolved.*
  - title: "Merge pull request & delete branch"
    desc: |
      When the code is approved, merge the pull request and delete the branch from GitHub’s website. The feature branch is no longer necessary because the code has been merged into `master`
  - title: "Close the Issue"
    desc: |
      Close the original task Issue and make sure the cards in the project board are in the “Done” column.

      - Use `Fixes #80` or `Closes #77` in commit message descriptions to automatically close Issues.
  - title: "Delete local branch"
    desc: |
      The local feature branch, on your computer, is no longer needed so delete it from your computer too.
  - title: "Pull"
    desc: |
      Finally, make sure the code inside your repository is the most up-to-date version by pulling.
      <br>`⌘⇧P`

---
