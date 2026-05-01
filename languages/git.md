# Git Syllabus

A complete, structured learning path for Git — your one-stop guide from your very first `git init` to branching, rebasing, conflict resolution, recovering "lost" commits, contributing to open source, and shipping production-grade automation. Whether you have never run a `git` command before, or you have been using it for years and still get nervous about `rebase -i`, this syllabus walks you through every concept in the right order, explains *why* each matters, and gives you real exercises to prove you actually learned it.

![Difficulty: Beginner to Advanced](https://img.shields.io/badge/Difficulty-Beginner%20to%20Advanced-blue)
![Estimated Duration: 3-5 Weeks](https://img.shields.io/badge/Duration-3--5%20Weeks-blue)
![Topics: 13 Phases](https://img.shields.io/badge/Topics-13%20Phases-orange)
![Git: 2.x](https://img.shields.io/badge/Git-2.x-F05032)

---

## Table of Contents

- [What is Git?](#what-is-git)
- [Why Learn Git in 2026?](#why-learn-git-in-2026)
- [How Git Works](#how-git-works)
- [Pick Your Path](#pick-your-path)
- [Prerequisites](#prerequisites)
- [How to Use This Syllabus](#how-to-use-this-syllabus)
- [Phase 1: Getting Started](#phase-1-getting-started)
- [Phase 2: The Three Trees & Basic Workflow](#phase-2-the-three-trees--basic-workflow)
- [Phase 3: Inspecting History](#phase-3-inspecting-history)
- [Phase 4: Branching & Merging](#phase-4-branching--merging)
- [Phase 5: Remote Repositories](#phase-5-remote-repositories)
- [Phase 6: Rewriting History](#phase-6-rewriting-history)
- [Phase 7: Stash, Cherry-pick & Tags](#phase-7-stash-cherry-pick--tags)
- [Phase 8: Workflows](#phase-8-workflows)
- [Phase 9: Pull Requests & Code Review](#phase-9-pull-requests--code-review)
- [Phase 10: Advanced — Bisect, Worktree, Reflog](#phase-10-advanced--bisect-worktree-reflog)
- [Phase 11: Hooks & Automation](#phase-11-hooks--automation)
- [Phase 12: The Git Ecosystem](#phase-12-the-git-ecosystem)
- [Phase 13: What's Next?](#phase-13-whats-next)
- [Common Mistakes](#common-mistakes)
- [Interview Questions](#interview-questions)
- [Practice Projects](#practice-projects)
- [Git Cheat Sheets](#git-cheat-sheets)
- [Resources](#resources)

---

## What is Git?

**Git is a distributed version control system that tracks every change to every file in your project, forever.** It is the tool that lets you go back in time to any past state of your code, work on multiple features in parallel without stepping on anyone's toes, collaborate with thousands of strangers on the internet, and recover from disasters that would otherwise cost a week of work. Every modern software team — from a two-person startup to Google and the Linux kernel — runs on Git.

Git was created in **April 2005 by Linus Torvalds** in roughly two weeks. The story is famous: the Linux kernel had been using a proprietary VCS called **BitKeeper** for free under a special license. After a kernel developer reverse-engineered the protocol, BitKeeper revoked the license. Linus, fed up with every existing version control system (CVS, Subversion, Perforce — all centralized, slow, and bad at branching), wrote his own. He had three goals: be **fast**, be **distributed** (every clone is a full backup), and **never corrupt data**. He named it "Git" — British slang for an unpleasant person — because, in his words, "I'm an egotistical bastard, and I name all my projects after myself. First Linux, now Git."

In simple words:

- **Git** is the tool that runs locally on your machine and tracks history (the engine).
- **GitHub / GitLab / Bitbucket** are *hosting platforms* that store Git repositories online and add collaboration features (the marketplace). They are not Git.
- A **repository** ("repo") is a project tracked by Git — a folder with a hidden `.git` directory inside that holds the entire history.

You can use Git with no internet, no GitHub account, no remote server. The full project history lives on every developer's laptop. That's what "distributed" means.

### Centralized vs Distributed VCS

| | Centralized (SVN, CVS, Perforce) | Distributed (Git, Mercurial) |
|--|----------------------------------|------------------------------|
| History location | One central server | Every clone has full history |
| Offline work | Limited (can't commit) | Full (commit, branch, log all work offline) |
| Branching | Slow, expensive, rare | Cheap, fast, encouraged |
| Single point of failure | Yes (server dies, you lose history) | No (every clone is a backup) |
| Speed | Slow over network | Fast (most ops are local) |

### The Three Trees

Git's mental model rests on three "trees" (areas) that hold your work at different stages:

1. **Working directory** — the actual files you edit in your editor. Modifying a file here changes nothing in Git yet.
2. **Staging area** (a.k.a. *index*) — a snapshot of changes you've marked as "ready to commit". `git add` moves changes here.
3. **Repository** (the `.git` folder) — the permanent, content-addressed history of every commit. `git commit` writes from staging into here.

Once you internalize these three trees, every Git command stops feeling magical. `git status` tells you which files are in which tree. `git diff` shows the differences between trees. `git reset` moves things between trees. That's the whole game.

### A Brief History

| Year | Version | What Changed |
|------|---------|--------------|
| 2005 | Git 1.0 | Linus Torvalds writes Git in ~2 weeks after the BitKeeper drama. Initially just a "stupid content tracker" plumbing layer. |
| 2008 | GitHub launches | Cloud Git hosting + pull requests turn open source on its head. |
| 2014 | Git 2.0 | Better UX defaults — `git push` now defaults to `simple` (push current branch only). |
| 2019 | Git 2.23 | Introduced `git switch` and `git restore` — splitting the overloaded `git checkout` into two clearer commands. |
| 2020 | `main` becomes default | GitHub, GitLab, and Git itself switch the default branch name from `master` to `main`. |
| 2024+ | Git 2.40+ | SHA-256 support stabilizing, faster `git status`, partial-clone, sparse-checkout — Git scaling to monorepos with millions of files. |

> [!IMPORTANT]
> When people say "Git" today, they mean the open-source CLI tool maintained at [git-scm.com](https://git-scm.com/). That tool is over 20 years old, runs on every OS, and powers GitHub, GitLab, Bitbucket, Gitea, Codeberg, and every team's internal server. Learn the CLI. The web UI changes every six months — `git` itself does not.

### What Makes Git Special

- **Snapshots, not diffs.** Most VCS store *deltas* between versions. Git stores a complete snapshot of every file at every commit (deduplicated by content hash). That's why operations like `log`, `diff`, and `checkout` are blazingly fast.
- **Content-addressed.** Every blob, tree, commit, and tag has a SHA-1 hash derived from its contents. Identical files share storage automatically. Tampering is detectable.
- **Branches are cheap.** A branch is just a 41-byte file pointing at a commit. Creating one is instant. Teams that fear branches are using a different tool — or using Git wrong.
- **Almost everything is local.** Commits, branches, log, diff, blame — all run against your local `.git` folder. No network round trip. No waiting on a server.
- **Designed to never lose data.** Even after `git reset --hard`, the lost commits sit in the reflog for ~90 days. If you panic-quote it on a forum, someone will recover it for you.

---

## Why Learn Git in 2026?

| Reason | What It Means |
|--------|---------------|
| **Mandatory for every dev job** | Frontend, backend, mobile, data, ML, DevOps, security — every job posting on Earth says "experience with Git." Saying "I use VS Code's Source Control panel" is not enough. |
| **The universal collaboration protocol** | Pull requests, code review, branch protection, CI/CD — all built on Git. No team ships software without it. |
| **GitHub / GitLab dominate hiring** | Your GitHub profile is your resume. Recruiters check commit graphs, README quality, and PR history before they call you. |
| **Open source contribution requires it** | Want to ship a fix to React, Next.js, or the Linux kernel? You'll fork, branch, commit, push, and open a PR. All Git. |
| **Time-travel debugging via `git bisect`** | Found a bug that "used to work last month"? `git bisect` binary-searches your history to find the exact commit that broke it. Saves hours. |
| **AI tools assume Git** | Cursor, Claude Code, Copilot, Codex — every AI coding assistant reads your repo, opens PRs, runs `git diff`. Bad Git habits = bad AI experience. |
| **Recovery is part of the job** | Force-pushed over your teammate's work? `git reflog` saves you. Deleted the wrong branch? `git reflog`. Lost a commit? `git reflog`. The senior who knows reflog is the hero. |
| **Production deployments run on Git** | Vercel, Netlify, Cloudflare Pages, Heroku, Fly, Railway — push to `main`, get a deploy. Git is the deploy interface for the modern web. |

---

## How Git Works

Understanding *what Git does under the hood* makes every command stop feeling like magic. The whole system is built on four object types and a few pointers.

```
   ┌─────────────────────────┐
   │    Working directory    │  Files you edit (untracked + modified)
   └────────────┬────────────┘
                │ git add <file>
                ▼
   ┌─────────────────────────┐
   │     Staging area        │  Changes marked "ready to commit"
   │       (the index)       │
   └────────────┬────────────┘
                │ git commit -m "..."
                ▼
   ┌─────────────────────────┐
   │   Local repository      │  .git/objects — your full history (DAG of commits)
   └────────────┬────────────┘
                │ git push origin main
                ▼
   ┌─────────────────────────┐
   │   Remote repository     │  GitHub / GitLab / Bitbucket — shared with the team
   └─────────────────────────┘
```

### The Four Object Types

Inside `.git/objects` Git stores four kinds of objects, each identified by a SHA-1 hash of its contents:

| Object | What It Stores |
|--------|----------------|
| **blob** | The raw contents of a single file (no filename, no path — just bytes). |
| **tree** | A directory listing — filenames plus the blob/tree hashes they point to. |
| **commit** | A snapshot pointer (root tree hash) + parent commit hash(es) + author, committer, message. |
| **tag** | A named pointer to a specific commit, often with a message and a signature (annotated tags). |

A commit is **not a diff** — it's a full snapshot. Identical files at different paths share one blob. Identical directories share one tree. That's why a 10-year-old Git repo with a million commits is often only a few hundred MB.

### Refs and the DAG

A **ref** is a human-readable name (`main`, `feature/login`, `v1.2.0`) stored as a tiny text file in `.git/refs/` containing a commit hash. The special ref `HEAD` points to "wherever you are right now" — usually a branch ref. Every commit also points back to its parent(s), forming a **DAG (directed acyclic graph)** — Git's history is a graph, not a list.

> [!TIP]
> Type `git cat-file -p HEAD` in any repo to literally see the contents of your most recent commit object. `git cat-file -p <tree-hash>` shows the tree. It's a useful party trick — and it makes the "Git is just a content-addressed filesystem" fact click.

---

## Pick Your Path

Git is mandatory for every developer — but most people don't need every phase equally. Pick the track that matches your goal. Each one tells you what to focus on, what to skip, and what to do next.

### Track 1 — Beginner / First-Time Git User (1–2 weeks)
**Goal:** stop being terrified of `git` and ship your first commit + first PR.

Do **Phases 1–5** in order. Get comfortable with `init`, `add`, `commit`, `push`, `pull`, and basic branching. Build a personal "hello, GitHub" repo, push it, and clone it on a second machine. Don't worry about rebase yet. By the end you should be able to fork a tutorial repo, fix a typo, and open your first PR.

### Track 2 — Solo Dev / Side Project Builder (2–3 weeks)
**Goal:** you build personal projects and want a clean history without the team workflow drama.

Do **Phases 1–7** plus **Phase 11 (Hooks)**. Skip team workflows for now. Focus on writing good commit messages, using branches per feature, learning `git stash`, and setting up a basic pre-commit hook (Prettier or lint). Tag your releases with semantic versioning so future-you can find that "version that worked."

### Track 3 — Team Member / Junior Dev (3–4 weeks)
**Goal:** you just joined a team. Don't be the one who breaks `main`.

Do **all 13 phases** in order, with extra time on **Phase 4 (Branching)**, **Phase 6 (Rewriting History)**, **Phase 8 (Workflows)**, and **Phase 9 (PRs & Code Review)**. Practice `rebase -i` until you're comfortable squashing 5 messy commits into 1 clean one. Learn your team's workflow (Git Flow vs trunk-based vs GitHub Flow) and respect it. Read `git log --oneline --graph --all` until it makes sense at a glance.

### Track 4 — Power User / Tech Lead (4–6 weeks)
**Goal:** you're the person teammates ping when something is broken.

All phases, but go deep on **Phase 6 (Rewriting History)**, **Phase 10 (Bisect, Worktree, Reflog)**, **Phase 11 (Hooks & Automation)**, and **Phase 12 (Ecosystem)**. Learn `bisect`, `worktree`, `reflog`, partial clone, sparse checkout, and `git filter-repo`. Master one CI provider (GitHub Actions). Be the person who can recover a "lost" branch, untangle a botched merge, and explain what just happened with a calm voice.

### Track 5 — Open Source Contributor (3–5 weeks)
**Goal:** ship PRs to projects you don't own.

Phases 1–9 plus **Phase 12 (Ecosystem)**. Learn the fork → branch → push → PR loop until it's muscle memory. Master `git rebase upstream/main`, conflict resolution, and writing PRs maintainers will actually merge. Practice on a "good first issue" in a real project. Get one PR merged into a popular repo — it goes on your resume.

> [!TIP]
> Whichever track you pick, **Phase 4 (Branching & Merging)** and **Phase 6 (Rewriting History)** are the two phases every track depends on — read them carefully. Most "Git is scary" feelings come from skipping these.

---

## Prerequisites

> [!NOTE]
> Git requires **zero programming experience**. You don't need to know any language to learn Git. You only need a terminal and the patience to type a few commands.

- A computer (Windows, Mac, or Linux)
- A terminal (Terminal on Mac/Linux, [Windows Terminal](https://aka.ms/terminal) or Git Bash on Windows)
- A text editor — [VS Code](https://code.visualstudio.com/) recommended (free, has built-in Git support)
- A [GitHub account](https://github.com/) (free) — you'll need it to push code anywhere shared
- Comfort with basic commands — `cd`, `ls`/`dir`, `mkdir`, `rm`

That's it. Git itself you'll install in Phase 1.

---

## How to Use This Syllabus

1. **Run every command yourself.** Reading `git rebase -i HEAD~3` is not the same as doing it. Make a throwaway repo (`mkdir gitlab && cd gitlab && git init`) and break things on purpose.
2. **Don't skip phases.** Each one builds on the last. If Phase 2 (the three trees) is shaky, Phase 6 (rewriting history) will feel impossible.
3. **Memorize `git status` and `git log --oneline --graph --all`.** These two commands are your eyes. Run them constantly.
4. **Embrace the reflog.** Once you internalize that *Git almost never permanently loses data*, you stop being scared of destructive commands. Phase 10 covers this — read it carefully.
5. **Configure aliases.** `co` for `checkout`, `lg` for a pretty log, `s` for `status`. Saves thousands of keystrokes per year. Phase 1 sets these up.
6. **Use the CLI, not just the GUI.** GUIs (SourceTree, GitKraken, VS Code's panel) are fine for daily flow — but you must understand what's happening underneath. Interviews ask CLI questions.
7. **Push to GitHub from day one.** Public repos by default. Build a "commit graph" you're proud of.

### Recommended Pace

| Track | Time | Phases | Outcome |
|-------|------|--------|---------|
| **Fast (experienced dev, learning Git properly)** | 1 week | All 13 phases | Comfortable with rebase, reflog, CI |
| **Regular (junior dev / fresher)** | 3–4 weeks | All 13 phases | Team-ready Git skills |
| **Deep (going for senior / OSS maintainer)** | 5–6 weeks | All 13 phases + projects | Can teach Git to others |

> [!TIP]
> Estimated times in each phase assume ~1–2 hours of focused practice per day. If you can only put in 30 minutes/day, multiply by 4. Depth beats speed.

---

## Phase 1: Getting Started

![Phase](https://img.shields.io/badge/Phase-1%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 2-3 Hours](https://img.shields.io/badge/Time-2--3%20Hours-yellow)

> Install Git, configure your identity, and create your first repository.

**What this phase is about.** Before you can track a single change, you need Git installed, your name and email configured (every commit you ever make is signed with these), and a sane set of defaults. This phase walks through installing Git on every OS, setting global config (user.name, user.email, default branch, editor, line endings), generating an SSH key for GitHub, and creating your very first repository with `git init`. By the end you'll have a working Git setup and a "hello, world" repo on disk.

**Why it matters.** Skip this phase and you'll spend the next twelve fighting tooling. A misconfigured `core.autocrlf` on Windows breaks every diff. Wrong email on commits and your contributions don't count on GitHub. No SSH key and you'll type your password every push. Get the setup right once and never think about it again.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Installing Git | macOS (`brew install git`), Windows ([Git for Windows](https://gitforwindows.org/)), Linux (`apt`, `dnf`, `pacman`); verify with `git --version` |
| 2 | Configuring Identity | `git config --global user.name`, `git config --global user.email` — the email *must* match your GitHub email |
| 3 | Default Branch Name | `git config --global init.defaultBranch main` — modern default (replaces `master`) |
| 4 | Choosing an Editor | `git config --global core.editor` — set to `code --wait`, `vim`, or `nano` for commit messages |
| 5 | Line Endings | `core.autocrlf=input` (Mac/Linux), `core.autocrlf=true` (Windows) — prevents the cross-platform CRLF nightmare |
| 6 | SSH Keys for GitHub | `ssh-keygen -t ed25519`, add public key to GitHub, test with `ssh -T git@github.com` |
| 7 | HTTPS vs SSH | Trade-offs; HTTPS uses Personal Access Tokens, SSH uses keys; SSH is the daily-use default |
| 8 | Creating Your First Repo | `mkdir hello-git && cd hello-git && git init`; what `.git/` actually contains |
| 9 | The `.gitignore` File | Glob patterns to skip files (`node_modules/`, `.env`, `*.log`); generate one from [gitignore.io](https://www.toptal.com/developers/gitignore) |
| 10 | Aliases | `git config --global alias.s status`, `alias.lg "log --oneline --graph --all"` — short commands you'll use forever |

> [!TIP]
> The single most useful global config to set on day one:
> ```
> git config --global pull.rebase true
> ```
> This makes `git pull` rebase your local commits on top of remote changes instead of creating a merge commit. Cleaner history, fewer "Merge branch 'main' of github.com..." commits cluttering the log.

<details>
<summary><strong>Reference: Day-One Global Config</strong></summary>

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
git config --global pull.rebase true
git config --global push.autoSetupRemote true
git config --global rebase.autoStash true
git config --global rerere.enabled true

# Useful aliases
git config --global alias.s status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm "commit -m"
git config --global alias.lg "log --oneline --graph --all --decorate"
git config --global alias.last "log -1 HEAD --stat"
git config --global alias.unstage "reset HEAD --"
```

Inspect your config any time with `git config --global --list`. Stored in `~/.gitconfig` — feel free to edit by hand.

</details>

<details>
<summary><strong>Reference: Generate and Add an SSH Key to GitHub</strong></summary>

```bash
# 1. Generate a new ed25519 key
ssh-keygen -t ed25519 -C "you@example.com"

# 2. Start the SSH agent and add the key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# 3. Copy the public key
cat ~/.ssh/id_ed25519.pub
# Paste it into GitHub: Settings -> SSH and GPG Keys -> New SSH Key

# 4. Verify
ssh -T git@github.com
# Hi <username>! You've successfully authenticated...
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Install Git and verify with `git --version`
- [ ] Configure global `user.name` and `user.email` (matching your GitHub email)
- [ ] Generate an SSH key and add it to GitHub; `ssh -T git@github.com` succeeds
- [ ] Create your first repo with `git init` and inspect `.git/` to see what's inside
- [ ] Set at least 5 useful aliases

</details>

---

## Phase 2: The Three Trees & Basic Workflow

![Phase](https://img.shields.io/badge/Phase-2%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Master the working directory → staging → repository workflow that drives everything else.

**What this phase is about.** Every Git command you ever run is, ultimately, moving content between the three "trees" — your **working directory** (files you edit), the **staging area** (also called the index — what's lined up for the next commit), and your **local repository** (the permanent history in `.git/objects`). This phase teaches the core verbs (`git status`, `git add`, `git commit`, `git diff`, `git rm`, `git mv`, `git restore`) and what each one does to which tree.

**Why it matters.** "I don't understand why my changes didn't get committed" is the #1 confusion among beginners. The cause is always the same: not understanding that **edits in the working directory are invisible to commits until you `git add` them**. Once the three-trees model clicks, you stop fighting Git. Bonus: `git status` becomes the most useful command in your toolbox — it tells you exactly what state every file is in.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | The Three Trees | Working directory, staging area (index), local repository — and what lives where |
| 2 | `git status` | Decoding "Untracked", "Changes not staged", "Changes to be committed", "nothing to commit" |
| 3 | `git add` | Staging individual files, all changes (`git add .`), interactive staging (`git add -p`) |
| 4 | `git commit` | Writing a commit, `-m` for inline message, `-am` for tracked-file shortcut, multi-line commits |
| 5 | Anatomy of a Commit | Author, committer, timestamp, parent SHA, tree SHA, commit message — what's stored |
| 6 | Writing Good Messages | The "50/72 rule": 50-char subject, blank line, 72-char wrapped body; imperative mood ("Add feature" not "Added feature") |
| 7 | `git diff` | Working dir vs index (`git diff`), index vs HEAD (`git diff --staged`), HEAD vs HEAD~1 (`git diff HEAD~1`) |
| 8 | `git rm` and `git mv` | Removing/renaming tracked files — Git records moves automatically when content is similar |
| 9 | `git restore` | Modern undo: `git restore <file>` (discard working changes), `git restore --staged <file>` (unstage) |
| 10 | Untracked vs Ignored | Untracked = Git sees it but doesn't track it; ignored = matched by `.gitignore` |
| 11 | Atomic Commits | One logical change per commit — makes `git log`, `git revert`, `git bisect`, and code review all easier |

> [!IMPORTANT]
> **A commit is not your file. A commit is a snapshot of every tracked file in your repo at a point in time.** Even if you only changed `README.md`, the commit references the full tree. Git just deduplicates everything that didn't change. This is why "commits are cheap" — they barely cost any disk space.

<details>
<summary><strong>Reference: The Basic Daily Workflow</strong></summary>

```bash
# 1. See what changed
git status

# 2. Stage the changes you want to commit
git add file1.js file2.css
# or stage everything tracked + new
git add .
# or stage interactively (chunk-by-chunk)
git add -p

# 3. Commit with a message
git commit -m "Add login form validation"

# 4. Verify
git log --oneline -5
```

That four-step loop is 80% of daily Git usage. Master it before anything else.

</details>

<details>
<summary><strong>Reference: Anatomy of a Good Commit Message</strong></summary>

```
Add rate limiting to the login endpoint

The login API was vulnerable to brute-force attacks because there was
no rate limit. This adds a 5-attempts-per-minute limit per IP using
the existing Redis instance.

Refs: #482
```

Rules:
1. **Subject line** under 50 characters, no period, imperative mood ("Add", "Fix", "Refactor", not "Added", "Fixes", "Refactored").
2. **Blank line** between subject and body.
3. **Body** wrapped at ~72 chars, explains *why* and *what*, not *how* (the diff shows how).
4. **Reference issues** at the bottom (`Refs:`, `Fixes #123`, `Closes #456`).

Many teams adopt [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `chore:`, `docs:`, `refactor:`, `test:`. Required if you use `semantic-release`.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain the three trees and which command moves content between which trees
- [ ] Read `git status` output and predict what `git commit` will record
- [ ] Stage hunks selectively with `git add -p`
- [ ] Write 5 commit messages that follow the 50/72 rule
- [ ] Use `git diff` and `git diff --staged` correctly

</details>

---

## Phase 3: Inspecting History

![Phase](https://img.shields.io/badge/Phase-3%2F13-blue)
![Difficulty: Beginner](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Read the past — find when, why, and by whom every line of code was written.

**What this phase is about.** Once you have a few commits, you need to *read* them. Git ships with one of the most powerful history tools in any VCS: `git log` with dozens of formatting options, `git show` to view a single commit, `git diff` to compare any two points in time, and `git blame` to figure out who wrote each line of a file (and why). This phase covers all of them, plus the visual graph view that makes branch history finally make sense.

**Why it matters.** "Why is this code here?" is the question every developer asks daily — usually about code they themselves wrote six months ago. `git log -S "loginUser"` finds every commit that added or removed the string `loginUser`. `git blame` plus `git show <commit>` tells you the original PR, commit message, and author. Real teams treat history as documentation. So should you.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `git log` | Default view, `--oneline`, `-n 10` (last 10), `--since`/`--until`, `--author`, `--grep` |
| 2 | The Graph View | `git log --oneline --graph --all --decorate` — the single most useful log invocation |
| 3 | Custom Format | `--pretty=format:` to show whatever fields you want; alias it once and forget it |
| 4 | `git show` | Show a single commit's message, author, and full diff |
| 5 | `git diff` Power | `git diff <commit>..<commit>`, `git diff main..feature`, `git diff --stat` (file-level summary) |
| 6 | Searching by Content | `git log -S "<string>"` (pickaxe — finds commits adding/removing a string), `git log -G <regex>` |
| 7 | Searching by Path | `git log -- path/to/file` — history of a single file, even after renames (`--follow`) |
| 8 | `git blame` | Annotate each line with the commit that last changed it; ignore whitespace with `-w` |
| 9 | `git shortlog` | Group commits by author — useful for changelogs and "who's been busy lately" |
| 10 | References & Revisions | `HEAD`, `HEAD~3` (3 commits ago), `HEAD^` (parent), `main@{yesterday}`, `:/fix typo` |
| 11 | Revisiting Old States | `git checkout <commit>` (detached HEAD) — read-only time travel |

> [!TIP]
> Add this alias permanently: `git config --global alias.lg "log --oneline --graph --all --decorate"`. Now `git lg` gives you a beautiful colored graph of every branch and tag. You'll use it dozens of times a day.

<details>
<summary><strong>Reference: 10 git log Recipes</strong></summary>

```bash
# Last 10 commits, one line each
git log --oneline -10

# Beautiful graph of all branches (alias as 'git lg')
git log --oneline --graph --all --decorate

# Commits by a specific author this month
git log --author="Linus" --since="1 month ago"

# Commits whose message mentions "auth"
git log --grep="auth" -i

# Commits that added or removed the string "TODO"
git log -S "TODO"

# Commits that changed src/login.js, even after renames
git log --follow -- src/login.js

# Commits with file-level stats
git log --stat -5

# Commits showing each diff
git log -p -3

# Just the commits on this branch but not on main
git log main..HEAD

# Group by author with commit counts
git shortlog -sn
```

</details>

<details>
<summary><strong>Reference: git blame in Practice</strong></summary>

```bash
# Annotate every line of a file with last-change info
git blame src/auth.js

# Ignore whitespace-only changes (formatting commits)
git blame -w src/auth.js

# Skip "noise" commits listed in a file (Black/Prettier reformats)
git blame --ignore-revs-file .git-blame-ignore-revs src/auth.js

# Blame just lines 100-150
git blame -L 100,150 src/auth.js
```

GitHub also has a graphical blame at any file URL — append `/blame/<branch>/<path>`. But the CLI is faster once you know it.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Read `git log --oneline --graph --all` and understand what each line/decorator means
- [ ] Find the commit that introduced a specific string with `git log -S`
- [ ] Use `git blame` to find the original author of a line of code
- [ ] Compare two branches with `git diff main..feature --stat`
- [ ] Inspect a specific commit with `git show <hash>`

</details>

---

## Phase 4: Branching & Merging

![Phase](https://img.shields.io/badge/Phase-4%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Work on multiple things in parallel without stepping on anyone — including yourself.

**What this phase is about.** A **branch** in Git is a 41-byte text file pointing at a commit. That's it. Creating one is instant. Switching to one is instant. This is *the* feature that makes Git different from older VCS — branching is so cheap that you should branch constantly, for every feature, every bug fix, every experiment. This phase covers `git branch`, the modern `git switch`/`git restore` commands (since 2.23), `git merge` (fast-forward vs three-way), and the unavoidable: **conflict resolution**.

**Why it matters.** Every team workflow you'll ever encounter is built on branches. "Feature branches", "release branches", "hotfix branches", "trunk-based development" — all branching strategies. The single biggest difference between a junior and a senior is comfort with branches: a senior creates a branch the moment they start a task, a junior commits straight to `main` and creates messes. Be the senior.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What a Branch Really Is | A movable pointer to a commit; the `HEAD` ref tracks "the current branch" |
| 2 | Listing & Creating | `git branch` (list), `git branch <name>` (create), `git branch -d` (delete merged), `git branch -D` (force) |
| 3 | Switching Branches | Modern: `git switch <name>`, `git switch -c <name>` (create + switch); old: `git checkout` |
| 4 | `git checkout` vs `git switch`/`git restore` | Why Git split `checkout` into two — branch ops vs file ops |
| 5 | Fast-Forward Merge | When `main` hasn't moved, the merge is just "move the pointer forward". No merge commit. |
| 6 | Three-Way Merge | When both branches diverged, Git creates a merge commit with two parents |
| 7 | `--ff-only`, `--no-ff`, `--squash` | Three flavors of merge — pick deliberately, especially in PRs |
| 8 | Conflict Resolution | Conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), editing manually, `git add` to mark resolved |
| 9 | Merge Tools | `git mergetool`, VS Code's built-in 3-way view, [Meld](https://meldmerge.org/) |
| 10 | Aborting a Merge | `git merge --abort` — bail out cleanly when you realize you started the wrong merge |
| 11 | Renaming & Deleting Branches | `git branch -m newname`, `git push origin :oldname` (delete remote) |
| 12 | Stale Branch Hygiene | `git fetch --prune`, deleting merged branches; tools like `git-branchless` |

> [!IMPORTANT]
> **Never work directly on `main`.** Even on solo projects. Always create a branch (`git switch -c feature/login`), make commits there, then merge or PR back to `main`. This habit alone separates you from 80% of self-taught developers.

<details>
<summary><strong>Reference: The Feature Branch Workflow</strong></summary>

```bash
# Start a new feature
git switch main
git pull
git switch -c feature/add-search

# Make commits as you work
git add .
git commit -m "Add search input component"
git add .
git commit -m "Wire up search API call"

# Push to remote (sets upstream tracking)
git push -u origin feature/add-search

# When done, merge back to main (or open a PR)
git switch main
git pull
git merge --no-ff feature/add-search
git push

# Clean up
git branch -d feature/add-search
git push origin :feature/add-search
```

</details>

<details>
<summary><strong>Reference: Resolving a Merge Conflict</strong></summary>

```bash
git switch feature/login
git merge main
# CONFLICT (content): Merge conflict in src/auth.js
# Automatic merge failed; fix conflicts and then commit the result.

git status
# both modified:   src/auth.js
```

Open `src/auth.js` and find the conflict markers:

```
<<<<<<< HEAD
function login(user) { return api.post('/login', user); }
=======
function login(creds) { return fetch('/auth', { method: 'POST', body: creds }); }
>>>>>>> main
```

Edit the file to keep what you want, remove all three marker lines, save, then:

```bash
git add src/auth.js
git commit              # opens editor with default merge message
git lg                  # verify the merge commit appears
```

If you panic and want to start over: `git merge --abort`.

</details>

<details>
<summary><strong>Reference: Merge vs Squash vs Rebase (when to use which)</strong></summary>

| Strategy | Result | Use When |
|----------|--------|----------|
| **Merge (`--no-ff`)** | Preserves the feature branch as a "bubble", with a merge commit | You want full history of how a feature was built |
| **Fast-forward (`--ff-only`)** | No merge commit — just moves `main` forward | Linear history, branch had no parallel commits on `main` |
| **Squash (`--squash`)** | Collapses entire feature branch into 1 commit on `main` | Default for PRs in many teams — clean linear `main` |
| **Rebase + ff** | Replays feature commits on top of `main`, then fast-forwards | Linear history *and* preserves individual commits |

There is no universally right answer. Pick a team policy and stick to it.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Create, switch, and delete branches with `git switch` and `git branch`
- [ ] Explain fast-forward vs three-way merge with examples
- [ ] Resolve a merge conflict by hand (no GUI)
- [ ] Choose between merge, squash, and rebase for a given situation
- [ ] Abort a botched merge with `git merge --abort`

</details>

---

## Phase 5: Remote Repositories

![Phase](https://img.shields.io/badge/Phase-5%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Sync your work with the rest of the world via GitHub, GitLab, or any other remote.

**What this phase is about.** A **remote** is just another copy of your repo, usually on a server you can reach over the network. `origin` is the conventional name for the remote you cloned from. This phase covers `git clone`, `git remote`, `git fetch`, `git pull`, `git push`, tracking branches, the difference between HTTPS and SSH remotes, and the [GitHub CLI (`gh`)](https://cli.github.com/) which lets you create repos and PRs straight from your terminal.

**Why it matters.** Most "Git problems" are actually remote-sync problems — pushed to the wrong branch, pulled and got a weird merge commit, can't push because someone else pushed first. Once you understand that **a remote is just another set of branches with a prefix (`origin/main`)**, all of these stop being mysterious. You learn to think in terms of "what's on my local, what's on the remote, what's the difference?" and `git status` + `git log origin/main..HEAD` answer both.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Cloning a Repo | `git clone <url>` — copies the entire history; `--depth 1` for shallow clones |
| 2 | Listing Remotes | `git remote -v` — see all configured remotes and their URLs (`fetch` and `push`) |
| 3 | Adding & Removing | `git remote add upstream <url>`, `git remote remove <name>`, `git remote rename` |
| 4 | HTTPS vs SSH URLs | `https://github.com/user/repo.git` vs `git@github.com:user/repo.git`; auth differences |
| 5 | `git fetch` | Downloads remote changes but does NOT modify your branches; updates `origin/*` refs |
| 6 | `git pull` | `fetch` + `merge` (or `rebase` if you set `pull.rebase=true`) into your current branch |
| 7 | `git push` | Send local commits to the remote; `-u`/`--set-upstream` ties local branch to remote branch |
| 8 | Tracking Branches | `origin/main` is a *remote-tracking branch* — Git's local cache of "where main was on origin last time we talked" |
| 9 | Force Pushing | `git push --force-with-lease` — the *safer* force push; never use plain `--force` on shared branches |
| 10 | Personal Access Tokens | GitHub deprecated password auth in 2021; HTTPS now uses tokens (or SSH keys) |
| 11 | The `gh` CLI | `gh repo create`, `gh pr create`, `gh pr checkout 123` — GitHub from the terminal |
| 12 | Multiple Remotes | The fork workflow: `origin` = your fork, `upstream` = the original repo |
| 13 | Pruning Stale Remotes | `git fetch --prune` — delete local refs to branches deleted on the remote |

> [!WARNING]
> **Never `git push --force` to `main` or any shared branch.** Use `--force-with-lease` instead — it refuses to push if the remote branch has new commits you don't have locally, preventing you from blowing away a teammate's work. Many teams ban force-push to `main` entirely via branch protection rules.

<details>
<summary><strong>Reference: First-Time Push to a New GitHub Repo</strong></summary>

```bash
# Locally
git init
git add .
git commit -m "Initial commit"

# Create the GitHub repo (using gh CLI)
gh repo create my-project --public --source=. --remote=origin --push

# Or, if you created the repo on github.com manually
git remote add origin git@github.com:you/my-project.git
git branch -M main
git push -u origin main
```

The `-u` flag sets the upstream tracking — after this, `git push` and `git pull` know where to go without arguments.

</details>

<details>
<summary><strong>Reference: fetch vs pull (the important distinction)</strong></summary>

| | `git fetch` | `git pull` |
|--|-------------|------------|
| Downloads commits? | Yes | Yes |
| Modifies your current branch? | No | Yes (merges or rebases) |
| Safe to run anytime? | Yes — never destructive | No — can cause unexpected merges |
| When to use | "What's new on the remote?" | "Sync this branch with the remote now" |

A common pro habit: `git fetch` first, look at `git log HEAD..origin/main` to see *what's incoming*, then decide to merge or rebase explicitly. Beginners often `git pull` blindly and create surprise merge commits.

</details>

<details>
<summary><strong>Reference: The Fork-and-Contribute Workflow</strong></summary>

```bash
# 1. Fork the repo on GitHub UI, then clone YOUR fork
git clone git@github.com:you/some-project.git
cd some-project

# 2. Add the original repo as 'upstream'
git remote add upstream git@github.com:original-org/some-project.git
git remote -v
# origin    git@github.com:you/some-project.git (fetch/push)
# upstream  git@github.com:original-org/some-project.git (fetch/push)

# 3. Stay in sync with upstream
git fetch upstream
git switch main
git rebase upstream/main
git push origin main

# 4. Branch, work, push, PR
git switch -c fix/typo-in-readme
# ... edit, commit ...
git push -u origin fix/typo-in-readme
gh pr create --fill   # opens a PR using your latest commit message
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Clone a repo, list remotes, add and remove remotes
- [ ] Explain the difference between `fetch` and `pull` to a beginner
- [ ] Push a branch to a remote with `-u` for the first time
- [ ] Set up the fork-and-contribute workflow (origin + upstream)
- [ ] Use `--force-with-lease` to safely amend a pushed commit on a personal branch

</details>

---

## Phase 6: Rewriting History

![Phase](https://img.shields.io/badge/Phase-6%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 5-6 Hours](https://img.shields.io/badge/Time-5--6%20Hours-yellow)

> Edit the past safely — squash messy commits, fix typos, restructure a feature branch.

**What this phase is about.** Git is the only mainstream VCS that lets you go back and *edit history*. Forgot to add a file to your last commit? `git commit --amend`. Accidentally committed to the wrong branch? `git reset`. Made 12 messy "wip" commits and want them as one clean commit? Interactive rebase. This phase covers `amend`, `reset` (`--soft`/`--mixed`/`--hard`), `revert`, `rebase`, and the most powerful tool of all: **interactive rebase** with squash, fixup, reword, edit, and drop.

**Why it matters.** Clean history is a professional courtesy — to your reviewers, your future self, and `git bisect`. The difference between "this PR has 47 commits including 8 'fix typo' messages" and "this PR has 3 logical commits each implementing one piece" is interactive rebase. Senior devs treat their commit history as a presentation: each commit is a slide that should make sense in isolation.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `git commit --amend` | Modify the *last* commit's message and/or contents — your most-used history-rewrite |
| 2 | `git reset --soft` | Move HEAD back; keep changes staged. Use to "uncommit" but keep work. |
| 3 | `git reset --mixed` (default) | Move HEAD back; unstage changes. Use to "uncommit and unstage but keep files." |
| 4 | `git reset --hard` | Move HEAD back; **destroy** working dir + index changes. The dangerous one. |
| 5 | `git revert` | Create a *new* commit that undoes a previous commit. Safe on shared branches. |
| 6 | `git rebase <branch>` | Replay your branch's commits on top of another branch — linear history |
| 7 | Interactive Rebase | `git rebase -i HEAD~5` — opens an editor to reorder, squash, fixup, reword, edit, or drop commits |
| 8 | `pick` / `reword` / `edit` | Three of the seven actions — keep, change message, or pause to amend |
| 9 | `squash` vs `fixup` | `squash` keeps both messages; `fixup` discards the squashed commit's message |
| 10 | Autosquash | `git commit --fixup=<sha>` then `git rebase -i --autosquash` — auto-arranges fixup commits |
| 11 | Splitting a Commit | During interactive rebase: `edit`, `git reset HEAD~`, then re-add and re-commit in pieces |
| 12 | The Golden Rule | **Never rewrite history that you've pushed to a shared branch.** Force-pushing rewrites breaks teammates' clones. |
| 13 | Recovery via Reflog | `git reflog` saves you from any history-rewrite disaster — covered in Phase 10 |

> [!CAUTION]
> `git reset --hard` and `git push --force` are the two commands that have caused the most "I lost my work" Slack messages in software history. Always run `git status` and `git log` first. Always prefer `--force-with-lease` over `--force`. Always remember: **`git reflog` can save you from almost anything** — see Phase 10.

<details>
<summary><strong>Reference: Three flavors of git reset</strong></summary>

| Command | Working dir | Index (staging) | HEAD |
|---------|:-----------:|:---------------:|:----:|
| `git reset --soft <commit>` | unchanged | unchanged | moved |
| `git reset --mixed <commit>` (default) | unchanged | reset to commit | moved |
| `git reset --hard <commit>` | reset to commit | reset to commit | moved |

Quick mental model: `--soft` keeps your work staged, `--mixed` keeps your work but unstages it, `--hard` deletes your work. Pair this with `HEAD~1` to "undo last commit" with the granularity you want.

</details>

<details>
<summary><strong>Reference: Interactive Rebase Cheat Sheet</strong></summary>

Run `git rebase -i HEAD~5` to edit the last 5 commits. You'll see:

```
pick a1b2c3d Add login button
pick e4f5g6h fix typo
pick i7j8k9l another fix
pick m1n2o3p Wire up auth API
pick q4r5s6t WIP debugging
```

Replace `pick` on each line with one of:

| Action | What It Does |
|--------|--------------|
| `pick` (`p`) | Keep the commit as-is |
| `reword` (`r`) | Keep the commit but change its message |
| `edit` (`e`) | Pause here so you can `git commit --amend` or split |
| `squash` (`s`) | Combine into the previous commit, merging both messages |
| `fixup` (`f`) | Combine into the previous commit, **discard** this commit's message |
| `drop` (`d`) | Delete this commit entirely |

Save and quit. Git replays each commit applying your changes. If conflicts arise, fix them, `git add`, then `git rebase --continue`. Bail out anytime with `git rebase --abort`.

</details>

<details>
<summary><strong>Reference: revert vs reset (when to use which)</strong></summary>

| | `git revert <commit>` | `git reset --hard <commit>` |
|--|----------------------|------------------------------|
| Modifies history | No — adds a new commit | Yes — moves the branch pointer back |
| Safe on shared branches | **Yes** — preferred | No — requires force-push |
| Use when | Undoing a commit on `main` | Undoing local-only commits |
| Result | History shows the bad commit *and* the revert | History shows only the good commits |

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `git commit --amend` to fix the last commit's message and contents
- [ ] Explain when to use `--soft`, `--mixed`, and `--hard` reset
- [ ] Squash 5 messy commits into 2 logical commits using `git rebase -i`
- [ ] Use `git revert` to undo a commit on a shared branch
- [ ] State the Golden Rule of rebase and explain why force-push to `main` is banned

</details>

---

## Phase 7: Stash, Cherry-pick & Tags

![Phase](https://img.shields.io/badge/Phase-7%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Three small but indispensable tools: park work-in-progress, copy a single commit between branches, and mark releases.

**What this phase is about.** This phase covers three semi-related power tools. **`git stash`** lets you set aside uncommitted changes when you suddenly need to switch branches ("hot fix on main, can't commit half-done work yet"). **`git cherry-pick`** copies a specific commit from one branch onto another (perfect for backporting bug fixes from `main` to a release branch). **Tags** mark specific commits as named releases (`v1.0.0`, `v2.4.7`) — what every npm package, GitHub Release, and Docker image is built on.

**Why it matters.** Stash is a lifesaver three times a week. Cherry-pick is how production hotfixes propagate. Tags are how the world knows what version your software is at — they trigger CI release pipelines, populate GitHub Releases, and feed `semantic-release`. Skipping any of these three leaves a hole in your real-world Git ability.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `git stash push` | Save uncommitted changes to a stack and restore a clean working dir |
| 2 | Naming Stashes | `git stash push -m "WIP login form"` — never have to guess what `stash@{0}` is |
| 3 | `git stash list` | List all stashes; `git stash show -p stash@{1}` to see contents |
| 4 | `git stash pop` vs `apply` | `pop` = apply + delete stash; `apply` = apply but keep |
| 5 | Stashing Untracked Files | `git stash push -u` — include new files; `-a` includes ignored too |
| 6 | Partial Stashes | `git stash push -p` — chunk-by-chunk, just like `git add -p` |
| 7 | `git cherry-pick <sha>` | Apply the diff of a single commit onto your current branch |
| 8 | Cherry-pick Conflicts | Same as merge conflicts; `--abort`, `--continue`, `--skip` available |
| 9 | Cherry-pick Ranges | `git cherry-pick A..B` — copy a range of commits |
| 10 | Lightweight Tags | `git tag v1.0.0` — just a pointer to a commit; no metadata |
| 11 | Annotated Tags | `git tag -a v1.0.0 -m "Release 1.0.0"` — full object with message, author, date, signature |
| 12 | Pushing Tags | `git push origin v1.0.0` (one tag) or `git push --tags` (all tags) |
| 13 | Semantic Versioning | `MAJOR.MINOR.PATCH` — when to bump each; pre-releases (`v1.0.0-rc.1`) |
| 14 | Signed Tags | `git tag -s v1.0.0` — GPG-signed tags for verified releases |

> [!TIP]
> **Always use annotated tags for releases.** Lightweight tags are fine for personal markers, but annotated tags carry author, date, and message — they show up properly on GitHub, in `git describe`, and in CI release pipelines. The convention is universal.

<details>
<summary><strong>Reference: Daily Stash Workflow</strong></summary>

```bash
# You're mid-work and a hotfix lands on main
git status
# Changes not staged...

git stash push -m "WIP refactoring AuthService"
git switch main
git pull
# ... fix the hotfix ...
git switch -c hotfix/critical-bug
# ... commit, push, PR ...

# Back to your work
git switch feature/refactor-auth
git stash list
# stash@{0}: On feature/refactor-auth: WIP refactoring AuthService
git stash pop
```

If `pop` causes conflicts, resolve them, `git add`, and the stash is automatically dropped (or use `apply` to keep the stash entry).

</details>

<details>
<summary><strong>Reference: Backporting a Fix with Cherry-pick</strong></summary>

```bash
# You fixed a bug on main, but v2 customers are on the release/v2 branch
git switch main
git log --oneline -1
# a1b2c3d Fix null pointer in checkout flow

git switch release/v2
git cherry-pick a1b2c3d
# [release/v2 e4f5g6h] Fix null pointer in checkout flow

git push
```

The fix now exists on both branches as separate commits — different SHAs, same content.

</details>

<details>
<summary><strong>Reference: Tagging a Release</strong></summary>

```bash
# Annotated tag at HEAD
git tag -a v1.4.0 -m "Release v1.4.0 — adds dark mode and SSO"

# Push it
git push origin v1.4.0

# List tags
git tag --list "v1.*"

# See tag details
git show v1.4.0

# Delete a tag (locally + remotely)
git tag -d v1.4.0
git push origin :refs/tags/v1.4.0
```

For automated tagging based on Conventional Commits, see [`semantic-release`](https://semantic-release.gitbook.io/) in Phase 11.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Stash and pop a partial change (`git stash push -p`)
- [ ] Cherry-pick a commit from `main` onto a release branch
- [ ] Resolve a cherry-pick conflict and continue
- [ ] Create both a lightweight and an annotated tag; push both
- [ ] Explain semantic versioning and pick the right bump for a sample changelog

</details>

---

## Phase 8: Workflows

![Phase](https://img.shields.io/badge/Phase-8%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> The team rules of the road — Git Flow, GitHub Flow, Trunk-Based Development.

**What this phase is about.** Git itself is just plumbing — branches, commits, merges. **Workflows** are the conventions teams adopt on top: which branches are sacred, who can push where, what merges back into what, when to release. The three big workflows are **Git Flow** (heavy, multiple long-lived branches — popular for desktop software with versioned releases), **GitHub Flow** (light, only `main` is long-lived, everything else is short PR branches — what most modern web teams use), and **Trunk-Based Development** (similar to GitHub Flow, even shorter-lived branches, behind feature flags — how Google, Facebook, and many fintechs work).

**Why it matters.** Joining a new team and not knowing their workflow is the fastest way to break `main`. Some shops branch off `develop`, some off `main`. Some require linear history, some require merge commits. Some allow direct push to `main`, most ban it. This phase teaches the three dominant patterns so you walk into any team and immediately know what's happening.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | Git Flow | `main`, `develop`, `feature/*`, `release/*`, `hotfix/*`; complex but explicit |
| 2 | When Git Flow Wins | Versioned products with multiple supported releases (libraries, desktop apps, embedded) |
| 3 | GitHub Flow | Only `main` is long-lived; every change goes through a PR from a short branch |
| 4 | When GitHub Flow Wins | Continuously deployed web apps — most SaaS products in 2026 |
| 5 | Trunk-Based Development | All devs commit to `main` (or merge daily); incomplete features hide behind feature flags |
| 6 | When TBD Wins | High-velocity teams shipping multiple times a day; requires great test coverage |
| 7 | Feature Branches | Short-lived, named clearly (`feature/`, `fix/`, `chore/`); merge or PR back daily |
| 8 | Long-Lived Branches Are Bad | Why you should rebase or merge `main` into your feature branch *daily* |
| 9 | Release Branches | When to use them, how to backport hotfixes, when they become technical debt |
| 10 | Branch Protection | GitHub/GitLab settings: require PR reviews, status checks, no force-push, no direct push |
| 11 | Code Owners | `CODEOWNERS` file — auto-assign reviewers based on changed paths |
| 12 | Stacked PRs | Modern workflow: a chain of small dependent PRs (tools: [Graphite](https://graphite.dev/), [git-spice](https://abhinav.github.io/git-spice/)) |

> [!IMPORTANT]
> If you join a new team and have one question, ask: **"What's our branching workflow?"** A good answer takes 30 seconds: "GitHub Flow — branch from main, PR to main, squash-merge, delete branch. CI must pass and one approval required." If the answer is fuzzy, that's a sign of bigger team-process problems.

<details>
<summary><strong>Reference: Git Flow at a Glance</strong></summary>

```
main      ───●──────────────●─────●────────●──   (production releases, tagged)
              \             /     /        /
release/1.0    ●─●────────●     /        /     (release prep / bugfixes)
                \              /        /
develop  ─────●──●──●──●──●──●─────●──●        (integration of all features)
                  \      \              \
feature/login      ●─●─●  \              \    (feature work; merges back to develop)
feature/billing             ●─●─●          \
hotfix/v1.0.1                               ●  (emergency fix from main, merged to both)
```

- `main` only contains release-tagged commits.
- `develop` is integration; features merge here.
- `release/*` is a stabilization period before a tag.
- `hotfix/*` branches off `main`, gets merged back into both `main` and `develop`.

Good for shrink-wrapped products. Overkill for most web apps.

</details>

<details>
<summary><strong>Reference: GitHub Flow at a Glance</strong></summary>

```
main  ─●──●──●────────●──●────────●──●──●──   (always deployable)
        \              \              \
        ●─●─PR          ●─●─PR        ●─PR
        feature/login   fix/cors      chore/deps
```

The whole rulebook fits on a card:
1. `main` is always deployable.
2. Branch from `main` for any change.
3. Push and open a PR early (even as a draft).
4. Merge to `main` only after review + CI passes.
5. Deploy `main` to production immediately (or on next scheduled push).

This is what most modern web teams do. It's what you'll meet at 80% of jobs.

</details>

<details>
<summary><strong>Reference: Trunk-Based Development at a Glance</strong></summary>

```
main  ─●──●──●──●──●──●──●──●──●──●──●──●──   (everyone commits here, multi/day)
         ↑           ↑              ↑
         feature flag toggles incomplete features off in production
```

- Branches live hours to a day, not weeks.
- Big features hide behind feature flags ([Unleash](https://www.getunleash.io/), [LaunchDarkly](https://launchdarkly.com/), [PostHog](https://posthog.com/)).
- Requires strong CI, strong tests, strong feature-flag discipline.
- Used by Google, Facebook, Stripe, and most other "ships continuously" companies.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Explain Git Flow, GitHub Flow, and Trunk-Based Development to a teammate
- [ ] Pick the right workflow for: a SaaS web app, a versioned npm library, a high-velocity fintech
- [ ] Configure branch protection on a GitHub repo (require PR + 1 review + passing CI)
- [ ] Add a `CODEOWNERS` file for at least 2 paths
- [ ] State why long-lived feature branches are an anti-pattern

</details>

---

## Phase 9: Pull Requests & Code Review

![Phase](https://img.shields.io/badge/Phase-9%2F13-blue)
![Difficulty: Intermediate](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> The single most important skill for working on a team — opening, reviewing, and merging great PRs.

**What this phase is about.** A **Pull Request** (PR) on GitHub — also called a **Merge Request** (MR) on GitLab — is the formal mechanism for asking "please merge my branch into yours." On top of that, PRs are where modern code review happens: line-level comments, suggestions, approvals, automated checks (CI, linters, security scanners), and the discussion thread that becomes the project's institutional memory. This phase covers opening a PR (UI and CLI), writing a great PR description, draft PRs, requesting reviews, line-level comments, the suggestion feature, resolving conflicts in a PR, and merging strategies (merge / squash / rebase).

**Why it matters.** Code review takes more developer hours than coding does at most teams. Becoming great at PRs — both writing them and reviewing them — is the highest-leverage skill in this entire syllabus. A junior writes a PR titled "Updates" with no description. A senior writes a PR with a clear title, a description that explains *why*, screenshots, a test plan, and links to the relevant issue. Be the senior.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What a PR Actually Is | A request to merge a branch + a discussion thread + automated checks; not a Git feature, a *platform* feature |
| 2 | Opening a PR | UI: GitHub/GitLab "New Pull Request"; CLI: `gh pr create` (also `glab mr create`) |
| 3 | Writing a Great Description | Title (imperative, short), summary, screenshots, test plan, link to issue (`Closes #123`) |
| 4 | PR Templates | `.github/PULL_REQUEST_TEMPLATE.md` — standardize what every PR description must include |
| 5 | Draft PRs | Mark a PR as draft to signal "don't review yet, but CI can run" |
| 6 | Requesting Reviews | `@mention` reviewers; `CODEOWNERS` auto-assigns based on file paths |
| 7 | Line-Level Comments | Click a line in the diff to leave a comment scoped to that exact line |
| 8 | Suggestions | GitHub's `suggestion` block — reviewer can write "the code I'd like instead" and you click "Commit" |
| 9 | Resolving Conflicts in a PR | Conflicts shown in the PR; small ones fix in the web editor, big ones rebase locally |
| 10 | Re-Review | After pushing changes, request re-review from the same people |
| 11 | Merging | Three buttons: **Create a merge commit** / **Squash and merge** / **Rebase and merge** |
| 12 | After Merge | GitHub auto-closes linked issues; delete the branch (auto-delete is a setting) |
| 13 | The Two-Person Rule | Why even solo team leads should require one approver — catches mistakes, spreads knowledge |

> [!TIP]
> The single best PR you can write: **small** (under ~400 lines), **focused** (one logical change), with a **description that answers "why"** (the code answers "what"). PRs that hit all three get reviewed in minutes. Mega-PRs with no description sit for days.

<details>
<summary><strong>Reference: Anatomy of a Great PR</strong></summary>

**Title:** `feat(auth): add rate limiting to login endpoint`

**Description:**

```
## Summary
The login API was vulnerable to brute-force attacks because there was no
rate limit. This PR adds a 5-attempts-per-minute-per-IP limit using the
existing Redis instance.

## Changes
- Added `rateLimit` middleware in `src/middleware/rateLimit.ts`
- Wired it into the login route only (not signup yet — see #485)
- Added unit tests + an integration test that asserts 429 after 5 hits

## Screenshots
[GIF showing the 429 response in DevTools]

## Test plan
- [x] Unit tests pass (`npm test`)
- [x] Integration tests pass
- [x] Manually verified 6th attempt returns 429

Closes #482
```

That's it. 30 seconds to write, hours saved in review.

</details>

<details>
<summary><strong>Reference: Opening a PR with the gh CLI</strong></summary>

```bash
# Create the PR with a title and inline body
gh pr create --title "feat(auth): rate limit login" --body "Closes #482

Adds a 5/min/IP rate limit using the existing Redis instance."

# Or, use --fill to auto-fill from your last commit message
gh pr create --fill

# Open it as a draft
gh pr create --draft --fill

# View an existing PR in the browser
gh pr view 123 --web

# Check out a teammate's PR locally to test it
gh pr checkout 123
```

GitLab's equivalent is [`glab`](https://gitlab.com/gitlab-org/cli) — `glab mr create`, `glab mr checkout 123`. Same shape.

</details>

<details>
<summary><strong>Reference: Merge Strategies in PRs</strong></summary>

| Strategy | What It Does | Best For |
|----------|--------------|----------|
| **Merge commit** | Adds a merge commit; preserves all branch commits | Long-lived feature branches where each commit matters |
| **Squash and merge** | Collapses the entire PR into 1 commit on `main` | Most teams' default — `main` stays linear and clean |
| **Rebase and merge** | Replays each PR commit onto `main` linearly | When you've curated commits with `rebase -i` |

The one rule: **pick a strategy and stick to it across the project.** Mixed strategies make `git log` confusing.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Open a PR with `gh pr create` (not the web UI)
- [ ] Write a PR description that includes summary, screenshots, and a test plan
- [ ] Leave a line-level comment with a `suggestion` block
- [ ] Resolve a merge conflict directly in a PR
- [ ] Pick the right merge strategy (merge / squash / rebase) for a given situation

</details>

---

## Phase 10: Advanced — Bisect, Worktree, Reflog

![Phase](https://img.shields.io/badge/Phase-10%2F13-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Three power tools that turn you from competent into the senior who saves the day.

**What this phase is about.** This phase covers Git's most powerful debugging and recovery tools — the ones that come up in interviews and in real emergencies. **`git bisect`** binary-searches your history to find the exact commit that introduced a bug. **`git worktree`** lets you check out multiple branches into multiple directories simultaneously (no more stashing every time you need to look at `main`). And **`git reflog`** — the most important command nobody teaches juniors — keeps a local log of every move `HEAD` has made for ~90 days, letting you recover from "I `reset --hard`-ed and lost everything" disasters.

**Why it matters.** This is what separates senior from junior. When a teammate panics in Slack — "I deleted my branch and it's gone!" — the senior says "calm down, run `git reflog`" and walks them through recovery. When QA says "this used to work last month but doesn't now" the senior runs `git bisect` and hands back the exact culprit commit in 5 minutes. Master these three commands and you become the team's Git oracle.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | `git bisect start` | Begin a bisect session — Git checks out a midpoint commit between known good and bad |
| 2 | `git bisect good` / `bad` | Mark each midpoint after testing; Git narrows the range with binary search |
| 3 | `git bisect reset` | End the session, return to where you were |
| 4 | Automated Bisect | `git bisect run <script>` — Git auto-runs your test on each commit (perfect with CI) |
| 5 | When Bisect Shines | "It worked last month, doesn't now" — find the exact breaking commit in `O(log n)` |
| 6 | `git worktree add` | Check out a second branch into a new directory without re-cloning |
| 7 | Worktree Use Cases | Long-running build vs hotfix; review a teammate's PR while your work continues |
| 8 | `git worktree list` / `remove` | Manage multiple worktrees from one source repo |
| 9 | `git reflog` | A log of every HEAD move (commits, resets, rebases, checkouts) — local-only |
| 10 | Recovering Lost Commits | After `reset --hard`, find the lost SHA in reflog and `git branch rescue <sha>` |
| 11 | Recovering Deleted Branches | `git reflog` shows the last SHA the branch pointed to; `git branch <name> <sha>` brings it back |
| 12 | `git fsck --lost-found` | When even reflog doesn't help — find dangling objects in `.git/objects` |
| 13 | Sparse Checkout | `git sparse-checkout set` — work on a subset of a giant monorepo without downloading everything |
| 14 | Partial Clone | `git clone --filter=blob:none` — clone a huge repo without downloading every blob |
| 15 | `git filter-repo` | The modern way to rewrite entire histories (e.g. remove an accidentally-committed secret from every past commit) |

> [!IMPORTANT]
> **Before you panic, run `git reflog`.** Almost everything you can do with Git can be undone via reflog within 90 days (default `gc.reflogExpire`). Lost commits, deleted branches, botched rebases, accidental hard-resets — all recoverable. Memorize this. It will save you and your teammates many times.

<details>
<summary><strong>Reference: Bisecting a Bug</strong></summary>

```bash
# You know commit a1b2c3d (last week) was good, HEAD is bad
git bisect start
git bisect bad                   # current HEAD is bad
git bisect good a1b2c3d          # this commit was good

# Git checks out the midpoint commit. Test it.
npm test
# Tests fail
git bisect bad

# Git checks out a new midpoint. Test again.
npm test
# Tests pass
git bisect good

# Continue until Git declares the culprit:
# e4f5g6h is the first bad commit

# End the session
git bisect reset
```

Even better — let CI do it for you:

```bash
git bisect start HEAD a1b2c3d
git bisect run npm test
# Walks every midpoint and reports the first bad commit when done
```

</details>

<details>
<summary><strong>Reference: Working in Two Branches at Once with worktree</strong></summary>

```bash
# You're mid-feature in your main repo dir
pwd
# /Users/you/projects/my-app  (on feature/login)

# Need to check main without losing your work
git worktree add ../my-app-main main
cd ../my-app-main
# Now you're on main in a separate directory. Both work.

git worktree list
# /Users/you/projects/my-app        e4f5g6h [feature/login]
# /Users/you/projects/my-app-main   a1b2c3d [main]

# When done, remove it
cd ../my-app
git worktree remove ../my-app-main
```

No stashing. No commit-WIP-pop dance. Two real working trees on one Git repo.

</details>

<details>
<summary><strong>Reference: Recovering "Lost" Work via reflog</strong></summary>

```bash
# Disaster: you ran `git reset --hard HEAD~5` and lost 5 commits
git log --oneline -3
# Nothing — you only see the new HEAD

# But reflog remembers
git reflog
# e4f5g6h HEAD@{0}: reset: moving to HEAD~5
# a1b2c3d HEAD@{1}: commit: add billing flow      <-- the lost work!
# 9z8y7x6 HEAD@{2}: commit: refactor auth
# ...

# Bring it back
git branch rescue a1b2c3d
git switch rescue
# Your work is back
```

Same pattern works for accidentally-deleted branches:

```bash
git branch -D feature/login         # whoops!
git reflog                          # find the last SHA the branch pointed to
git branch feature/login <sha>      # restored
```

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Use `git bisect` to find the commit that introduced a bug in a sample repo
- [ ] Set up a `git worktree` for `main` while staying on a feature branch
- [ ] Recover a "lost" commit using `git reflog`
- [ ] Recover a deleted branch using `git reflog`
- [ ] Run a partial clone or sparse checkout on a large public repo

</details>

---

## Phase 11: Hooks & Automation

![Phase](https://img.shields.io/badge/Phase-11%2F13-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 4-5 Hours](https://img.shields.io/badge/Time-4--5%20Hours-yellow)

> Make Git enforce your team's standards automatically — no human reminders.

**What this phase is about.** **Git hooks** are scripts that run automatically at specific points in Git's lifecycle — before a commit, after a commit, before a push, on the server when a push arrives. They live in `.git/hooks/` (client-side) or on the server. The catch: `.git/hooks/` isn't tracked in your repo, so teams use tools like [Husky](https://typicode.github.io/husky/) and [lefthook](https://github.com/evilmartians/lefthook) to install them automatically. This phase covers `pre-commit`, `commit-msg`, `pre-push`, and `post-merge` hooks; the [pre-commit framework](https://pre-commit.com/) (a portable hook manager popular in Python land); and `semantic-release` for automated versioning + changelog generation.

**Why it matters.** Hooks turn "we should run the linter before every commit" from a wish into a guarantee. They block bad commits *before* they hit CI, save minutes per developer per day, and prevent "oops, forgot to format" PR feedback loops. Once you've used a well-configured pre-commit hook, you'll never want to ship without one.

| # | Topic | What You'll Learn |
|:-:|-------|-------------------|
| 1 | What Hooks Are | Executable scripts in `.git/hooks/` named for the lifecycle event |
| 2 | Client vs Server Hooks | Client (your machine — pre-commit, commit-msg, pre-push); Server (on the remote — pre-receive, post-receive) |
| 3 | `pre-commit` | Run before the commit message editor opens — block on lint errors, formatting, secrets |
| 4 | `commit-msg` | Validate the commit message — enforce Conventional Commits, max length, ticket prefix |
| 5 | `pre-push` | Run before sending commits upstream — block on failing tests, large files, banned strings |
| 6 | `post-merge` / `post-checkout` | Auto-run `npm install` when `package.json` changed; auto-rebuild migrations |
| 7 | Husky | The dominant JS/TS hook manager; tracks hooks in your repo, installs on `npm install` |
| 8 | lint-staged | Run linters/formatters only on staged files — fast, no full-repo lint on every commit |
| 9 | lefthook | Husky alternative — single binary, no Node required, supports parallel runs |
| 10 | pre-commit (Python framework) | Cross-language hook manager; thousands of pre-built hooks for Python, Go, Terraform, etc. |
| 11 | Conventional Commits | `type(scope): subject` — `feat:`, `fix:`, `chore:`, `docs:`, etc.; enforce via `commit-msg` hook |
| 12 | commitlint | Lints commit messages against the Conventional Commits spec |
| 13 | semantic-release | Automates the entire release: parses commits, bumps version, generates changelog, publishes |
| 14 | changesets | Alternative to semantic-release — explicit "what changed" notes per PR; popular in monorepos |
| 15 | Server-Side Hooks | `pre-receive` enforces rules on the server (most teams use branch protection instead, but useful for self-hosted Gitea/GitLab) |

> [!TIP]
> **Minimum viable hook setup for a JavaScript project:** Husky + lint-staged + Prettier + ESLint + commitlint. Five npm packages, 10 minutes to set up, prevents 80% of "you forgot to format" PR comments forever.

<details>
<summary><strong>Reference: Setting Up Husky + lint-staged + commitlint</strong></summary>

```bash
# Install
npm install --save-dev husky lint-staged @commitlint/cli @commitlint/config-conventional

# Initialize Husky
npx husky init

# Add pre-commit hook
echo "npx lint-staged" > .husky/pre-commit

# Add commit-msg hook
echo "npx --no -- commitlint --edit \$1" > .husky/commit-msg

# Configure lint-staged in package.json
```

```json
{
  "lint-staged": {
    "*.{js,ts,tsx}": ["eslint --fix", "prettier --write"],
    "*.{json,md}": ["prettier --write"]
  },
  "commitlint": {
    "extends": ["@commitlint/config-conventional"]
  }
}
```

Now every commit auto-formats only the files you staged, and every commit message is validated against Conventional Commits. Bad commits never enter your repo.

</details>

<details>
<summary><strong>Reference: Conventional Commits Cheat Sheet</strong></summary>

```
<type>(<scope>): <subject>

<body>

<footer>
```

| Type | When to Use |
|------|-------------|
| `feat:` | New feature for the user |
| `fix:` | Bug fix for the user |
| `docs:` | Documentation only |
| `style:` | Formatting; no code change |
| `refactor:` | Refactor; no feature/bug change |
| `perf:` | Performance improvement |
| `test:` | Adding/fixing tests |
| `chore:` | Build, deps, tooling |
| `ci:` | CI configuration |
| `BREAKING CHANGE:` | (in footer) major version bump |

Examples:
- `feat(auth): add Google OAuth login`
- `fix(checkout): handle empty cart edge case`
- `chore(deps): bump react from 18 to 19`

This format is what `semantic-release` reads to auto-bump versions: `fix:` → patch, `feat:` → minor, `BREAKING CHANGE:` → major.

</details>

<details>
<summary><strong>Reference: A Minimal pre-commit Hook (Bash)</strong></summary>

```bash
#!/usr/bin/env bash
# .husky/pre-commit

# Block commits that contain "TODO" in staged JS files
if git diff --cached --name-only | grep -E '\.(js|ts)$' | xargs -r grep -l 'TODO'; then
  echo "Error: TODO comment in staged files. Remove it or use FIXME."
  exit 1
fi

# Run linter
npm run lint || exit 1
```

Hooks are just scripts — `bash`, `node`, `python`, anything executable. They block the commit by exiting non-zero.

</details>

<details>
<summary><strong>Learning Checklist</strong></summary>

- [ ] Set up Husky + lint-staged + Prettier on a sample repo
- [ ] Add a `commit-msg` hook that enforces Conventional Commits
- [ ] Write a custom `pre-push` hook that runs your test suite
- [ ] Configure `semantic-release` or `changesets` on a sample npm package
- [ ] Explain the difference between client-side and server-side hooks

</details>

---

## Phase 12: The Git Ecosystem

![Phase](https://img.shields.io/badge/Phase-12%2F13-blue)
![Difficulty: Advanced](https://img.shields.io/badge/Difficulty-Advanced-red)
![Time: 3-4 Hours](https://img.shields.io/badge/Time-3--4%20Hours-yellow)

> Map of the entire Git universe — every tool you'll meet in a real job.

**What this phase is about.** Git itself is a single CLI binary, but a sprawling ecosystem of tools sits on top of it: hosting platforms (GitHub vs GitLab vs Gitea), enhanced CLIs (`gh`, `glab`, `lazygit`, `tig`), GUI clients (GitKraken, SourceTree, Tower), CI/CD systems (GitHub Actions, GitLab CI), AI-powered review tools (CodeRabbit, Sourcery), monorepo tooling (Turborepo, Nx, Bazel), large-file storage (Git LFS), and AI coding assistants that read and write Git (Cursor, Claude Code, Copilot). This phase is your map.

**Why it matters.** "I know Git" is necessary but not sufficient — every job requires you to operate inside *some* part of this ecosystem. Job postings ask for "GitHub Actions experience", "Husky/Conventional Commits experience", "monorepo experience". This phase tells you which tools are worth learning, which are nice-to-know, and which are noise.

### 12.1 — Hosting Platforms

| Platform | Best For | Notes |
|----------|----------|-------|
| **[GitHub](https://github.com/)** | Default for most open source and modern teams | Owned by Microsoft. Best ecosystem (Actions, Copilot, gh CLI). |
| **[GitLab](https://gitlab.com/)** | Enterprises that want self-hosted; teams that value built-in CI | Strong DevOps story, free self-hosted CE edition. |
| **[Bitbucket](https://bitbucket.org/)** | Atlassian shops (Jira integration) | Free private repos for teams of 5. |
| **[Gitea](https://gitea.io/)** | Lightweight self-hosted | Single binary; great for homelabs and small teams. |
| **[Codeberg](https://codeberg.org/)** | Free, ethical alternative to GitHub for open source | Built on Gitea; non-profit. |
| **[Sourcehut](https://sourcehut.org/)** | Email-based workflows, minimalist | Drew DeVault's "no JS" platform; mailing-list patches. |
| **[Forgejo](https://forgejo.org/)** | Community fork of Gitea | Picking up steam in the FOSS world. |

### 12.2 — Enhanced CLIs

| Tool | What It Does |
|------|--------------|
| **[gh](https://cli.github.com/)** (GitHub CLI) | `gh pr create`, `gh issue list`, `gh repo clone` — GitHub from your terminal |
| **[glab](https://gitlab.com/gitlab-org/cli)** (GitLab CLI) | `gh`'s GitLab equivalent |
| **[lazygit](https://github.com/jesseduffield/lazygit)** | Beautiful terminal UI for Git — keyboard-driven, faster than any GUI |
| **[gitui](https://github.com/extrawurst/gitui)** | Rust-based TUI; lightning fast on huge repos |
| **[tig](https://jonas.github.io/tig/)** | Old-school text-mode interface for browsing log/blame/diff |
| **[delta](https://github.com/dandavison/delta)** | Drop-in replacement for `git diff` output — syntax-highlighted, side-by-side |

### 12.3 — GUI Clients

| Tool | Notes |
|------|-------|
| **[GitKraken](https://www.gitkraken.com/)** | Beautiful, cross-platform, paid for commercial use |
| **[SourceTree](https://www.sourcetreeapp.com/)** | Free, Atlassian, Mac/Windows |
| **[Tower](https://www.git-tower.com/)** | Polished Mac/Windows client, paid |
| **[Fork](https://git-fork.com/)** | Fast, native, one-time license |
| **[GitButler](https://gitbutler.com/)** | New-wave: Rust-based, "virtual branches", from the founders of GitHub |
| **[VS Code Source Control](https://code.visualstudio.com/docs/sourcecontrol/overview)** | Built-in; great for daily flow |

### 12.4 — CI/CD

| Tool | Best For |
|------|----------|
| **[GitHub Actions](https://github.com/features/actions)** | Default if you're on GitHub. YAML-based, generous free tier, biggest action marketplace. |
| **[GitLab CI](https://docs.gitlab.com/ee/ci/)** | Default if you're on GitLab. Tight integration, self-hosted runners. |
| **[CircleCI](https://circleci.com/)** | Older but still strong; great parallelism. |
| **[Buildkite](https://buildkite.com/)** | Self-hosted runners, hybrid model — popular in fintechs. |
| **[Jenkins](https://www.jenkins.io/)** | The grandparent of CI; powerful, ugly, ubiquitous in enterprise. |
| **[Drone](https://www.drone.io/)** | Container-native, simple YAML, self-hosted. |
| **[Woodpecker](https://woodpecker-ci.org/)** | Open-source fork of Drone. |

### 12.5 — Hook Managers

| Tool | Notes |
|------|-------|
| **[Husky](https://typicode.github.io/husky/)** | Default for JS/TS projects |
| **[lefthook](https://github.com/evilmartians/lefthook)** | Single Go binary; great parallel runs; language-agnostic |
| **[pre-commit](https://pre-commit.com/)** | Python-rooted, vast hook ecosystem, language-agnostic |
| **[lint-staged](https://github.com/okonet/lint-staged)** | Run linters only on staged files; pairs with Husky |

### 12.6 — Stacked PR / Branch Tools

| Tool | What It Does |
|------|--------------|
| **[Graphite](https://graphite.dev/)** | Stacked PRs as a workflow — chain dependent PRs with `gt submit` |
| **[git-spice](https://abhinav.github.io/git-spice/)** | Open-source stacked-branch CLI |
| **[git-branchless](https://github.com/arxanas/git-branchless)** | "Workflow upgrade" for branchless local development; smart-log, undo |
| **[git-town](https://www.git-town.com/)** | Higher-level commands: `git town hack`, `git town ship` |

### 12.7 — Code Review (AI-augmented)

| Tool | Notes |
|------|-------|
| **[CodeRabbit](https://www.coderabbit.ai/)** | AI-powered PR reviews — line-level summaries and bug detection |
| **[Sourcery](https://sourcery.ai/)** | AI suggestions for refactoring, in PR comments |
| **[Reviewable](https://reviewable.io/)** | More structured PR-review UI than GitHub default; tracks unresolved threads |
| **[Graphite Reviewer](https://graphite.dev/)** | Stacked-PR-aware review experience |

### 12.8 — Monorepo Tools

| Tool | What It Does |
|------|--------------|
| **[Turborepo](https://turbo.build/repo)** | Vercel's high-perf JS/TS monorepo build tool |
| **[Nx](https://nx.dev/)** | Full monorepo platform — build cache, generators, dep graph |
| **[Bazel](https://bazel.build/)** | Google's build system; polyglot, deterministic, gnarly to set up |
| **[Pants](https://www.pantsbuild.org/)** | Bazel competitor with friendlier ergonomics |
| **[Buck2](https://buck2.build/)** | Meta's Rust-rewrite of their build system |

### 12.9 — Conventions & Releases

| Tool | What It Does |
|------|--------------|
| **[Conventional Commits](https://www.conventionalcommits.org/)** | The commit-message specification |
| **[commitlint](https://commitlint.js.org/)** | Validates commit messages against Conventional Commits |
| **[semantic-release](https://semantic-release.gitbook.io/)** | Auto-versions + auto-publishes from commits |
| **[changesets](https://github.com/changesets/changesets)** | Explicit per-PR change notes; popular in monorepos |
| **[release-please](https://github.com/googleapis/release-please)** | Google's release-PR generator |
| **[git-cliff](https://git-cliff.org/)** | Customizable changelog generator from commits |

### 12.10 — Security

| Tool | What It Does |
|------|--------------|
| **[git-secrets](https://github.com/awslabs/git-secrets)** | Block commits that look like AWS keys |
| **[trufflehog](https://github.com/trufflesecurity/trufflehog)** | Scan history for leaked credentials |
| **[gitleaks](https://github.com/gitleaks/gitleaks)** | Same idea, fast Go binary, popular in CI |
| **[Dependabot](https://github.com/dependabot)** | Auto-PRs to bump vulnerable dependencies (built into GitHub) |

### 12.11 — Large Files / Big Repos

| Tool | What It Does |
|------|--------------|
| **[Git LFS](https://git-lfs.com/)** | Large File Storage — keeps big binaries out of the main pack files |
| **[git-annex](https://git-annex.branchable.com/)** | Manage huge files (videos, datasets) with Git pointers |
| **[Sparse checkout](https://git-scm.com/docs/git-sparse-checkout)** | Built-in: work on a slice of a giant repo |
| **[Partial clone](https://git-scm.com/docs/partial-clone)** | Built-in: clone without downloading every blob |

### 12.12 — AI Coding Tools (Git-aware)

| Tool | Notes |
|------|-------|
| **[GitHub Copilot](https://github.com/features/copilot)** | The original; deeply integrated with VS Code, JetBrains, gh CLI |
| **[Cursor](https://www.cursor.com/)** | AI-first editor; reads `.git` and your full repo |
| **[Claude Code](https://claude.com/claude-code)** | Anthropic's terminal agent — runs `git`, reads diffs, opens PRs |
| **[Codex](https://platform.openai.com/docs/codex)** | OpenAI's coding agent |
| **[Sweep](https://sweep.dev/)** | Bot that opens PRs from issues |
| **[Aider](https://aider.chat/)** | CLI pair programmer; commits its own changes with proper messages |

### 12.13 — Submodules vs Subtrees vs Workspaces

Three ways to bring "another repo" into yours. Each has trade-offs:

| Approach | What It Is | Best For | Pain Points |
|----------|-----------|----------|-------------|
| **[Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules)** | A pointer to a specific commit of an external repo | Vendoring a third-party lib at a pinned version | Easy to forget `--recurse-submodules`; checkouts confuse new devs |
| **[Subtrees](https://www.atlassian.com/git/tutorials/git-subtree)** | Merge an external repo's contents *into* yours | Including a small support repo without ceremony | Harder to push changes back |
| **[Monorepo workspaces](https://docs.npmjs.com/cli/v10/using-npm/workspaces)** (npm/pnpm/yarn) | Multiple packages in one repo, one history | Most modern multi-package projects (Turbo, Nx) | Not Git-level; package-manager features |

**Default in 2026:** monorepo workspaces. Submodules are a last resort.

---

## Phase 13: What's Next?

![Phase](https://img.shields.io/badge/Phase-13%2F13-blue)
![Difficulty: Bridge](https://img.shields.io/badge/Difficulty-Bridge-purple)
![Time: Ongoing](https://img.shields.io/badge/Time-Ongoing-yellow)

> You know Git. Now plug it into the rest of your stack.

**What this phase is about.** Git is rarely the goal — it's the *substrate* under everything else you ship. Once you're comfortable with the workflows in Phases 1–11, the highest-leverage next steps are: become great at **GitHub Actions** (every modern project's CI), pair Git with a backend language (Python, Node, Go) so your projects do something, and learn **Docker** so deploys become reproducible. This phase points at the right next syllabus for each track.

**Why it matters.** Git skill compounds with everything around it. Knowing Git + GitHub Actions makes you a better backend dev. Knowing Git + Docker makes you a better DevOps engineer. Knowing Git + a language makes you employable. Sitting on raw Git knowledge with no project to apply it to is wasted study.

### 13.1 — Master GitHub Actions (CI/CD)

GitHub Actions is the dominant CI/CD platform in 2026 — generous free tier, biggest action marketplace, runs natively on every push and PR. Master it and you can ship software end-to-end.

Start with: a workflow that runs `npm test` on every push, then add lint, type-check, build, and deploy steps. Move on to matrix builds (test on Node 18 + 20 + 22 simultaneously), reusable workflows, and OIDC for cloud deploys (no long-lived secrets).

➡️ Continue with the [GitHub Actions Syllabus](github-actions.md) (or the [DevOps Syllabus](devops.md) for a broader take).

### 13.2 — Pick a Backend Language

Git is most useful when you have something to commit. Pick one of these to actually build things:

| Language | Best For | Companies |
|----------|----------|-----------|
| **[JavaScript/TypeScript](javascript.md)** + Node.js | Web, full-stack, the largest job market | Meta, Netflix, Vercel, Stripe |
| **[Python](python.md)** | Backend, data, ML/AI, automation | Google, Instagram, Anthropic, OpenAI |
| **[Go](go.md)** | Cloud infrastructure, CLIs, microservices | Google, Cloudflare, Docker, HashiCorp |
| **[Rust](rust.md)** | Performance-critical systems, embedded, WASM | AWS, Microsoft, Discord, Cloudflare |
| **[Java](java.md)** / Kotlin | Enterprise backends, Android | Google, Amazon, Oracle, every bank |

**Recommendation for 2026:** JavaScript/TypeScript if you want the biggest job pool, Python if you want AI/ML, Go if you want infra/DevOps.

### 13.3 — Learn Docker (Reproducible Deploys)

Once you can ship code via Git, the next step is shipping the *environment* with it. Docker packages your app + its dependencies + the OS into one image that runs identically on your laptop, your teammates' laptops, and production. It pairs naturally with Git: GitHub Actions builds an image on every push, pushes it to a registry, and your servers pull the new tag.

➡️ Continue with the [Docker Syllabus](docker.md).

### 13.4 — Real-World Add-Ons

| Skill | Why It Matters |
|-------|----------------|
| **Cloud (AWS / GCP / Azure)** | Where your code actually runs. Start with one. |
| **Kubernetes** | Container orchestration. Mandatory at any company shipping microservices. |
| **Terraform / Pulumi** | Infrastructure-as-code — your servers tracked in Git, just like your app. |
| **Open Source Contribution** | The fastest way to level up Git skill *and* build a public reputation. Pick a "good first issue" and ship a PR this month. |

### 13.5 — Suggested Order After This Syllabus

```
GitHub Actions -> Docker -> a backend language -> a cloud -> open source PR -> Kubernetes
```

Or in a single sentence: **pick one language, ship one project, automate it with Actions, deploy it on a cloud.** That's the loop. Repeat until employed.

---

## Common Mistakes

Avoid these pitfalls that trip up most beginners (and many seniors too):

| # | Mistake | Why It's Wrong | Do This Instead |
|---|---------|----------------|-----------------|
| 1 | Committing `.env` files / API keys | Once pushed, they're in the history forever — bots scrape GitHub for leaked secrets within minutes | Add `.env` to `.gitignore` from day one; rotate keys if leaked; use [`gitleaks`](https://github.com/gitleaks/gitleaks) in CI |
| 2 | Working directly on `main` | Breaks the team workflow; impossible to revert one feature without reverting others | Always `git switch -c feature/*` first |
| 3 | `git push --force` to a shared branch | Rewrites teammates' clones — destroys their commits | Use `--force-with-lease`, and never on `main` |
| 4 | Vague commit messages ("update", "fix") | Useless in `git log`; defeats `bisect`; bad PR review experience | Use Conventional Commits or at least imperative subject + body |
| 5 | No `.gitignore` | `node_modules/`, `dist/`, `.DS_Store` end up in the repo | Generate one from [gitignore.io](https://www.toptal.com/developers/gitignore) before first commit |
| 6 | Merge commits when squash was wanted | Polluted `main` history with `Merge branch 'feature/foo' of...` noise | Configure repo merge strategy; pick squash for PRs |
| 7 | `git reset --hard` without checking first | Loses uncommitted work permanently (well, until reflog) | Always `git status` first; prefer `git stash` if unsure |
| 8 | Skipping pre-commit hooks | Pushing unformatted/unlinted code; CI fails for trivia | Husky + lint-staged; takes 10 min, saves hours |
| 9 | Long-lived feature branches | Conflicts pile up; rebase becomes a nightmare; teammates wait | Merge `main` into your branch (or rebase) daily |
| 10 | Branch names like `fix2`, `tmp`, `test` | Useless in `git branch` output; nobody knows what they're for | Use `type/short-description`: `fix/login-rate-limit` |
| 11 | `git pull` blindly without `git status` | Can create surprise merge commits when you have local changes | `git fetch` first, inspect, then merge or rebase explicitly |
| 12 | Not pulling before pushing | Push rejected — non-fast-forward; first-week confusion | `git pull --rebase` before push, or set `pull.rebase=true` globally |
| 13 | Using GUI exclusively, never CLI | Can't debug edge cases; slower; interview red flag | Learn the CLI first; GUI for daily flow is fine *after* |
| 14 | Committing huge binaries to Git | Repo balloons; clones take forever | Use [Git LFS](https://git-lfs.com/) for binaries (videos, models, large assets) |
| 15 | Rebasing a branch others are working on | Their next pull explodes with conflicts | Never rebase shared branches; rebase only your local feature branches |
| 16 | Storing secrets in commit messages | Same problem as committing them in files — they ship | Never. Use environment variables and secret managers. |
| 17 | Ignoring `git status` warnings | "Your branch is ahead of 'origin/main' by 3 commits" — and then you force-push | Read what `git status` is telling you. Always. |
| 18 | One giant PR with 30 changes | Impossible to review; conflicts pile up; reviewers procrastinate | Aim for <400 lines, one logical change, write a description |

---

## Interview Questions

<details>
<summary><strong>Beginner</strong></summary>

**1. What is Git, and how is it different from GitHub?**

Git is the distributed version-control *tool* that runs locally on your machine and tracks file changes over time. GitHub is a *hosting platform* that stores Git repositories online and adds collaboration features (PRs, issues, Actions). You can use Git without GitHub. You cannot use GitHub without Git.

**2. What are the three trees in Git?**

The **working directory** (files you edit), the **staging area / index** (changes lined up for the next commit), and the **local repository** (`.git` — the permanent history). `git add` moves changes from working directory to index; `git commit` moves them from index to repository.

**3. What is `HEAD`?**

`HEAD` is a special ref pointing to "where you are right now" — usually the tip of your current branch. After `git switch main`, `HEAD` points to `main`, which points to a commit. When you check out a commit directly (not a branch), `HEAD` becomes "detached" — pointing at a commit but not at any branch.

**4. What's the difference between `git fetch` and `git pull`?**

`git fetch` downloads new commits from the remote into `origin/*` tracking branches but does **not** modify your current branch. `git pull` is `fetch` + automatic merge (or rebase) into your current branch. Use `fetch` when you want to inspect what's new before merging.

**5. How do you undo the last commit?**

Three options depending on intent:
- `git commit --amend` — edit the last commit (message and/or files).
- `git reset --soft HEAD~1` — uncommit but keep changes staged.
- `git revert HEAD` — create a *new* commit that undoes it (safe on shared branches).

**6. What's a fast-forward merge?**

When the target branch hasn't moved since you branched off, Git can simply move the branch pointer forward to your tip — no merge commit needed. The history stays linear. If both branches have new commits, fast-forward is impossible and Git creates a merge commit.

**7. How do you create a new branch and switch to it?**

Modern: `git switch -c feature/login`. Old: `git checkout -b feature/login`. Both create a new branch from your current `HEAD` and switch to it.

</details>

<details>
<summary><strong>Intermediate</strong></summary>

**1. Explain `git rebase` vs `git merge`. When do you use each?**

`git merge` combines two branches and creates a merge commit (unless fast-forward is possible) — preserves the branch topology. `git rebase` replays your branch's commits on top of another branch — produces a linear history. Use **merge** when you want to preserve the actual story of how a feature was built. Use **rebase** when you want a clean, linear `main`. The Golden Rule: **never rebase commits that exist on a shared/public branch** — rebasing rewrites SHAs and breaks teammates' clones.

**2. What's the difference between `git reset --soft`, `--mixed`, and `--hard`?**

| | Working dir | Staging | HEAD |
|--|------------|---------|------|
| `--soft` | unchanged | unchanged | moved |
| `--mixed` (default) | unchanged | reset | moved |
| `--hard` | reset (destroyed) | reset | moved |

`--soft` "uncommits but keeps everything staged." `--mixed` "uncommits and unstages but keeps files." `--hard` "throw it all away." Always run `git status` before `--hard`.

**3. What's `git reset` vs `git revert`?**

`git reset` moves the branch pointer back, rewriting history (dangerous on shared branches, requires force-push). `git revert` creates a *new* commit that inverts a previous commit's changes — safe on shared branches because it adds rather than rewrites. Use **reset** for local-only mistakes, **revert** for anything already pushed.

**4. How does `git stash` work?**

`git stash push` takes your current uncommitted changes (working dir + index) and saves them to a stack, leaving you with a clean working dir. `git stash list` shows the stack. `git stash pop` applies the latest stash and removes it from the stack. `git stash apply` applies but keeps it. Stashes are local — never pushed.

**5. What is a detached HEAD?**

When you check out a specific commit (not a branch), `HEAD` points at the commit directly, not at any branch ref. Any new commits you make in this state are not on any branch — if you switch away, they become unreachable (recoverable via reflog for ~90 days). Useful for inspecting old states. To "save" work in a detached HEAD, create a branch: `git switch -c rescue`.

**6. What's a `.gitignore` and how does it work?**

A text file at any level of your repo listing glob patterns of files Git should not track (`node_modules/`, `*.log`, `.env`). Already-tracked files are NOT affected — `.gitignore` only stops *new* files from showing up as untracked. To untrack an already-committed file, use `git rm --cached <file>` then commit.

**7. What does `git cherry-pick` do?**

Apply the diff of a single commit (or range) onto your current branch as a *new* commit (different SHA, same content). Common use: backporting a bug fix from `main` to a release branch.

**8. How do you resolve a merge conflict?**

When Git can't auto-merge, it leaves conflict markers in the file:
```
<<<<<<< HEAD
your changes
=======
their changes
>>>>>>> branch-name
```
Edit the file to keep what you want, remove the markers, `git add` the resolved file, then `git commit` (for merges) or `git rebase --continue` (for rebases). Bail out anytime with `git merge --abort` or `git rebase --abort`.

</details>

<details>
<summary><strong>Advanced</strong></summary>

**1. How does `git reflog` save you from disasters?**

`git reflog` is a local-only log of every move `HEAD` has made — every commit, reset, rebase, checkout, merge — kept for ~90 days by default. Even after `git reset --hard`, the "lost" commits are still in the reflog. To recover: `git reflog` to find the SHA, then `git branch rescue <sha>` (or `git reset --hard <sha>`). It's the safety net that makes destructive Git commands non-fatal.

**2. Walk me through `git bisect`.**

`git bisect start` begins a session. You mark a known good commit (`git bisect good <sha>`) and a known bad commit (`git bisect bad`). Git checks out the midpoint and asks you to test it. You mark `good` or `bad`; Git narrows the range with binary search. After log₂(n) steps, Git reports "the first bad commit." Even better: `git bisect run <script>` automates the testing — Git runs your test on each midpoint, exiting 0=good, non-0=bad, finds the culprit hands-free. `O(log n)` instead of linear search.

**3. How does Git store data internally?**

Git is a content-addressed filesystem. Four object types in `.git/objects/`, each identified by SHA-1 hash:
- **Blob:** raw file contents (no path, no name).
- **Tree:** a directory listing — names + blob/tree hashes.
- **Commit:** root tree hash + parent commit hash(es) + author + committer + message.
- **Tag:** an annotated pointer to a commit, with metadata.

Refs (in `.git/refs/`) are tiny text files: `main` is just a file containing the latest commit hash. `HEAD` points to the current ref. Branches are cheap because they're just 41-byte files.

**4. Explain stacked PRs.**

A workflow where a chain of small, dependent PRs are open simultaneously: PR #1 (foundation) → PR #2 (depends on #1) → PR #3 (depends on #2). Reviewers can review each one in isolation. When #1 merges to `main`, #2 rebases onto `main` and is reviewed next. Tools: [Graphite](https://graphite.dev/), [git-spice](https://abhinav.github.io/git-spice/), [git-branchless](https://github.com/arxanas/git-branchless). Common at companies that prize small PRs (Stripe, Meta).

**5. What's the difference between `merge --squash`, fast-forward merge, and rebase + merge?**

- **Merge commit (`--no-ff`)**: keeps branch as a "bubble" with a merge commit linking both histories.
- **Fast-forward (`--ff-only`)**: just moves the pointer forward — only works if the target hasn't diverged.
- **Squash and merge (`--squash`)**: collapses the entire feature branch into a single commit on `main`.
- **Rebase + merge**: replays each commit individually onto `main`, then fast-forwards.

Trade-off: branch-bubble (merge) preserves "how it was built", linear (rebase/squash) gives a cleaner `main` log.

**6. How do you remove a secret accidentally committed long ago?**

`git filter-repo --path <file> --invert-paths` (or the older, slower `git filter-branch`) rewrites every commit to remove the file. Then force-push to the remote. **Critical:** the commit still exists in any clone or fork — you must rotate the secret immediately. Tools like [`bfg-repo-cleaner`](https://rtyley.github.io/bfg-repo-cleaner/) automate this.

**7. What's `git worktree` and when do you use it?**

`git worktree add <dir> <branch>` checks out another branch into another directory, sharing one `.git/`. Lets you have multiple branches checked out simultaneously without re-cloning or stashing. Common uses: long-running build on `main` while you continue feature work; reviewing a teammate's PR locally without disturbing your work; running tests on multiple branches in parallel CI.

**8. How does `git rerere` (reuse recorded resolution) help with rebases?**

`git rerere.enabled true` makes Git remember how you resolved a conflict the first time. If the same conflict appears again (common during long rebases or repeatedly merging the same branches), Git auto-applies your previous resolution. Saves significant time on big rebases.

</details>

---

## Practice Projects

Work through these as you progress. Each one builds a real artifact you can demonstrate.

### Project 1: Configure Your Global Git
![Phase 1](https://img.shields.io/badge/After-Phase%201-green)

**What you'll do:** Set up Git on a fresh machine end-to-end — install, configure name/email, set the default branch to `main`, generate an SSH key, add it to GitHub, set 8+ aliases, set `pull.rebase=true`, `rerere.enabled=true`, `push.autoSetupRemote=true`. Save your `.gitconfig` to a personal dotfiles repo (yes — your config goes in Git too).

**Skills practiced:** Installation, config, SSH, aliases, dotfiles workflow.

---

### Project 2: Hello, GitHub — Your First Public Repo
![Phase 2-3](https://img.shields.io/badge/After-Phase%202--3-green)

**What you'll do:** Create a `hello-git` repo on GitHub, clone it, make 5 atomic commits with proper Conventional Commits messages, push, and verify the green commit graph on your profile. Use `git log --oneline --graph --all` to inspect the result.

**Skills practiced:** Init/clone, three trees, commit hygiene, push, log inspection.

---

### Project 3: Branching Practice
![Phase 4](https://img.shields.io/badge/After-Phase%204-yellow)

**What you'll do:** In any repo, create three feature branches off `main`. Make conflicting changes to the same file on two of them. Merge one into `main`. Then merge the second — resolve the conflict by hand. Use `git merge --abort` to bail at least once, then redo it successfully. Diagram the final history with `git log --graph`.

**Skills practiced:** Branching, fast-forward vs three-way merge, conflict resolution, abort.

---

### Project 4: Recover a "Lost" Commit Using Reflog
![Phase 6, 10](https://img.shields.io/badge/After-Phase%206%2C%2010-yellow)

**What you'll do:** In a throwaway repo, make 5 commits. Then deliberately destroy the last 3 with `git reset --hard HEAD~3`. Use `git reflog` to find them and recover using `git branch rescue <sha>`. Repeat the exercise but with a deleted branch (`git branch -D <name>`) — recover that too. Document the steps in a Markdown gist.

**Skills practiced:** `reset`, `reflog`, recovery, the safety-net mindset.

---

### Project 5: Open Source Contribution
![Phase 5, 8, 9](https://img.shields.io/badge/After-Phase%205%2C%208%2C%209-yellow)

**What you'll do:** Pick a real open-source project on GitHub with a "good first issue" label (try [first-timers-only](https://www.firsttimersonly.com/) or [Up For Grabs](https://up-for-grabs.net/)). Fork, clone, branch, fix, push, open a PR with a great description, respond to review feedback, and get it merged. Bonus: a typo fix in a major project's README is easier than people think — and it's a real merged PR you can show.

**Skills practiced:** Fork-and-contribute workflow, PR writing, code review, conflict resolution, public collaboration.

---

### Project 6: Set Up GitHub Actions CI on a Project
![Phase 11](https://img.shields.io/badge/After-Phase%2011-red)

**What you'll do:** Take any small project (yours or a fork). Add `.github/workflows/ci.yml` that runs on every push and PR: install dependencies, run linter, run tests, build the project. Add a status badge to the README. Add branch protection on `main` requiring the CI to pass before merging. Open a deliberately-broken PR and watch it get blocked.

**Skills practiced:** CI/CD basics, GitHub Actions YAML, branch protection, badges.

---

### Project 7: Husky + Conventional Commits + semantic-release
![Phase 11](https://img.shields.io/badge/After-Phase%2011-red)

**What you'll do:** On a small npm package, add Husky + lint-staged + commitlint + semantic-release. Make a `feat:` commit and a `fix:` commit. Push to `main`. Watch the CI auto-bump the version, generate a CHANGELOG, create a Git tag, publish a GitHub Release, and (optionally) publish to npm — all from your commit messages alone.

**Skills practiced:** Hooks, Conventional Commits, automated releases, the full modern release pipeline.

---

### Project 8: Bisect a Bug
![Phase 10](https://img.shields.io/badge/After-Phase%2010-red)

**What you'll do:** In a sample repo with 50+ commits, write a test that reproduces a bug introduced somewhere in the history. Run `git bisect start`, `git bisect bad`, `git bisect good <old-sha>`, and walk Git through finding the breaking commit. Then automate it with `git bisect run npm test` and watch Git find it hands-free.

**Skills practiced:** `git bisect`, debugging via history, automated bisection.

---

## Git Cheat Sheets

Copy-paste-ready command references, organized by task. Bookmark this section.

### 1. Daily Workflow

```bash
# See where you stand
git status                              # what's changed, what's staged, current branch
git status -s                           # short version

# Stage and commit
git add file.txt                        # stage one file
git add -p                              # stage hunks interactively (best habit)
git add .                               # stage everything in current dir
git restore --staged file.txt           # unstage (modern) — keeps file changes
git commit -m "feat: add login form"    # commit with message
git commit                              # opens $EDITOR for a longer message
git commit --amend                      # edit the LAST commit (only if not pushed!)
git commit --amend --no-edit            # add staged changes to last commit, keep message

# See what you did
git log --oneline -10                   # last 10 commits, one line each
git log --oneline --graph --all         # visual branch graph
git diff                                # unstaged changes
git diff --staged                       # staged changes
git diff main                           # diff vs another branch
git show HEAD                           # what was in the last commit
git show abc1234                        # what was in commit abc1234
```

### 2. Branching & Switching (Modern: `switch` / `restore`)

```bash
# Branches
git branch                              # list local branches
git branch -a                           # list local + remote branches
git branch -d feature-x                 # delete merged branch (safe)
git branch -D feature-x                 # FORCE delete (loses unmerged work)
git branch -m old-name new-name         # rename current branch

# Switching (modern — clearer than checkout)
git switch main                         # switch to existing branch
git switch -c feature-login             # create + switch to new branch
git switch -                            # switch to PREVIOUS branch (like `cd -`)
git switch --detach HEAD~3              # detached HEAD at 3 commits ago

# Restoring files (modern — replaces `checkout -- <file>`)
git restore file.txt                    # discard unstaged changes to file
git restore --staged file.txt           # unstage but keep working changes
git restore --source=HEAD~1 file.txt    # restore file from 1 commit ago

# (Old syntax still works — you'll see it everywhere)
git checkout main                       # switch (old)
git checkout -b feature-login           # create + switch (old)
git checkout -- file.txt                # discard changes (old)
```

### 3. Undo & Recovery — "Oh Shit, Git!"

```bash
# I made changes I want to throw away
git restore .                           # discard ALL unstaged changes (CAREFUL)
git restore file.txt                    # discard one file
git clean -fd                           # delete untracked files + directories

# I committed too early / forgot a file
git add forgotten.txt
git commit --amend --no-edit            # add to the last commit

# I committed to the wrong branch
git reset HEAD~1                        # undo last commit, keep changes staged
git switch correct-branch
git commit -m "..."                     # recommit on correct branch

# I want to undo a commit but keep the changes
git reset --soft HEAD~1                 # undo commit, stay staged
git reset --mixed HEAD~1                # undo commit + unstage (default)
git reset --hard HEAD~1                 # ⚠️  destroys changes, use with care

# I pushed a bad commit and others have it
git revert abc1234                      # creates a NEW commit that undoes abc1234 (safe)

# I did something terrible — get me back
git reflog                              # full history of HEAD movements (recovery gold)
git reset --hard HEAD@{2}               # jump back to where you were 2 moves ago
git switch -c rescue HEAD@{2}           # create a branch at that point

# I deleted a branch
git reflog                              # find the branch's last SHA
git switch -c restored-branch <sha>     # bring it back

# I want to keep some changes but undo others
git reset HEAD~3                        # rewind 3 commits, all changes still in working dir
# now `git add -p` to pick what to recommit
```

### 4. History Inspection

```bash
git log --oneline --graph --all --decorate     # the universal "show me everything" view
git log --author="Alice"                       # by author
git log --since="2 weeks ago"                  # by date
git log --grep="fix typo"                      # by commit message
git log -S "useEffect"                         # commits that ADDED or REMOVED this string
git log -p file.txt                            # full history of a file with diffs
git log --follow file.txt                      # history of file (across renames)
git log main..feature                          # commits in `feature` not in `main`

git blame file.txt                             # who wrote each line
git blame -L 10,20 file.txt                    # blame specific lines
git show abc1234:path/to/file.txt              # see file at a specific commit
git diff abc1234 def5678 -- file.txt           # diff a file between two commits
```

### 5. Remotes — Push, Pull, Fetch

```bash
git remote -v                                  # list remotes
git remote add origin git@github.com:u/r.git   # add a remote
git remote set-url origin <new-url>            # change remote URL

git fetch                                      # download remote changes (don't merge)
git fetch --prune                              # also remove gone remote branches
git pull                                       # fetch + merge (default)
git pull --rebase                              # fetch + rebase (cleaner history)
git pull --ff-only                             # safest pull — only fast-forward

git push                                       # push current branch to its tracking remote
git push -u origin feature-x                   # first push of a new branch (sets upstream)
git push --force-with-lease                    # safer force-push (won't clobber others' work)
git push origin --delete feature-x             # delete remote branch
git push --tags                                # push all tags

# Better global default
git config --global pull.rebase true           # always rebase on pull
git config --global push.autoSetupRemote true  # auto-set upstream on first push
```

### 6. Stash — Pause Your Work

```bash
git stash                                      # save uncommitted changes, clean working dir
git stash push -m "WIP: refactor"              # save with a message
git stash push file.txt                        # stash only one file
git stash -u                                   # include untracked files

git stash list                                 # see all stashes
git stash show -p stash@{0}                    # diff of latest stash
git stash apply                                # restore latest stash, KEEP it in stash list
git stash pop                                  # restore latest stash, REMOVE from stash list
git stash apply stash@{2}                      # restore a specific stash
git stash drop stash@{0}                       # delete a stash
git stash clear                                # delete all stashes
```

### 7. Rebase, Squash, Cherry-pick

```bash
# Rebase your branch onto latest main
git fetch origin
git rebase origin/main                         # replay your commits on top of main
git rebase --abort                             # something went wrong, give up
git rebase --continue                          # after resolving conflicts

# Interactive rebase (rewrite the last N commits)
git rebase -i HEAD~5
# In the editor:
#   pick   - keep the commit
#   reword - keep changes, edit message
#   edit   - pause to amend
#   squash - combine into the previous commit (merge messages)
#   fixup  - combine into previous, drop this message
#   drop   - delete the commit

# Squash all commits in a feature branch into one
git rebase -i $(git merge-base feature main)

# Cherry-pick a commit from another branch
git cherry-pick abc1234                        # apply that commit on current branch
git cherry-pick abc1234..def5678               # range
git cherry-pick --abort                        # gave up
```

### 8. Tags & Releases

```bash
git tag                                        # list tags
git tag v1.0.0                                 # lightweight tag at HEAD
git tag -a v1.0.0 -m "First release"           # annotated tag (recommended)
git tag -a v1.0.0 abc1234                      # tag a specific commit
git push origin v1.0.0                         # push one tag
git push --tags                                # push all tags
git tag -d v1.0.0                              # delete locally
git push origin :refs/tags/v1.0.0              # delete on remote
```

### 9. Conflict Resolution

```bash
# After a merge/rebase/cherry-pick fails:
git status                                     # shows conflicted files
# Open files, find <<<<<<< / ======= / >>>>>>> markers, edit
git add resolved-file.txt                      # mark as resolved
git rebase --continue                          # (or --merge --continue / --cherry-pick --continue)

# Use a 3-way diff tool
git mergetool                                  # opens your configured tool

# Take one side wholesale
git checkout --ours file.txt                   # keep YOUR version
git checkout --theirs file.txt                 # take THEIR version
git add file.txt

# Abort and start over
git merge --abort                              # cancel a failed merge
git rebase --abort                             # cancel a failed rebase
```

### 10. Diff & Compare

```bash
git diff                                       # unstaged
git diff --staged                              # staged
git diff main..feature                         # what's different between branches
git diff main...feature                        # changes feature added since branching
git diff --stat                                # summary (files + line counts)
git diff --shortstat                           # one-line summary
git diff --name-only                           # just filenames
git diff --word-diff                           # diff word-by-word (better for prose)

# Compare a file between branches
git diff main feature -- file.txt
git diff abc1234 def5678 -- file.txt
```

### 11. Reflog — Your Time Machine

```bash
git reflog                                     # full history of HEAD movements (every change)
git reflog show feature-x                      # reflog for one branch
git reset --hard HEAD@{5}                      # jump back 5 moves
git reset --hard 'HEAD@{2 hours ago}'          # time-based

# Recover a "lost" commit
git reflog | grep "commit message"             # find the SHA
git switch -c recovered <sha>                  # create a branch at that point
```

### 12. Bisect — Find the Bad Commit

```bash
git bisect start
git bisect bad                                 # current commit is broken
git bisect good v1.0.0                         # this old tag works
# Git checks out a middle commit. Test it. Then:
git bisect good                                # if it works
git bisect bad                                 # if it's broken
# Repeat until Git tells you the first bad commit
git bisect reset                               # exit bisect, return to where you were

# Automated:
git bisect start HEAD v1.0.0
git bisect run npm test                        # Git runs your test, finds the breaking commit
```

### 13. Worktrees — Multiple Checkouts

```bash
# Work on two branches at once without stashing
git worktree add ../my-feature feature-login
cd ../my-feature                               # entire second checkout
# Edit, commit, push as normal

git worktree list                              # see all worktrees
git worktree remove ../my-feature              # clean up
```

### 14. GitHub CLI (`gh`)

```bash
# Auth
gh auth login                                  # one-time login

# Repos
gh repo create my-repo --public --source=. --push     # create + push current dir
gh repo clone owner/repo                       # clone
gh repo fork                                   # fork current

# Pull requests
gh pr create --title "feat: x" --body "..."    # open a PR from current branch
gh pr create --fill                            # use commit messages
gh pr list                                     # list PRs
gh pr view 123                                 # view PR #123
gh pr checkout 123                             # check out a PR locally for review
gh pr merge 123 --squash --delete-branch       # merge + clean up
gh pr review 123 --approve                     # approve a PR
gh pr review 123 --request-changes -b "..."    # request changes

# Issues
gh issue create --title "Bug: ..." --body "..."
gh issue list
gh issue close 42

# Workflows / Actions
gh run list                                    # recent CI runs
gh run watch                                   # tail the latest run live
gh run rerun <id>                              # retry a failed run
```

### 15. Aliases — Save Hours Forever

Drop these in `~/.gitconfig` (or run `git config --global alias.<x> <cmd>`):

```ini
[alias]
    s   = status -s
    co  = checkout
    sw  = switch
    br  = branch
    ci  = commit
    cm  = commit -m
    ca  = commit --amend --no-edit
    last = log -1 HEAD --stat
    lg  = log --oneline --graph --all --decorate -20
    lga = log --oneline --graph --all --decorate
    df  = diff
    dfs = diff --staged
    unstage = restore --staged
    pf  = push --force-with-lease
    sync = !git fetch --all --prune && git pull --rebase
    aliases = config --get-regexp ^alias\\.
    # Show contributors by commit count
    who = shortlog -sn --all --no-merges
    # Pretty log with author and time
    hist = log --pretty=format:'%C(yellow)%h%Creset %ad %s %C(blue)[%an]%Creset' --date=relative
```

Then `git s`, `git lg`, `git pf`, `git sync` become muscle memory.

### 16. Common Conventional Commit Prefixes

For tools like [Commitlint](https://commitlint.js.org/) + [semantic-release](https://semantic-release.gitbook.io/):

```
feat:     new feature                                    →  minor version bump
fix:      bug fix                                        →  patch version bump
docs:     documentation only
style:    formatting (no code change)
refactor: code change that neither fixes nor adds
perf:     performance improvement
test:     adding/updating tests
build:    build system / dependencies
ci:       CI config
chore:    misc (no production impact)
revert:   revert a previous commit

Breaking change: append `!` or use `BREAKING CHANGE:` footer
  → major version bump

Examples:
  feat: add OAuth login flow
  fix(auth): refresh token expiry off by one second
  refactor!: drop Node 16 support
```

### 17. `.gitignore` Starter

```gitignore
# Dependencies
node_modules/
__pycache__/
target/
vendor/

# Build outputs
dist/
build/
*.exe
*.o

# Editor / OS
.DS_Store
.idea/
.vscode/*
!.vscode/settings.json
*.swp

# Env / secrets — NEVER commit these
.env
.env.local
.env.*.local
*.pem
*.key

# Logs
*.log
logs/

# Test coverage
coverage/
.nyc_output/
```

For language-specific templates, browse [github.com/github/gitignore](https://github.com/github/gitignore).

### 18. Emergency Cheat Sheet — "I'm Panicking"

| Situation | Do This |
|-----------|---------|
| Wrote bad commit message | `git commit --amend` (only if not pushed) |
| Forgot to add a file | `git add file && git commit --amend --no-edit` |
| Need to undo last commit, keep changes | `git reset HEAD~1` |
| Need to undo last commit, throw away | `git reset --hard HEAD~1` |
| Pushed a bad commit | `git revert <sha>` (don't reset+force on shared branches) |
| Wrong branch — committed to main | `git reset HEAD~1 && git switch -c right-branch && git commit ...` |
| "Lost" a commit | `git reflog` → `git switch -c rescue <sha>` |
| Conflict during merge/rebase | Edit, `git add`, `git rebase --continue` (or `--abort`) |
| Force-pushed and broke a teammate | Use `--force-with-lease` next time. Send apology |
| Committed `.env` with secrets | **Rotate the secret first.** Then `git filter-repo` to scrub history + force push. Notify team |
| `git status` shows tons of unrelated changes | You're probably on the wrong branch — `git switch correct-branch` |
| `detached HEAD state` warning | You checked out a SHA. Make a branch: `git switch -c new-branch` |

> [!IMPORTANT]
> **The two rules of recovery:** (1) Almost nothing is truly lost — `git reflog` saves you for ~90 days. (2) Once you `git push --force` to a shared branch, others can lose work. Always prefer `--force-with-lease`.

---

## Resources

### Documentation

| Resource | Why It's Great |
|----------|---------------|
| [Pro Git Book (Free)](https://git-scm.com/book/en/v2) | The definitive Git book by Scott Chacon. Free online, multiple languages, deep yet readable. Read the first 5 chapters. |
| [git-scm.com Reference](https://git-scm.com/docs) | Official man pages for every Git command — the source of truth. |
| [GitHub Docs](https://docs.github.com/) | Everything GitHub-specific: PRs, Actions, Pages, Codespaces. |
| [GitLab Docs](https://docs.gitlab.com/) | If your job uses GitLab — equally polished. |
| [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials) | The clearest free tutorials on the internet for branching, rebasing, workflows. |
| [Oh Shit, Git!?!](https://ohshitgit.com/) | Bookmark this. The fastest answer to "I made a mess, how do I fix it?" |

### Books

| Book | Why Read |
|------|---------|
| [Pro Git (Scott Chacon)](https://git-scm.com/book/en/v2) | Free online. Cover-to-cover the best Git book ever written. |
| [Git for Teams (Emma Hogbin Westby)](https://www.oreilly.com/library/view/git-for-teams/9781491911204/) | Workflow-focused — choosing strategies, configuring repos, scaling teams. |
| [Learn Git in a Month of Lunches (Rick Umali)](https://www.manning.com/books/learn-git-in-a-month-of-lunches) | Beginner-friendly, paced as 25-minute daily lessons. |

### Visual Learning

| Tool | What It Does |
|------|--------------|
| [Visualizing Git](https://git-school.github.io/visualizing-git/) | Type Git commands and see the DAG update live. The fastest way to internalize how branches work. |
| [Learn Git Branching](https://learngitbranching.js.org/) | Interactive in-browser puzzles that teach branching/rebasing/merging. The single best free Git tutorial on the internet. |
| [Git Explorer](https://gitexplorer.com/) | "I want to do X" → click options → get the exact Git command. Reverse lookup. |
| [ohmygit.org](https://ohmygit.org/) | A game that teaches Git. Genuinely fun. |

### Cheat Sheets

| Cheat Sheet | Format |
|-------------|--------|
| [GitHub Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) | One-pager PDF, official |
| [Atlassian Git Cheat Sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet) | Beautifully formatted, common-task focused |
| [QuickRef.ME — Git](https://quickref.me/git.html) | Long, scannable, all common commands on one page |
| [Tower Git Cheat Sheet](https://www.git-tower.com/blog/git-cheat-sheet/) | Beautiful design, printable |

### YouTube

| Channel / Video | Why Watch |
|-----------------|-----------|
| [The Net Ninja — Git & GitHub for Beginners](https://www.youtube.com/playlist?list=PL4cUxeGkcC9goXbgTDQ0n_4TBzOO0ocPR) | Step-by-step playlist; gentle pace; perfect for first-time learners |
| [Fireship — Git for the Rest of Us](https://www.youtube.com/watch?v=HkdAHXoRtos) | 100-second whirlwind tour; great refresher |
| [The Coding Train — Git & GitHub](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV) | Friendly, project-based; great for visual learners |
| [GitHub's "How to Use Git and GitHub"](https://www.youtube.com/@GitHub) | Official channel; talks on Actions, Copilot, advanced patterns |

### Hosts & Practice

| Platform | What You Get |
|----------|-------------|
| [GitHub](https://github.com/) | The default. Free public + private repos, free Actions minutes, free Pages hosting. |
| [GitLab](https://gitlab.com/) | Free private repos, free CI/CD minutes, easy self-host. |
| [Codeberg](https://codeberg.org/) | Free, ethical, non-profit alternative for open source. |
| [first-timers-only](https://www.firsttimersonly.com/) | Curated "good first issue" tasks across many projects |
| [Up For Grabs](https://up-for-grabs.net/) | Bigger directory of beginner-friendly OSS issues |

### Roadmaps

| Resource | What It Does |
|----------|-------------|
| [roadmap.sh — Git & GitHub](https://roadmap.sh/git-github) | Interactive learning path — click each topic to see resources |
| [roadmap.sh — DevOps](https://roadmap.sh/devops) | Bigger picture — where Git fits in the full DevOps stack |

### Tools (Install Once, Use Forever)

| Tool | Why You Need It |
|------|----------------|
| [GitHub CLI (`gh`)](https://cli.github.com/) | `gh pr create`, `gh issue list`, `gh repo clone` — GitHub from the terminal |
| [lazygit](https://github.com/jesseduffield/lazygit) | Beautiful TUI; once you try it you'll use it daily |
| [delta](https://github.com/dandavison/delta) | Drop-in `git diff` upgrade — syntax-highlighted, gorgeous |
| [VS Code](https://code.visualstudio.com/) | Best built-in Git UI of any editor; great for merge conflicts |
| [GitLens (VS Code)](https://www.gitkraken.com/gitlens) | Inline blame on every line, file history, the works |

### Validation, Security & Hygiene

| Tool | What It Does |
|------|-------------|
| [gitleaks](https://github.com/gitleaks/gitleaks) | Scan repos for committed secrets — run in CI |
| [trufflehog](https://github.com/trufflesecurity/trufflehog) | Deep history secret scanning |
| [pre-commit framework](https://pre-commit.com/) | Cross-language hook manager with hundreds of pre-built hooks |
| [Husky](https://typicode.github.io/husky/) | Default JS/TS hook manager |
| [commitlint](https://commitlint.js.org/) | Enforce Conventional Commits |
| [semantic-release](https://semantic-release.gitbook.io/) | Automate versioning and changelogs from commit messages |

> [!TIP]
> If you install **only one tool** from this list, install **GitHub CLI (`gh`)**. It pays for itself within a day — `gh pr create --fill` alone saves you several minutes per PR.

---

[Back to Main Syllabus](../README.md)
