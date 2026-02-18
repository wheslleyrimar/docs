# Best Practice: Do One Commit

This template standardizes how we **squash all work into a single, clean commit** before opening/merging a PR.

This applies whenever your branch has **2 or more commits** (vs the base branch) and you want to ship the branch as **one commit**.
It applies **even if you currently have no staged changes** (a clean working tree).

## Preconditions

- **MANDATORY / NON-NEGOTIABLE:** Ask for the base branch (do not assume).
  - Ask: "What is the base branch for this work?"
  - **Stop here and wait for the user's answer before continuing.**
- **MANDATORY / NON-NEGOTIABLE:** Be up to date with the base branch.
  - Run: `git pull origin <base-branch>`
- Your current branch contains everything you want to ship (even if the working tree is clean).

## Plan (required checklist)

- [ ] **Ask for the base branch** (MANDATORY / NON-NEGOTIABLE). Stop and wait for the user's answer.
- [ ] **Be up to date with the base branch** (MANDATORY / NON-NEGOTIABLE): `git pull origin <base-branch>`
- [ ] **Inspect only current-branch commits**: `git log origin/<base-branch>..HEAD --oneline --decorate --graph --max-count=50`
- [ ] **Update `CHANGELOG.md`** under `## [Unreleased]` with **2–4 bullets**
- [ ] **Soft reset to base**: `git reset --soft origin/<base-branch>`
- [ ] **Stage everything**: `git add .`
- [ ] **Create the single commit**: `git commit -m "[VERB]: <Short description>"`
- [ ] **User force-pushes (safer)** (agent must not): `git push --force-with-lease origin <current-branch>`

## Workflow (details)

### 1) Inspect history and update `CHANGELOG.md` (max 2–4 bullets)

Use git history to understand what changed, then update `CHANGELOG.md` with **2–4 bullet points** under `## [Unreleased]`.
To avoid noise, review **only the commits from the current branch** (i.e., commits that are not in the base branch).

```bash
git pull origin <base-branch>
git log origin/<base-branch>..HEAD --oneline --decorate --graph --max-count=50
```

Guidelines for changelog bullets:
- Keep it **short and user-facing** (what changed / why it matters).
- Prefer **2–4 bullets max**.
- Write in the same style as existing entries.

If you are preparing a release (version already defined):
- Create a `## [x.y.z]` section.
- Move the bullets from `## [Unreleased]` into `## [x.y.z]`.
- Leave `## [Unreleased]` empty (ready for the next work).

### 2) Soft reset to the base branch

This keeps your working tree changes but rewinds commits so you can create **one new commit**.
Even if you started with **no staged/unstaged changes**, after this step you will have changes to stage again.

```bash
git reset --soft origin/<base-branch>
```

Examples:

```bash
git reset --soft origin/develop
```

### 3) Stage everything

```bash
git add .
```

### 4) Create the single commit (commit convention)

```bash
git commit -m "[VERB]: <Short description>"
```

#### Allowed verbs

- `FEAT`
- `FIX`
- `ENHANCEMENT`
- `DOCS`
- `REFACTOR`
- `MIGRATION`

#### "Short description" rules (mandatory)

- It must be **written based on what you wrote in `CHANGELOG.md`**.
- It must contain:
  - **1 title**, and
  - **2–4 insights** (short phrases) describing what was delivered.

Recommended format:

```text
[VERB]: <Title> - <Insight 1>; <Insight 2>; <Insight 3>; <Insight 4>
```

Example:

```text
FEAT: Add prompt versioning endpoints - create-prompt + update-prompt; version-history streaming; authorization integration
```

### 5) Force-push the branch (USER responsibility)

After the commit is created, **the user must run the force-push** (do not do this as the agent).
Prefer `--force-with-lease` and push to `origin` using the current branch name:

```bash
git push --force-with-lease origin <current-branch>
```