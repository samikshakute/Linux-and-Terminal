#### What is Terminal Emulator?
It is basically a program/application that will allow us to use the terminal in a graphical environment. </br>
Using terminal we can control our OS.

#### What is a shell?
A shell is a command line interface that will take all our commands as input. It interprets the commands and tells the OS what to do. Some of the commonly used shells are bash shell, bourne shell, c shell, korn shell, z shell, etc. </br>

Part of the terminal is known as Command Prompt.

#### Username and Hostname:
When we open our terminal we can see something like this: samiksha@samiksha-Inspiron-5570 </br>
Here, samiksha is the computer's username and samiksha-Inspiron-5570 is the host name.

#### What are environment variables?
These are named values that are used to change how the commands and processess are executed. 
A process is an instace of a running command.
  - Setting environment variables:
    - One way to set environmental variables in bash is using the `export` keyword </br>
    - For example: `export MY_PATH="Samiksha"`
    - These variables are not permanent. if we close the terminal it will be gone.
    - If we want to modify the PATH variable we can edit the .profile file using `vim .profile` command. Each path is separated by a colon(:).

#### What are aliases?
Aliases are shortcuts for long commands.

#### Bash Files
Whenever we open the terminal, some commands are automatically executed to automate tasks and it is depended on bash.
Some of the bash files are .bashrc, .profile, .bash_history, etc. These files are located in the home directory. They are hidden and we can list them using the `ls -a` command. if we want to see what lies in these files we can use the `cat` command. </br>
For example: `cat .bashrc` will display the contents of the .bashrc file.
 
#### Bash commands
   `whoami`
   `whereis`
  - List Operations
    - `ls`
    - `ls -l` --> shows users, permissions, group owners, etc.
    - `ls -a` --> also shows hidden files.
    - `ls -al` -->combination of ls -a and ls -l
    - `ls -R` --> also shows files in sub directories. </br>
    
  - Directory Operations
    - `open .` - opens current directory in files
    - `pwd` - displays the present working directory
    - `mkdir <dir-name>` - creates a new directory.
    - `mkdir <dir1-name> <dir2-name>` - creates a new directory in existing directory.
    - `mkdir -p <dir1-name> <dir2-name> <dir3-name>` - creates a new directory in between existing directories.
    - `cd folder-name`
    - `cd` --> go to home directory
    - `cd` .. --> go back </br>
      . means current directory and .. means previous directory
    - `cd ../folder-name` --> in the previous directory there is another directory.
    - `rm -r folder-name` - removes a folder permanently.
    - `find .` - find in current directory.
    - `find ..` - find in previous directory.
    - `find <folder-name>` - find in folder.
    - `find . -type d` - displays files in current directory of type directory.
    - `find . -type f` - displays files in current directory of type file.
    - `find . -type f -name <file-name>`
        - `-type f -name f*` - shows files starting with f.
        - `-type f -name "*.txt"` - shows files of type .txt
        - `-type f -iname "*.txt"` - shows files of type .txt that are not case sensitive.
        - `-type f -mmin -20` - displays files that were modified less than 20 min ago.
        - `-type f -mmin +20` - displays files that were modified more than 20 min ago.
        - `-type f -maxdepth 2` - 
    - `find . -size +1k` - shows files/folders with size greater than 1kb.
    - `find . -empty` - shows files that are empty.
    
    
  - File Operations
    - `touch <file-name>` - creates a new file.
    - `touch <folder-name>/<file-name>` - creates a file in a folder.
    - `cp <file1-name> <file2-name>` - copy file1 contents in file2.
    - `mv <file1-name> <file2-name>` - renames file1-name to file2-name.
    - `mv <file-name> <dir-name>` - moves file into directory.
    - `mv <file-name ../<newFile-name>` - move and create a new file in previous directory.
    - `rm <file-name>` - removes a file permanently. 
    - `rm -f <file-name>` - forces deletion of file in certain scenarios when the file is unable to delete. For example, if the file is open, etc.
    - `head <file-name>` - displays the first 10 lines of file.
    - `head -n 4 <file-name>` - displays the first 4 lines of file.
    - `tail <file-name>` - displays the last 10 lines of file.
    - `tail -n 2 <file-name>` - displays last 2 lines of file.
    - `diff <file1-name> <file2-name>` - compares the contents of two file line by line and outputs the lines that do not match.
    - `locate <file-name>` - locates the file.
    - `locate ".txt"` - displays all the files that end with an extension of .txt
    
  - Environmental Variables:
    - `env` --> display environmental variables
    - `$PATH` 
    
  - Concatenate (cat)
    - `cat <file-name>` - displays contents of file.
    - `cat > <file-name>` - creates a new file. `>` basically means where do you want to output.
    - `cat <file1-name> <file2-name>` - prints the contents of two files.
    - `cat <file1-name> <file2-name> > <file3-name>` - merges file1 and file2 contents in file3. 
    - `cat <file1-name> | tr a-z A-Z > <file2-name>` - `|` is known as pipe which means output of the first file will act as an input to the second file.          The `tr` command is used to translate the contents of a file and `>` is used to redirect it into another file.

    - `echo "message"` - prints message
    - `echo "message" > file-name` - adds message in a file.
    
   - System Commands
      - `sudo` - used for administrative permissions.
      - `df` - used to check the system disk space.
        - `df -m` - in megabytes.
        - `df -hg` - in gigabytes.
      - `du` - shows disk usage statistics.
      
    
  - Permissions<br>
    There are three types of permissions: **read, write and execute** and there are three types of owners: **user, group and others.**
    - `find . -perm 777` - shows all files that have read, write and execute permissions. <br>
    `chmod` command is use to change file modes or permissions.
    - `chmod u=rwx, g=rx, o=r <file-name>` - changes the user, group and others permission of a file. <br>
    - We can also use octal numbers to change permissions. `chmod 777 <file-name>` - sets read, write and execute permissions to all owners. Here the number 777 is divided into 3 categories - user, group, others. 4 stands for read, 2 stands for write, 1 stands for execute and 0 stands for no permission. So, if we want to set read and write permissions to all the owners i.e. 4 + 2 = 5 --> `chmod 555 <file-name>` 
    - `chown root <file-name>` - changes the file owner to root.<br>
    root is a super user account used for administrative purposes and has the highest number of access rights in the system.
    - `find . -perm 777` - displays files that have permission to read, write and execute.
    
  - Search operations
    - `find . -type f -name "*.txt" -exec rm -rf {} +` - Here {} are parameters. 
    - `grep` - global regular expression print. It allows us to search for text within our files and is case sensitive.
    - `grep -V` - version of grep
    - `grep "text" <file-name>` - searching for particular text in a file.
    - `grep -w "text" <file-name>' - displays complete sentence/word.
    - `grep 
    
    
    
    
    
    
    
    
    
7. 
8.
9. `open $PATH`
19. `man`

