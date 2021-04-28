# Some Linux Commands (and extra things)

## Commands with some examples
`sudo [command]` run a command as an admin  
Example: `sudo su` (this moves you into admin mode)  

`ls` is used to list your current directory. To show hidden files and directories, add the flag `-a`.  
Example: `ls -a`  

`man [option] [command]` to get information about the command. The option is optional.  
Example: `man ls`  

`mkdir [dir_name]` create a directory/folder with the name supplied  
Example: `mkdir images` creates folder with the name "images"  

`pwd` displays the path to the current directory you're working in  

`nano [filname]` opens a file with the given filenam using the nano editor. If the file doesn't exist, it's created  

`mv [file_path] [new_file_path]` for moving files. Can also rename files using it  

`rm [filename]` used to remove files. Can also be used to remove directories  
Example: `rm -r images/` (the `-r` flag means "recursive". It allows you to delete directories that contain files)  

`ps` check processes that are running  

### Wildcards `*`, `?`, and `[]`
`*` represents any number of unknown characters  
`?` represents only one unknown character  
`[]` these brackets are used to match any occurences of character defined within them   

## Other Things
hello

<!-- ### To do

- what is a wildecards and How to use Wildcards
- how can you do Process Management
- What is Currently Running on your system
- Killing a process/Crashed Process
- how to check any process running in Foreground and Background Jobs
- how to stop/kill any process running in Foreground and Background Jobs
- How to change permissions with chmod command
- how to check permission for files/dir
- what does 777, 400, 600, r,w,x
- how to use head, tail, sort, nl (number line), wc (word count)
- what is pipping and redirection, HINT > indicates to the command line
- what is STDIN standard input and output -->