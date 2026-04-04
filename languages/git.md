# Git Syllabus

A complete, structured learning path for Git — from your first commit to branching, rebasing, recovering mistakes, collaborating safely, and maintaining professional team workflows.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 4-8 Weeks](https://img.shields.io/badge/Duration-4--8%20Weeks-blue)
![Topics: 10 Phases](https://img.shields.io/badge/Topics-10%20Phases-orange)
![Git: Modern CLI](https://img.shields.io/badge/Git-Modern%20CLI-F05032)

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Phase 1: Getting Started & Mental Model](#phase-1-getting-started--mental-model)
- [Phase 2: Tracking Changes & Commit Hygiene](#phase-2-tracking-changes--commit-hygiene)
- [Phase 3: Inspecting History & Undoing Work](#phase-3-inspecting-history--undoing-work)
- [Phase 4: Branching & Merging](#phase-4-branching--merging)
- [Phase 5: Remotes & Collaboration](#phase-5-remotes--collaboration)
- [Phase 6: Rebase, Stash, Cherry-Pick & Tags](#phase-6-rebase-stash-cherry-pick--tags)
- [Phase 7: Conflict Resolution & Recovery](#phase-7-conflict-resolution--recovery)
- [Phase 8: Advanced Git Tools](#phase-8-advanced-git-tools)
- [Phase 9: Team Workflows & Pull Request Practices](#phase-9-team-workflows--pull-request-practices)
- [Phase 10: Release Management & Automation](#phase-10-release-management--automation)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Resources](#resources)

---

## Prerequisites

> [!NOTE]
> Git is a **version control system**, not a hosting platform. Learn Git itself first. GitHub, GitLab, and Bitbucket sit on top of Git workflows but do not replace understanding the CLI and the underlying model.

- Basic command line usage
- Familiarity with files, folders, and text editing
- A local machine with Git installed
- A small practice project you can safely experiment on

---

## Phase 1: Getting Started & Mental Model

![Phase](https://img.shields.io/badge/Phase-1%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Learn what Git stores and how its snapshot model differs from file syncing.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What is Git | A distributed version control system built around snapshots and history |
| 2 | Why Version Control Matters | Recoverability, collaboration, reviewability, and experimentation |
| 3 | Installing Git | `git --version`, first-time setup, editor configuration |
| 4 | Repository Basics | `git init`, `.git/`, working tree, local repository |
| 5 | Snapshot Mental Model | Commits as snapshots, not just text diffs |
| 6 | HEAD, Branches, and Refs | Lightweight pointers and your current checkout |
| 7 | Git vs GitHub | Local version control vs remote hosting and collaboration tooling |

> [!IMPORTANT]
> Git becomes much easier once you stop thinking "save my files" and start thinking "create named snapshots of project state."

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Initialize a repository and configure your identity
- [ ] Explain the working tree, staging area, and commit history
- [ ] Explain what `HEAD` points to

</details>

---

## Phase 2: Tracking Changes & Commit Hygiene

![Phase](https://img.shields.io/badge/Phase-2%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn the day-to-day Git workflow for creating clean history.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `git status` | Reading what changed and what Git expects next |
| 2 | Staging Area | `git add`, partial staging, intentional commit composition |
| 3 | Commits | `git commit -m` and meaningful snapshot boundaries |
| 4 | Commit Messages | Clear messages that explain what changed and why |
| 5 | `.gitignore` | Keeping generated files and secrets out of history |
| 6 | File Renames & Deletes | `git mv`, removals, and how Git tracks changes |
| 7 | Small Atomic Commits | Why clean history improves reviews and debugging |
| 8 | Branch Defaults | Using `main` or repo conventions consistently |

> [!TIP]
> The staging area is one of Git's best features. Use it to craft commits that tell one coherent story instead of dumping every local change into one snapshot.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Make several clean commits with good messages
- [ ] Use `.gitignore` to exclude generated files
- [ ] Explain why staging and committing are separate steps

</details>

---

## Phase 3: Inspecting History & Undoing Work

![Phase](https://img.shields.io/badge/Phase-3%2F10-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn how to read history and correct mistakes safely.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `git log` | Reading commit history with useful flags |
| 2 | `git diff` | Comparing working tree, staged, and committed changes |
| 3 | `git show` | Inspecting a single commit in detail |
| 4 | `git restore` | Reverting file content safely |
| 5 | `git reset` | Moving branch pointers and unstaging work carefully |
| 6 | `git revert` | Safely undoing shared history with new commits |
| 7 | Amending Commits | Fixing the most recent commit intentionally |
| 8 | Revision References | `HEAD~1`, hashes, branch names, ranges |

> [!CAUTION]
> `git reset --hard` is powerful and dangerous. Do not use destructive history commands casually, especially on work you have not backed up or pushed.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Compare working tree vs staged changes
- [ ] Undo a mistake with `restore`, `reset`, and `revert` in the right contexts
- [ ] Explain why reverting shared history is safer than rewriting it

</details>

---

## Phase 4: Branching & Merging

![Phase](https://img.shields.io/badge/Phase-4%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Master Git's most important workflow capability.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Creating Branches | `git branch`, `git switch -c`, naming conventions |
| 2 | Switching Branches | What changes in the working directory and why |
| 3 | Divergent History | How branches evolve independently |
| 4 | Merging | Fast-forward, three-way merges, merge commits |
| 5 | Merge Strategies | When a merge commit is useful vs when linear history helps |
| 6 | Branch Cleanup | Deleting merged branches and keeping repos tidy |
| 7 | Visualizing History | Graph views and decorated logs |
| 8 | Topic Branch Workflow | Feature branches and parallel work |

> [!IMPORTANT]
> Git branches are lightweight pointers, not heavyweight copies. That is why branching early and often is normal in Git.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create, switch, and delete branches safely
- [ ] Merge a feature branch back into main
- [ ] Explain fast-forward vs merge commit

</details>

---

## Phase 5: Remotes & Collaboration

![Phase](https://img.shields.io/badge/Phase-5%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn how local Git history connects to team workflows.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Remotes | `origin`, additional remotes, fetch URLs, push URLs |
| 2 | `fetch` vs `pull` | Why seeing remote changes before merging matters |
| 3 | `push` | Publishing branches and setting upstreams |
| 4 | Remote Tracking Branches | `origin/main`, `origin/feature-x`, local vs remote pointers |
| 5 | Pull Requests / Merge Requests | Review-based collaboration workflows |
| 6 | Fork Workflows | Contributing to projects you do not own |
| 7 | Syncing Work | Rebasing or merging local branches with remote updates |
| 8 | Communication Through History | Clean commits, descriptive PRs, predictable updates |

> [!TIP]
> `git pull` is really `fetch + merge` by default. Many Git problems start because people skip the `fetch` mental step and merge unseen changes automatically.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Add a remote and push a branch
- [ ] Explain `fetch` vs `pull`
- [ ] Open and update a collaborative branch workflow cleanly

</details>

---

## Phase 6: Rebase, Stash, Cherry-Pick & Tags

![Phase](https://img.shields.io/badge/Phase-6%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn the tools that help shape and reuse history intentionally.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Rebasing | Replaying commits onto a new base |
| 2 | Interactive Rebase | Squash, reword, reorder, drop, fixup workflows |
| 3 | Stashing | Temporarily parking work without committing it |
| 4 | Cherry-Picking | Bringing specific commits onto another branch |
| 5 | Tags | Annotated tags, lightweight tags, release markers |
| 6 | Detached HEAD | What it means and when it is useful |
| 7 | Aliases | Shortcuts for high-frequency Git commands |
| 8 | History Hygiene | When to rewrite local history and when not to |

> [!WARNING]
> Rebase is excellent for cleaning up local history. Rebasing commits that teammates already pulled can create collaboration pain if you do it carelessly.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Rebase a local feature branch onto updated main
- [ ] Use interactive rebase to clean up commits
- [ ] Create and inspect a release tag

</details>

---

## Phase 7: Conflict Resolution & Recovery

![Phase](https://img.shields.io/badge/Phase-7%2F10-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Recover confidently when things go wrong.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Merge Conflicts | How conflicts arise and how to read conflict markers |
| 2 | Rebase Conflicts | Resolving replayed changes during rebase |
| 3 | `git mergetool` | Tool-assisted conflict resolution |
| 4 | `git reflog` | Recovering lost commits and branch tips |
| 5 | Restoring Lost Work | Recovering from resets, deleted branches, and mistakes |
| 6 | `git blame` | Tracking when and why code changed |
| 7 | `git bisect` | Systematically finding the commit that introduced a bug |
| 8 | Safer Recovery Habits | Pausing before destructive commands and verifying refs |

> [!IMPORTANT]
> `reflog` is one of Git's most underused safety nets. If you "lost" work locally, there is a good chance Git still knows where it went.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Resolve both merge and rebase conflicts
- [ ] Recover a commit or branch pointer with `reflog`
- [ ] Use `bisect` or `blame` in a debugging scenario

</details>

---

## Phase 8: Advanced Git Tools

![Phase](https://img.shields.io/badge/Phase-8%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 6-8 Hours](https://img.shields.io/badge/Time-6--8%20Hours-yellow)

> Learn the tools that make Git powerful in large or long-lived repositories.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Revision Ranges | `A..B`, `A...B`, commit selection syntax |
| 2 | Worktrees | Multiple checkouts from one repository |
| 3 | Submodules & Alternatives | When external repo embedding helps and when it hurts |
| 4 | Hooks | Automating checks on commit, push, or other repo events |
| 5 | Sparse Checkout Concepts | Working efficiently in large monorepos |
| 6 | Signing Commits | Authenticity and trust in history |
| 7 | Patch Workflows | `format-patch`, `apply`, email-style or patch-based sharing |
| 8 | Repository Maintenance | Garbage collection, pruning awareness, keeping repos healthy |

> [!TIP]
> Advanced Git is mostly about precision. Learn the basic model first, then add tools that solve a real problem instead of collecting commands you never use.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain a revision range and use it in a log command
- [ ] Use a worktree for parallel branch work
- [ ] Describe one use case for Git hooks

</details>

---

## Phase 9: Team Workflows & Pull Request Practices

![Phase](https://img.shields.io/badge/Phase-9%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Use Git in a way that scales beyond solo work.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Branching Strategies | Trunk-based development, feature branching, release branches |
| 2 | PR Scope | Keeping changes reviewable and narrowly focused |
| 3 | Review-Friendly History | Commit organization, message quality, avoiding noisy diffs |
| 4 | Updating PRs | Rebase vs merge for staying current with main |
| 5 | Force Push Etiquette | When `--force-with-lease` is acceptable and when it is not |
| 6 | Code Review Conversation | Using history to support review, not fight it |
| 7 | Protected Branches | Rules that reduce accidental damage |
| 8 | Team Agreements | Shared conventions for branch names, commit messages, and merges |

> [!TIP]
> The best Git workflow is the one your team can explain clearly and follow consistently. Consistency beats ideological debates over "perfect" branching strategies.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Prepare a branch and PR that is easy to review
- [ ] Explain when force-pushing is acceptable
- [ ] Define a simple team Git workflow in writing

</details>

---

## Phase 10: Release Management & Automation

![Phase](https://img.shields.io/badge/Phase-10%2F10-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Learn how Git supports dependable releases and repeatable automation.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Release Tags | Marking known-good versions for distribution |
| 2 | Changelog Generation | Using commit history responsibly for release notes |
| 3 | Hotfix Flows | Fixing production issues without destabilizing ongoing work |
| 4 | Backports | Moving fixes across release lines safely |
| 5 | CI Triggers | Using branches and tags to drive pipelines |
| 6 | Semantic Versioning | How tags and releases map to version strategy |
| 7 | Repository Policies | Required checks, signed commits, protected branches |
| 8 | Long-Term Repository Health | Pruning stale branches, preserving history, reducing confusion |

> [!TIP]
> Git history becomes a release asset when tags, changelogs, and branch discipline are intentional. Otherwise it becomes archaeology.

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Tag and document a release
- [ ] Explain a hotfix or backport workflow
- [ ] Connect Git events to CI/CD behavior

</details>

---

## Common Mistakes

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Committing directly to main without discipline | Makes history noisy and risky in teams | Use short-lived topic branches where appropriate |
| 2 | Writing vague commit messages | History stops being useful for debugging and review | Explain what changed and why |
| 3 | Using `git add .` blindly | Stages unintended files and secrets easily | Review `git status` and stage intentionally |
| 4 | Confusing `reset`, `restore`, and `revert` | Can destroy work or rewrite shared history | Learn the purpose of each command clearly |
| 5 | Rebasing published shared work carelessly | Forces teammates to repair history | Rebase local branches, coordinate if history is shared |
| 6 | Force-pushing without `--force-with-lease` | Can overwrite remote work unexpectedly | Use `--force-with-lease` when history rewrite is truly necessary |
| 7 | Ignoring `.gitignore` | Build output and secrets pollute history | Define ignore rules early |
| 8 | Avoiding branches entirely | Makes experimentation and review harder | Use lightweight branches freely |
| 9 | Panicking during conflicts | Leads to bad manual edits and lost context | Read conflict markers, compare both sides, resolve deliberately |
| 10 | Forgetting Git is local-first | People over-rely on hosting platforms to save them | Understand the CLI and your local history model first |

---

## Interview Questions

<details>
<summary><strong>Beginner Level</strong></summary>

1. **What is the staging area in Git?**
   - It is the intermediate area where you choose exactly what will go into the next commit.

2. **What is a branch in Git?**
   - A lightweight movable pointer to a commit, typically used to isolate a line of work.

3. **What is the difference between `git fetch` and `git pull`?**
   - `fetch` downloads remote updates without integrating them. `pull` usually downloads and then merges them into the current branch.

4. **Why is `git revert` safer than rewriting history on shared branches?**
   - It creates a new commit that undoes changes without changing existing published history.

5. **What does `.gitignore` do?**
   - It tells Git which untracked files or patterns should be ignored and not staged accidentally.

</details>

<details>
<summary><strong>Intermediate Level</strong></summary>

1. **What is the difference between merge and rebase?**
   - Merge combines histories with a merge commit when needed. Rebase rewrites commits onto a new base for a linear history.

2. **When would you use cherry-pick?**
   - When you need one specific commit on another branch without bringing over the full branch history.

3. **What is `reflog` and why is it useful?**
   - It records where refs like `HEAD` have pointed locally, which helps recover work after resets, rebases, or deleted branches.

4. **How do you keep commit history review-friendly?**
   - Small coherent commits, good messages, no unrelated changes mixed together, and clean rebases or merges before review.

5. **What is a remote-tracking branch?**
   - A local reference like `origin/main` that reflects the last known state of a branch on a remote repository.

</details>

<details>
<summary><strong>Advanced Level</strong></summary>

1. **What is the difference between `A..B` and `A...B`?**
   - `A..B` shows commits reachable from `B` but not `A`. `A...B` refers to the symmetric difference in many Git commands, useful for comparing diverged histories.

2. **How would you recover from an accidental hard reset?**
   - Check `git reflog`, locate the previous commit or HEAD position, and reset or branch from that recovered reference.

3. **When is rewriting history acceptable?**
   - On local or unshared branches, or on shared branches only when the team explicitly expects and coordinates it.

4. **How do worktrees help advanced workflows?**
   - They let you check out multiple branches from one repository simultaneously without cloning the repo again.

5. **How do you design a sane team Git workflow?**
   - Minimize ambiguity, define branch and merge rules clearly, keep PRs small, protect important branches, and choose conventions the team will actually follow.

</details>

---

## Practice Projects

### Project 1: Personal Notes Repo
![Phase 1-3](https://img.shields.io/badge/After-Phase%201--3-green)

**What you'll build:** A small local repository where you make, stage, commit, inspect, and undo changes deliberately.

**Skills practiced:** Init, status, add, commit, diff, restore, revert.

---

### Project 2: Branching Lab
![Phase 4-5](https://img.shields.io/badge/After-Phase%204--5-yellow)

**What you'll build:** A practice repo with feature branches, merges, remotes, and pull request style updates.

**Skills practiced:** Branches, merge, fetch, pull, push, remote collaboration.

---

### Project 3: History Cleanup Exercise
![Phase 6-7](https://img.shields.io/badge/After-Phase%206--7-yellow)

**What you'll build:** A messy branch history that you clean up with interactive rebase, stash, cherry-pick, and reflog recovery.

**Skills practiced:** Rebase, stash, cherry-pick, conflict resolution, recovery.

---

### Project 4: Team Workflow Simulation
![Phase 8-9](https://img.shields.io/badge/After-Phase%208--9-orange)

**What you'll build:** A simulated team repository with branch protection rules, code review conventions, and release tags.

**Skills practiced:** Workflows, PR discipline, advanced Git tools, policy design.

---

### Project 5: Release Workflow Demo
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll build:** A repository that demonstrates version tags, changelog generation, hotfix flow, and automated CI triggers.

**Skills practiced:** Everything from all phases — your Git graduation project.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Pro Git Book](https://git-scm.com/book/en/v2) | The best comprehensive Git learning resource |
| [gittutorial](https://git-scm.com/docs/gittutorial) | Official tutorial introduction to Git |
| [Git Basics](https://git-scm.com/book/en/v2/Git-Basics-Summary) | Clear coverage of everyday commands |
| [Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell) | Excellent explanation of why Git branching is powerful |
| [Git Revisions](https://git-scm.com/docs/revisions) | Authoritative reference for revision syntax and ranges |

### Interactive Courses (Free)

| Course | What Makes It Special |
|--------|----------------------|
| [Learn Git Branching](https://learngitbranching.js.org/) | Best interactive Git visualization and practice tool |
| [Oh My Git!](https://ohmygit.org/) | Game-style Git learning with visual feedback |
| [GitHub Skills](https://skills.github.com/) | Good guided practice for Git + collaboration workflows |

### Video / Channels

| Video / Channel | Why Watch |
|----------------|-----------|
| [GitKraken YouTube](https://www.youtube.com/@GitKraken) | Clear Git explanations and workflow demos |
| [freeCodeCamp](https://www.youtube.com/@freecodecamp) | Long-form Git and GitHub courses |
| [The Primeagen](https://www.youtube.com/@ThePrimeagen) | Opinionated but useful Git workflow discussions |

### Tools & Extensions

| Tool | Why You Need It |
|------|----------------|
| [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) | Powerful Git visibility inside VS Code |
| [LazyGit](https://github.com/jesseduffield/lazygit) | Fast terminal UI for common Git workflows |
| [delta](https://github.com/dandavison/delta) | Better diff rendering in the terminal |
| [tig](https://jonas.github.io/tig/) | Terminal UI for browsing Git history |
| [GitHub Desktop](https://desktop.github.com/) | Friendly GUI for beginners who still want real Git underneath |

### Further Reading

| Resource | Format |
|----------|--------|
| [git help](https://git-scm.com/docs) | Official manual pages for every command |
| [gitrevisions](https://git-scm.com/docs/gitrevisions) | Deep dive into revision specification |

---

[Back to Main Syllabus](../README.md)
