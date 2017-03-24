# Team workflow with GIT
---
## === READ ME FIRST ===
#### 01. ALWAYS create `NEW BRANCH` for each `ticket`.
#### 02. ALWAYS put `BRANCH NAME` is `TICKET CODE`.
#### 03. DO NOT use commit with argument `amend` or `reset commit` if don't know what to do.
#### 04. DO NOT rebase with `Interactive` in any conditions.
#### 05. ALWAYS inform teammate after push commit.
#### 06. ALWAYS ask teammate and team leader if have any question/confuse.
#### 07. SHOULD use ssh for git task.
#### 08. ALWAYS rebase `BASED BRANCH` before push commit
#### 09. ALWAYS push `commit` after done task.
#### 10. SHOULD commit `files` before leaving.
---

## === WORKING with GIT ===
_This tutorial is using project `PROJECTS TUTORIAL` with code `TUT`_.

_There are some points as below:_

0. `Based branch` is `develop`

1. `TUT-1` assigned to `Person 1`

### 00. Prepare before working
#### i. Working directory
_Should create directories for personality management._

_This is an example_
```bash
$ mkdir -p ~/Projects/TUTORIAL/{Code,Documents,Design}
```

```
|-- ~/Projects
  |-- TUTORIAL
    |-- Code
      |-- TUTORIAL_GIT # Project Tutorial will be cloned to this
      |-- TUTORIAL_HTML
      |-- TUTORIAL_PHP
    |-- Documents
    |-- Design
```
#### ii. Clone Project

```bash
$ git clone <git_path> <directory_path>
```
```bash
# Eg:
$ git clone git@github.com:person_1/tutorial.git ~/Projects/TUTORIAL/Code/TUTORIAL_GIT
Cloning into 'TUTORIAL_GIT'...
remote: Counting objects: 42, done.
remote: Compressing objects: 100% (27/27), done.
remote: Total 42 (delta 13), reused 42 (delta 13), pack-reused 0
Receiving objects: 100% (42/42), 7.27 KiB | 0 bytes/s, done.
Resolving deltas: 100% (13/13), done.
Checking connectivity... done.
```

#### iii. Setup environment & Install Dev tools
- Please read `README` file before install development environment.
- Ask teammate or teamleader if don't know how to complete this step.
- Learn to use newest tools to improve performance.

#### iv. Edit `.gitignore` file
- Just add lines (DON'T EDIT) into `.gitignore` to avoid committing trash or useless files.

### 01. Create new `BRANCH`
```bash
$ git checkout <based-branch> <new-branch>
```

```bash
# Eg:
$ git checkout develop TUT-1
Switched to a new branch 'TUT-1'
```
### 02. Add files to `staging` and commit files
_Always using `git status` to make sure what should commit_

**Just remember that `multiple commits` is important for `reviewing` and `self improvement`**

```bash
$ git status
$ git add <file> # Repeat this for all needed file
$ git commit -m 'This is summary message'
```
**REPEAT these `commands` until all needed files are commited**

```bash
# Eg:
$ git status
On branch TUT-1
Your branch is up-to-date with 'origin/TUT-1'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   first_file.tut
  modified:   second_file.tut

Untracked files:
  (use "git add <file>..." to include in what will be committed)

  just-ignore-this-file.tut
  new-file.tut

$ git add first_file.tut
$ git add new-file.tut
$ git commit -m 'TUT-1: first commit for editing files'
[TUT-1 a63694a] TUT-1: first commit for editing files
 2 files changed, 104 insertions(+), 2 deletions(-)
 create mode 100644 docs/git-flow.md

$ git add second-file.tut
$ git commit -m 'TUT-1: Update second-file'
[TUT-1 e2f3b47] TUT-1: first commit for editing files
 2 files changed, 104 insertions(+), 2 deletions(-)
 create mode 100644 docs/git-flow.md

```
### 03. Push commits to git server
+++ IMPORTANT!!! DO NOT rebase other branch before push commit but `based-branch` +++
#### i. Rebase `new merged commit` from `based-branch`
- Rebase branch.
```bash
$ git rebase <based-branch>
# or
$ git pull -r <remote-repo-short-name> <based-branch>
```
- Sometime there are conflicts between code with server. Please fix these before push commits. Make sure that when to using `--theirs`, `--ours`, or `merge` code. After done these, add files and continue to rebase.
```bash
$ git add <file>
$ git rebase --continue
```
- There is some case that current code is too old from newest code. So that code is needed to rebase with many commits. Please be patient to rebase and remember that ALWAYS update code.

#### ii. Push commits
```bash
$ git push <remote-repo-short-name> <branch-name>
```
#### iii. Create pull-request
Create pull-request in `git server` ui page. And remember to inform teammate about new commits.
#### iv. Fix conflicts
If have any conflict after create new pull-request, please fix ASAP.

1. Checkout to `branch`.

2. Do [Step 03](#03-push-commits-to-git-server) until there is no conflict.

### 04. Reviewing and Fix feedbacks
- Team leader and member should review code when new pull-request is created.
- Do not hesitate to comment others' commit.
- Do not pass commit if there is any comment.
- Fix comments and commit file follow [Step 02](#02-add-files-to-staging-and-commit-files) with new commit. Do not use `commit --amend` and push with `--force`. The others will be able to trace changes.
- Push fixed commits as [Step 03](#03-push-commits-to-git-server)

### 05. Sign-off tasks (for team leaders)
#### i. Merged Pull requests
```bash
$ git checkout <based-branch>
$ git pull <remote-repo-short-name> <branch-name>
$ git push <remote-repo-short-name> <based-branch>
# or
$ git checkout <remote-repo-short-name>/<branch-name> -b <branch-name>
$ git checkout <based-branch>
$ git merge <branch-name>
$ git branch -D <branch-name>
$ git push <remote-repo-short-name> <based-branch>
```
#### ii. Versioning release
```bash
$ git tag -a -m 'Summary message for this release' <version>
```
- If project does not require special version for each release, please use this format:
```
v<phase>.<sprint>.<revirsion_of_tag / revison_of_building>

# Eg: v2.40.14 = Phase 2 - Sprint 40 - Revision 14
```
#### iii. Shipping code
```bash
$ git push <remote-repo-short-name> --tags
```
