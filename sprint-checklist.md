---
layout: checklist
title: "Sprint checklist"
tags: "agile sprint scrum kanban software development checklist"
desc: "A checklist listing the things to be completed before and after an Agile Scrum Sprint."

sections:
  - title: 'Agile'
    notes: 'Focus on users and customers & reorient when requirements and people’s minds change.'
    groups:
      - title: 'Sprint process'
        notes: 'The team defines what tasks each sprint collects & assigns to be completed by a deadline.'
        notCheckList: true
        items:
          - '![Project task list ➔ Plan sprint ➔ Sprint task list ➔ Design & dev ➔ Sprint review ↫](sprint-flow.svg)'

      - title: 'Issue labels'
        notes: 'Use GitHub Issue labels to help categorize and understand all the tasks—every Issue must be labeled.'
        notCheckList: true
        items:
          - '![“blocked”: yellow; “bug”: red; “content”: purple; “design”: blue; “dev”: dark blue; “enhancement”: green; “product”: dark green](labels.png)'

      - title: 'Development process'
        notes: 'The `master` branch is always pristine—commit only to feature branches then merge with a pull request.'
        notesAfter: '[See Branching & GitHub flow for more detail ➔](/topics/branching-github-flow/)'
        items:
          - 'Protect `master` branch: require pull requests, dismiss stale pull requests & include admins'
          - 'All team members clone the repository'
          - 'Create a new feature branch for making changes'
          - 'Commit to the feature branch & publish'
          - 'Create a pull request for review'
          - 'Get another team member to review and approve or deny'
          - 'Merge pull request into `master` & delete the feature branch online and locally'

  - title: 'Plan sprint'
    notes: 'At the start of each sprint setup, plan & assign all the work to be completed by the set deadline.'
    groups:
      - title: 'Milestone & deadline'
        items:
          - 'Create a new milestone named after the sprint (week) number, e.g. “Sprint 2”'
          - 'Add a description denoting the overall sprint goal'
          - 'Add a deadline: before class next week'
      - title: 'Project board'
        noteImg: '![](task-board-small.svg)'
        items:
          - 'Create a new project board named after the sprint (week) number, e.g. “Sprint 2”'
          - 'Add a description denoting the overall sprint goal'
          - 'Use GitHub’s “Kanban (Automated)” template as a starter'
          - |
            Create a new “In review” column:

            - Preset: “Done”
            - Check: “Move all closed Issues here”
            - Yes: “This rule will be removed from the Done column”
            - Move “In review” between “In progress” & “Done”
          - 'Delete the sample cards'

      - title: 'Create Issues'
        items:
          - '**It’s an Issue or it doesn’t exist.**'
          - 'Determine what the product should look like by the end of the sprint'
          - 'Create Issues for each small task *or* use Issues from the product backlog'
          - 'Use [Markdown task lists](/topics/markdown-yaml-cheat-sheet/#markdown) to further detail the Issue'
          - 'Label each issue categorically'
          - 'Assign each Issue to a single person'
          - 'Assign each Issue to the sprint’s milestone'
          - 'Assign each Issue to the sprint’s project board'

  - title: 'Sprint review'
    groups:
      - title: 'Cleanup'
        notes: 'Cleanup leftovers in preparation for the next sprint.'
        items:
          - 'Make sure all complete Issues are closed'
          - 'Make sure all pull requests are approved & complete'
          - 'Remove all incomplete Issues from the sprint’s milestone'
          - 'Remove all incomplete Issues from the sprint’s board'
          - 'Close the sprint milestone'
          - 'Close the sprint project board'
      - title: 'Review'
        notes: 'Complete a small critique, review and reflection of your work during the sprint.'
        items:
          - 'Make a new Issue, assigned to the sprint’s milestone & assigned to **all** the team members'
          - 'Assign this Issue the “product” label'
          - 'Give a quick overview of your progress so far as the Issue description'
          - |
            Each team member must make a comment answering these questions:

            - How did you & the sprint *succeed*? What was positive?
            - How did you & the sprint *fail*? What was negative?

            **Do not blame team members for anything.** This reflection is all about *you* and what *you* contributed.
          - 'Tag `@thomasjbradley` when all team members have contributed'
          - 'Close the Issue'

---
