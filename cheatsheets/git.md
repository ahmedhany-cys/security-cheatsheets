# Git

## Everyday
```bash
git status
git switch -c feature/x       # new branch
git add -p                    # stage hunks interactively
git commit -m "message"
git push -u origin feature/x
git pull --rebase
```

## Inspecting history
```bash
git log --oneline --graph --all
git show <commit>
git blame file.txt
git diff main...feature/x     # changes since branching
```

## Undoing
```bash
git restore file.txt          # discard working changes
git restore --staged file.txt # unstage
git commit --amend            # fix last commit (before pushing)
git revert <commit>           # new commit that undoes another
```

## Security hygiene
- Never commit secrets; add them to `.gitignore` and use env vars.
- If a secret is pushed, **rotate it first** — rewriting history is not enough.
- Scan for leaked secrets: `gitleaks detect` or `trufflehog git file://.`
- Sign commits: `git config commit.gpgsign true`
