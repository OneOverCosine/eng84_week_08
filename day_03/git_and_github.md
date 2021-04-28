# GitHub Workflow
And other useful things  

## The three stages of Git
Info from [here](https://archaeogeek.github.io/foss4gukdontbeafraid/git/stages.html)
- `Untracked` - The file exists, but is not part of git's version control
- `Staged` - The file has been added to git's version control, but changes have not been committed
- `Committed` - The changes have been committed

You can use `git status` to see the stage your files are in.  

## Oh no! I didn't mean to commit that...
Well, you're in luck!

### Remove a file you committed (but haven't pushed yet)
- `git reset --soft HEAD^1` - undo the last commit
- `git rm --cached [file_name]` - this removes the file fromt the commit and sets it back to an untracked file
