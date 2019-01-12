---
title: "Using GitHub for project management"
tags: "github issues milestones users tasks lists project management"
desc: "Techniques like milestones, assign people to tasks, lists and more to use GitHub as a large-scale project management tool."
checklist: sprint-checklist
lesson: "/courses/web-dev-6/agile-project-planning/"
---

GitHub has lots of tools to help project management for software projects—not just repositories & code hosting. The primary project management tool is Boards, but Issues work very well for task lists & team assignments.

**And we can host our code in the same place—our project management and code on the same platform.**

---

## Issues as tasks

We primarily think of Issues as a way to describe something that’s wrong and ask for help on bugs. But that’s a really narrow idea of what Issues can accomplish for us.

GitHub Issues work really well as backlogs for Agile development and Sprint tasks. We can assign them to specific teammates, we can categorize them and give them deadlines using milestones.

![](issue.jpg)

They provide lots of features within their commenting system: Markdown, task lists, screenshots, etc. Leveraging Issues for more than just bugs opens up lots of project management ideas.

Issues can even be brainstorming/discussion platforms—they don’t always have to turn into a Sprint task.

### An Issue or it doesn’t exist

One idea to really get into your brain is that the Issue list is everything. **If it isn’t an Issue then it doesn’t exist and it doesn’t need to be completed.**

Everything that should be documented, event frivolous things that probably don’t need to be documented should become an Issue—they’re searcable, filterable and taggable.

### Helpful labels

Using labels and assigning them to Issues is a great way to organize Issues. It allows us to see at a glance what the Issue pertains too and they’re completely filterable.

![](labels.jpg)

Here’s standard set of Issue labels & colours you can use in your project:

- **blocked** — (yellow) something held-up by another task, awaiting something else to be completed; technical debt: code that needs to be written better
- **bug** — (red) critical, something broken, something needs fixing
- **content** — (purple) creation, writing, acquiring, editing written text content
- **design** — (blue) graphic design, UX, illustration, preparing assets
- **dev** — (dark blue) writing code, debugging, maintaining code
- **enhancement** — (green) something to be added, new, not fully specified yet
- **product** — (dark green) overarching ideas, decisions & discussions

Try to assign a label to every Issue to help team communication.

### Assigning teammates

When starting a new Sprint and determining which team member will be assigned each task we can assign people directly to a task within GitHub.

In the sidebar of the Issue screen there’s an “Assignee” menu you can use to assign your teammates to the Issue task.

*Each Issue task should be small enough for a single person to fully complete within the Sprint’s time period—one small feature of the project.*

**There are very few situations where you should assign more than one person to an Issue task.** If you find yourself assigning multiple people to the task it’s likely you haven’t broke the task into small enough pieces.

### Issue task lists

Task lists within Issues are a wonderful way to break down a task into smaller chunks—they even have a nice little completion graph based on how many items have been checked off.

**Do not treat task lists as a way to assign a teammate multiple jobs for the Sprint.** The task list is there to break down a larger, more involved job into a recognizable list.

Use the GitHub Markdown task list syntax to start a list in your Issue:

```md
- [x] Confirm the dataset is accurate
- [ ] Check new data against historical sets
- [ ] Import data into application
- [ ] Generate chart with new & old data sets
```

*Putting an `x` in between the brackets denotes that it’s checked off.* This isn’t completely necessary because GitHub will present you with a checkbox after the Issue has been published.

---

## Projects boards

Another fantastic feature that GitHub offers to help with project management is: Boards. Boards are an implementation of Kanban boards—they even have automation features that link up with Issues.

![](progress.jpg)

Here’s a fairly common board setup—based on the ”Kanban automated” board. There template provided by GitHub will work well for most teams, but you can also customize it and play with the automation features.

- **To do** shows all the task that need to be completed for this Sprint—you can add an Issue task from the Issue screen by assigning it to a project.

- **In progress** is where we can find the features that are currently being developed—it’s up to each teammate to move their task Issue into this column.

- **In review** shows all the tasks that are waiting to be reviewed by teammates—you can get a task to automatically move from *In progress* to *In review* by adding a magic keyword in the commit message’s description: `Closes #58` (where `58` is the ID of the Issue).

- **Done** is where task Issues are moved when they are reviewed and complete. Usually they’re moved there as a team during the Sprint review.

---

## Milestones & deadlines

To fit with the Agile Sprint methodology, GitHub provides Milestones. Milestones allow us to group a bunch of task Issues together and set a deadline for them.

![](milestone.jpg)

You can assign a Milestone to an Issue directly on the Issue’s page—there’s a little menu.

**We end up having a new Board & a new Milestone for each Sprint.** This is really beneficial when we’re looking back to see how and when things were completed because all the Issues are grouped together on the Milestone page.

---

## Branching, pull requests, approvals

Many teams love to have protected branches & approvals for code changes. One common setup is to use the `master` branch of the repository to be the *live* project. It work’s really well with the Agile Manifesto because we can release small features onto the `master` branch regularly which will automatically populate to the live application.

*We prevent everybody on the team from committing directly to the `master` branch because that means they’re committing directly to the live project.* We most often want people to have their work reviewed by a teammate before it’s merged and deployed into the live `master` branch.

**Each Issue task, that’s assigned to a team member must get it’s own branch—branched from `master`.** It really helps with organization to know that each Issue is associated with a specific branch in the code base.

[**☛ Learn more about Branching & GitHub Flow**](/topics/branching-github-flow/)
