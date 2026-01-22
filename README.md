# IS 601 - Module 1: Assignment-Linux and GIT Command Cheat Sheet

## Linux Commands
### cd
```bash
cd [-L | -P] [directory]
```

`cd` changes the current working directory.

**Examples:**  
`cd /etc` – Change to the /etc directory  
`cd ..` – Move up one directory level  
`cd ~` – Go to the home directory  
`cd -` – Switch to the previous directory  

### ls
```bash
ls [--all | -a] [--long | -l] [--human-readable | -h]
	[--recursive | -R] [--sort=time | -t]
	[--reverse | -r] [--classify | -F]
	[<file>…]
```

`ls` lists files and directories.

**Examples:**  
`ls` – List files in the current directory  
`ls -la` – List all files with detailed information  
`ls -lh` – Show file sizes in human-readable format  
`ls -R` – Recursively list directories  

### grep
```bash
grep [--ignore-case | -i] [--recursive | -r]
	[--line-number | -n] [--invert-match | -v]
	[--extended-regexp | -E] [--fixed-strings | -F]
	[pattern] [file…]
```

`grep` searches for text patterns in files.

**Examples:**  
`grep "error" logfile.txt` – Search for “error” in a file  
`grep -i "warning" *.log` – Case-insensitive search  
`grep -rn "TODO" .` – Recursively search with line numbers  
`ps aux | grep ssh` – Search command output  

### find
```bash
find [path…] [expression]
```

`find` searches for files and directories based on criteria such as name, type, or time.

**Examples:**  
`find . -name "*.txt"` – Find all .txt files  
`find /var/log -type f` – Find regular files  
`find . -size +100M` – Find files larger than 100 MB  
`find . -name "*.tmp" -delete` – Find and delete files  

### pwd
```bash
pwd [-L | -P]
```

`pwd` prints the current working directory.

Examples:
`pwd` – Show the current directory path
`pwd -P` – Show the physical path (resolving symlinks)

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

**Examples:**  
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

**Examples:**  
`git push` – Push current branch to its upstream remote  
`git push origin main` – Push main branch to origin  
`git push -u origin feature-x` – Push and set upstream tracking branch  
`git push --force-with-lease` – Force push safely (checks remote state first)  

### Git Merge
```bash
git merge [--commit | --no-commit] [--edit | --no-edit]
	[--ff | --no-ff | --ff-only] [--log] [--stat]
	[--squash | --no-squash] [--strategy=<strategy>]
	[--abort] [--continue] [--quit]
	[<commit>…​]
```

`git merge` combines changes from one or more branches into the current branch.

**Examples:**  
`git merge feature-x` – Merge feature-x into the current branch  
`git merge --no-ff feature-x` – Create a merge commit even if fast-forward is possible  
`git merge --abort` – Abort a merge with conflicts and restore pre-merge state  

### Git Rebase
```bash
git rebase [--onto <newbase>] [--continue | --abort | --skip]
	[--interactive | -i] [--rebase-merges | -r]
	[--autosquash] [--autostash]
	[--keep-empty] [--reapply-cherry-picks]
	[--strategy=<strategy>] [--strategy-option=<option>]
	[<upstream> [<branch>]]
```

`git rebase` reapplies commits from one branch on top of another base commit, creating a linear commit history.

**Examples:**  
`git rebase main` – Rebase the current branch onto main  
`git rebase -i HEAD~5` – Interactively edit, squash, reorder, or drop the last 5 commits  
`git rebase --continue` – Continue a rebase after resolving conflicts  
`git rebase --abort` – Cancel the rebase and restore the previous state  
`git rebase --onto main dev feature-x` – Move feature-x commits from dev onto main  

### Git Stash
```bash
git stash [push [--keep-index | -k] [--include-untracked | -u]
	[--all | -a] [--patch | -p] [-m <message>]]
git stash list
git stash show [--patch] [<stash>]
git stash apply [--index] [<stash>]
git stash pop [--index] [<stash>]
git stash drop [<stash>]
git stash clear
```

`git stash` temporarily saves uncommitted changes so you can work on something else.

**Examples:**  
`git stash` – Save modified tracked files and clean working directory  
`git stash -u` – Stash including untracked files  
`git stash list` – Show all stashed changes  
`git stash pop` – Reapply and remove the most recent stash  