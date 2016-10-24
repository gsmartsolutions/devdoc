# Workflow
We practice Scrum/Agile in all projects. Generally:

- UK members are our `Product Owners` (PO)
- GSS developers stand as `Scrum Master` (SM) and `Dev Team` (DEV)

We keep our projects on [Github](https://github.com/twentyci/) and collaborate on [JIRA](https://twentyci.atlassian.net).

## With JIRA

### Rules

We have many projects and they're being grouped to Kanban boards by their type: PHP, Ruby and Magneto.
Each project still has their board for easier to follow.

---

#### Individual Project Kanban:
This board is used for planning and managing each projects in long run.

TODO: Text is boring, Require to add some Image to demonstrate ideas

- Backlog:
    - PO raise use-stories, often big
    - Could be considered as "Project Features"
- Requirement Reviews:
    - PO, DEV brainstorming then break Backlog's issues to smaller use-stories or sub-tasks
    - Or DEV could raise tickets which are benefits to projects, PO would review to approve or reject
    - It could be consider as "Dev requirements"
- Grooming:
    - Discussion with PO, UK team for requirements
    - QA to clear all confusions, unclear points ...
- Estimation:
    - DEV internal session, Use issues as input to produce `Issue Estimation` in story points
    - Story points allowed : 1,2,3,5,8
    - We don't want to be risky. Every `8 points issues` will be considered to break to be smaller one
    - Estimation should be realistic and consistency. Simple things like update copy, fix typo,
    change image ... should be 1 points.
    - Issues has Estimation will display on **Sprint Planning**
- Dev Backlog:
    - aka Sprint Backlog
    - Issues added after **Sprint Planning** session. These ones should be delivered at end of Sprint
- In Progress & Done should be managed in `Projects' Type Kanban` instead. No action for those columns
on this board.

#### Projects' Type Kanban

TODO: Add projects' type kanban board information

### Common events:

- **Sprint Planning** starts on Tuesday from 3:30 PM
- **Sprint Retro** starts on Thursday 4:00 PM (After new sprint started)
- **Daily Scrum** meetings at 4:00 PM every day

Current Buts :
- Missing **Sprint Review** event and we do **Sprint Retro** after new sprint get started.
- Story points are related to Execution time, rather than Complexity

## With Git
We're using `Git fork` as primary Git work-flow.  You could read more about `Forking work-flow` in
[here](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow)

TODO: Add `Forking work-flow` overview image and step by step to working on projects
(from branching-off, to release tag)

## References