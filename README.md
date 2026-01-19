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