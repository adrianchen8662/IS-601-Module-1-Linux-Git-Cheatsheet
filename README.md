# IS 601 - Module 1: Assignment-Linux and GIT Command Cheat Sheet

## Linux Commands

## Git Commands
### Git Add
```bash
git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p]
	[--edit | -e] [--[no-]all | -A | --[no-]ignore-removal | [--update | -u]] [--sparse]
	[--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing] [--renormalize]
	[--chmod=(+|-)x] [--pathspec-from-file=<file> [--pathspec-file-nul]]
	[--] [<pathspec>…​]
```
`git add` is used to add new or changed files to the Git staging area

**Examples:**  
`git add .` - Add all local changes to the Git staging area  
`git add [filename]` - Add a single file to the Git staging area. Also works on directories/subdirectories  
`git add -p` - Add selective chunks out of files to the Git staging area  

### Git Commit
```bash
git commit [--all | -a] [--patch | -p] [--reuse-message=<commit> | -C <commit>]
	[--reedit-message=<commit> | -c <commit>] [--fixup <commit>]
	[--squash <commit>] [--reset-author] [--short] [--branch]
	[--porcelain] [--long] [--null] [--file=<file> | -F <file>]
	[--message=<msg> | -m <msg>] [--edit | -e] [--no-edit]
	[--amend] [--no-verify] [--allow-empty] [--allow-empty-message]
```

`git commit` records the staged changes to the local repository as a new commit.

Examples:
`git commit -m "Fix login bug"` – Commit staged changes with a message  
`git commit -a -m "Update config"` – Stage and commit tracked files in one step  
`git commit --amend` – Modify the most recent commit (message or content)  

### Git Push
```bash
git push [--all] [--prune] [--mirror] [--dry-run]
	[--force | --force-with-lease] [--tags]
	[--set-upstream | -u] [<repository> [<refspec>…​]]
```

`git push` uploads local commits to a remote repository.

Examples:
`git push` – Push current branch to its upstream remote  
`git push origin main` – Push main branch to origin  
`git push -u origin feature-x` – Push and set upstream tracking branch  
`git push --force-with-lease` – Force push safely (checks remote state first)  