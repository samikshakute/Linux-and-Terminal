#### Bash commands
    
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
    - `rmdir <dir-name>` - to remove an empty directory.
      - `rmdir -rf <dir-name>` - removes a non-empty directory.
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
    - `sort <file-name>` - sorts alphabetically.
        - `-r` - sorts in reverse order
        - `-f` - case insensitive sorting
        - `-n` - returns result in numerical order
    - Zipping files: `zip <zip-file-name> <file1-name> <file2-name>`
    - Unzipping files: `unzip <file-name>`
    - `cut -c 1-2 <file-name>` - shows first 2 columns of file.   
    - `whereis` - locates and displays source of file.
    - `file <file/directory-name>` - To find the type of files/directories.
    
    - Concatenate (cat)
      - `cat <file-name>` - displays contents of file.
      - `cat > <file-name>` - creates a new file. `>` basically means where do you want to output.
      - `cat <file1-name> <file2-name>` - prints the contents of two files.
      - `cat <file1-name> <file2-name> > <file3-name>` - merges file1 and file2 contents in file3. 
      - `cat <file1-name> | tr a-z A-Z > <file2-name>` - `|` is known as pipe which helps in executing multiple commands simultaneously. The `tr` command is used to translate the contents of a file and `>` is used to redirect it into another file.

    - `less <file-name>` - displays the contents of a file one page at a time. We can switch to the next page by click the space bar.
    - `echo "message"` - prints message
    - `echo "message" > file-name` - adds message in a file.
    
  - Environmental Variables:
    - `env` --> display environmental variables
    - `$PATH` 
    
  
    
   - System Commands
      - `sudo` - used for administrative permissions.
      - `df` - used to check the system disk space.
        - `df -m` - in megabytes.
        - `df -hg` - in gigabytes.
      - `du` - shows disk usage statistics.
      - `top` - shows process running and CPU usage. 
      - `kill <process-id>` - to kill the process.
      - `uname` - shows kernel name.
          - `-o` - shows type of kernel.
          - `-a` - shows architechture.
          - `-r` - shows kernel version
      - `cat /etc/os-release` - shows all the info about the OS.
      - `lscpu` - shows CPU details.
      - `free` - shows free memory.
        - `-h` - shows used and free memory.
      - `vmstat` - shows virtual memory.
      - `id` - shows all id's.
          - `id <user-name>` - shows id of a particular user.
      - `useradd <new-user-name>` - creates a new user
      - `passwd <user-name>` - creates a password for user.
      - `userdel <user-name>` - deletes a user.
      - `getent group <user-name> - to check user exists or not
      - `lsof` - shows all open files.
          - `lsof -u <user-name>` - shows open files for particular user.
      - `ps aux` - shows processess running.
      
    
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
    - `grep <keyword> <file-name>` - searching for particular keyword in a file.
    - `grep -w <keyword> <file-name>' - displays complete word.
    - `grep -i <keyword> <file-name>` - searches for keyword ignoring case.
    - `grep -iw <keyword> <file-name>` - shows complete word ignoring case.
    - `grep -n <keyword> <file-name>` - displays line number.
    - `grep -win <keyword> <file-name>` - combination of all three tags.
    - `grep -B 3 <keyword> <file-name>` - shows previous three lines that comes before particular keyword.
    - grep -win <keyword> ./ .txt` - searching a keyword in all text files in current directory.
    - `grep -rwin <keyword> .` - searching recursively in current directory.
    - `grep -wirl <keyword> .` - displays all the files that have particular keyword.
    - `grep -wirc <keyword> .` - displays count of files that contain particular keyword.
    - `history` - shows history of all the commands we are using.
    - Piping output of one command into other commands using grep:<br>
      `history | grep "<command>"` - shows history of a particular command.
    
  - What are jobs?<br>
  It is a process started by the shell. We can use `jobs` command to list the running jobs.
  
  - Networking commands
    - `ping` - connects
    - `wget <url>` - use to download files from the internet. 
      - `wget -o <custom-file-name> <url> - to set custom name for the downloaded file.
    - `hostname` - use to obtain the dns name.
      - `-i` - shows IP address.
    - `nslookup <url/IP address>` - to check IP address for particular domain.
    - `netstat` - shows all active ports 
    - `ifconfig` 
    - `sed`
    - `telnet`
  
  - Basic shortcuts
      - `CTRL+A` - moves the cursor at the beginning.
      - `CTRL+E` - moves the cursor to the end.
      - `CTRL+K` - removes everything after the cursor.
      - `TAB` is used to show possibilities.
      - Running previous commands using history number/name: `!<history-number>` or `!<command-name>`
      - `CTRL+L` or `clear` - used to clear terminal.
      - `CTRL+L` (In Files) - used to access path of specific directory.
      - We can run multiple commands using `;`<br>
        Example: `git init;git add .;git commit -m "message";git push`
    
  - Operators:  
    - `&` - it will create a process in the background so that other commands can be running. We can check the background process using `ps` command and kill it if needed. Example: `ping google.com & facebook.com`
    - `&&` - The command that is succeeding this operator will only execute when the previous one is finish executing. Example: `echo "first" && "second"`
    - `||` - The command that is after the OR operator will only execute if the execution of previous command fails. Example: `echo "first" || echo "second"`
    - `!` - can be use to delete all the files except one particular file.
      Example: `rm -rf !(<file-name>)`
    - `>>` - use to append contents. example: `"hey" >> <file-name>` file will contain hey.
    - `>` - use to overwrite.
    - `\` 
    - `{}` - combination operator use to group commands. </br>
