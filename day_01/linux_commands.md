# Some Linux Commands (and extra things)

## Commands with some examples
`sudo [command]` run a command as an admin  
The following moves you into admin mode
```
sudo su
```  

`ls` is used to list your current directory. To show hidden files and directories, add the flag `-a`.  
```
ls -a
```  

`[command] --help` - prints a message about how to use the command.  
```
ls --help
```  

`man [option] [command]` displays the manual for the command. The option is optional.  
```
man ls  
```

`pwd` displays the path to the current directory you're working in  

`mkdir [dir_name]` creates a directory/folder with the name supplied  
The following creates a directory with the name "images" in your current working directory
```
mkdir images
```  

`nano [filname]` opens a file with the given filenam using the nano editor. If the file doesn't exist, it's created  
```
nano test.txt
```

`mv [file_path] [new_file_path]` for moving files. Can also rename files using it  
The following moves a file called "cat.png" from the "dogs" directory to one named "cats"
```
mv dogs/cat.png cats/cat.png
```

`rm [filename]` used to remove files. Can also be used to remove directories    
The following deletes all the files and sub-directories inside of "dogs" and also deletes "dogs" itself. The `-r` flag means "recursive". It allows you to delete directories that contain files and other directories.
```
rm -r dogs/
```


### Wildcards `*`, `?`, and `[]`
`*` represents any number of unknown characters  
`?` represents only one unknown character  
`[]` these brackets are used to match any occurences of character defined within them   

## Processes
`top` - displays running processes in real time  
`ps` - displays running processes  

`kill [options] [pid]` - used to terminate processes. Use `kill -l` to list all available signals.  
I you don't specify a signal, it defaults to `15` (`TERM`) which gracefully stops a process.  
Other common signals are `1` (`HUP`) and `9` (`KILL`), which reload and forcefully stop processes, respectively.

## Changing Permissions
`chmod` allows you to change the permissions of a file. You can manage permissions symbolically or numerically.  

Here are the symbols and numeric values for each permission:  
- `r` (read) = 4
- `w` (write) = 2
- `x` (execute) = 1
- no permissions = 0

**Usage (Numeric)**  
The following changes the permissions of "run_me.sh" such that it can be read, writen to, and executed by the owner of the file and only read by anyone else.
```
chmod 744 run_me.sh
```
<!-- **Usage (Symbolic)**  
```
chmod o=rwx
``` -->

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