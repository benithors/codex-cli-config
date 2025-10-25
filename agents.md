## 1 Scope & Defaults

* You **MUST** only modify or revert files you authored for the current task, unless you have explicit written approval **in this conversation**.
* When uncertain about other agents’ in-flight work, you **MUST STOP** and coordinate before acting.

## 2 Hard Prohibitions (NO EXCEPTIONS)

* You **MUST NOT** edit `.env` or any environment-variable files. Only the user may change them.
* You **MUST NOT** run destructive git operations without explicit written approval here:

  * `git reset --hard`, `rm -rf`, `git checkout`/`git restore` to an older commit, forced branch rewrites, or any history rewrite.
* You **MUST NOT** use `git restore` (or similar) to revert files you didn’t author.
* You **MUST NOT** delete files just to silence local type/lint errors. Ask first.
* You **MUST NOT** use `git push --force` on the `main` branch.
* You **MUST NOT** commit secrets, credentials, or API keys to the repository.

## 3 Approval-Required Actions

These actions **require explicit written approval here** before proceeding:

* Deleting unused/obsolete files (from refactors, feature removals, etc.).
* Reverting or removing work you didn’t author.
* Any change that could impact another agent’s in-progress edits.

## 4 Allowed Without Extra Approval

* Moving, renaming, and restoring **only** the files you authored for this task.

## 5 Commit Protocol (Atomic & Explicit)

* **Always** check status before committing:

  ```bash
  git status
  ```

* Keep commits atomic: commit **only** the files you touched and list each path explicitly.

  **Tracked files example**

  ```bash
  git commit -m "<scoped message>" -- path/to/file1 path/to/file2
  ```

  **Brand-new files one-liner**

  ```bash
  git restore --staged :/ && git add "path/to/file1" "path/to/file2" && git commit -m "<scoped message>" -- path/to/file1 path/to/file2
  ```

* Quote any paths with brackets or parentheses so the shell doesn’t glob or spawn subshells:

  ```bash
  git add "src/app/[candidate]/index.tsx"
  git commit -m "Scope: add candidate page" -- "src/app/[candidate]/index.tsx"
  ```

## 6 Coordination & Stop Rules

* If your local change would delete/override adjacent work, **STOP** and coordinate.
* If lint/type failures suggest deleting files you didn’t author, **STOP** and ask the user.
* If a git operation may affect other branches or history, **STOP** and request approval.


## 7 Security & Privacy Baselines

* **Principle of Least Privilege:** you **MUST** scope access keys, roles, and permissions to the minimal set required.

* **Secrets Handling:** you **MUST** use environment variables for sensitive data.

  * You **MUST NOT** place secrets in source files, docs, or commit messages.
  * You **MAY** update `.env.example` (placeholders only) to document required variables; do **not** add real values.
  * If a new secret is needed, request that the user adds it to the runtime environment.

* **Input Validation:** you **MUST** validate all user inputs on **both** client and server (type, range/format, length, allow-list/deny-list as appropriate).

## 8 Documentation Rules

* Project documentation **lives under** `docs/*.md`.

  * Add or update markdown docs there when behavior, APIs, configs, or decisions change.
  * Link code to relevant docs in commit messages when helpful.

## 9 Final Checks (Build & Lint)

* **Before concluding a task**, you **SHOULD** build and lint the project to surface integration errors.

## 10 Continuous Rule Improvement

 * When a misstep, conflict, or unclear situation reveals a missing guideline, propose a new rule for agents.md.

 * Include: what happened, the proposed rule (as a clear MUST/MUST NOT statement), and why it helps prevent future confusion.

 * Post your suggestion in this conversation before applying it.