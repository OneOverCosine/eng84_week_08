# GitHub Workflow
And other useful things  

## The three stages of Git
Info from [here](https://archaeogeek.github.io/foss4gukdontbeafraid/git/stages.html)
- `Untracked` - The file exists, but is not part of git's version control
- `Staged` - The file has been added to git's version control, but changes have not been committed
- `Committed` - The changes have been committed

You can use `git status` to see the stage your files are in.  

## Merging
`git merge` 

## Oh no! I didn't mean to commit that...
Well, you're in luck! (Info from [here](https://dev.to/morinoko/useful-git-commands-for-removing-accidentally-pushed-or-committed-files-2ld))

### Remove a file you committed (but haven't pushed yet)
- `git reset --soft HEAD^1` - undo the last commit
- `git rm --cached [file_name]` - this removes the file fromt the commit and sets it back to an untracked file
- `git commit -m "commit message"` - to commit the other files as usual

### Remove a file you pushed
Depending on why you want to remove the file, this can either be a single command solution or maybe something more involved...  

**You just don't want the file up anymore**  
Simply run `git rm --cached [file_name]`. This won't delete the file locally, so you still have access to it.  

***Note:*** Past commits can still be found the in the history, so this isn't enough for sensitive information you've accidentally pushed.

**So, uploaded a password...**  
All the info you need is [here](https://rtyley.github.io/bfg-repo-cleaner/)