# Bash commands
  - <b> Basic Operations:</b>
      - Locating Applications:
          - `which [command]` - Locates and displays source of file
          - `whereis [command]` - Locates and displays source of file. It also looks for packages in a broader range of system directories.
      - Accessing Directories:
          - `pwd` - Displays the present working directory.
          - `cd` - Go to home directory
              - `cd ..` - Go back </br>
              . means current directory and .. means previous directory
              - `cd ../folder-name` --> In the previous directory there is another directory.
              - `cd -` - Change to previous working directory; - (minus)
      - Exploring the File System:
          - `cd /` - Changes your current directory to the root (/) directory (or path you supply).
          - `ls` - List the contents of the present working directory.
              - `ls -a` - List all files, including hidden files and directories (those whose name start with . )
              - `ls -l` - Shows users, permissions, group owners, etc.
              - `ls -li /path/to/directory` -  Used to list files and directories in a directory. The -l option provides a long listing format, and the -i option displays the inode number of each file.
              - `ls -l *pattern*` - Used to list all files and directories in the current directory that match the specified pattern.
              - `ls -al` - Combination of ls -a and ls -l
              - `ls -R` - Also shows files in sub directories. </br>
          - `tree` - Displays a tree view of the filesystem.
              - `tree -d` - Displays directories only.
      - Hard and Soft Links:
          - `ln <source> <destination>` - Used to create hard links.
          - `ln -s <source> <destination>` - Used to create soft(symbolic) links.
          
      - Navigating the directory history:
          - `pushd <directory>` - Used to change the current directory and also save the current directory onto the directory stack.
          - `popd <directory>` - Used to remove the top directory from the directory stack and change the current directory to the one that was removed from the stack.
          - `dirs` - Displays the directories in the directory stack in reverse order, with the most recent directory listed first.   
               
  - <b> File Operations: </b>
    - `cat` - Used for viewing files that are not very long; it does not provide any scroll-back.
        - `cat -n` - Also displays the line numbers.
    - `wc <file>` - Prints the number of lines, words and characters in file.
    - `tac`- Used to look at a file backwards, starting with the last line.
    - `less` - Used to view larger files because it is a paging program. It pauses at each screen full of text, provides scroll-back capabilities, and lets you search and navigate within the file.

     *NOTE: Use / to search for a pattern in the forward direction and ? for a pattern in the backward direction. An older program named more is still used, but has fewer capabilities: "less is more".*
    - `head <file-name>` - Displays the first 10 lines of file.
        - `head -4 <file-name>` - Displays the first 4 lines of file.
    - `tail <file-name>` - Displays the last 10 lines of file by default.
        - `tail -2 <file-name>` - Displays last 2 lines of file by default.
    - `touch <file-name>` - Creates a new file.
    - `touch <folder-name>/<file-name>` - Creates a file in a folder.
    - `echo > <file-name>` - Creates a new file 
    - `mv <file1-name> <file2-name>` - Renames file1-name to file2-name.
    - `mv <file-name> <dir-name>` - Moves file into directory.
    - `mv <file-name ../<newFile-name>` - Move and create a new file in previous directory.
    - `rm <file-name>` - Removes a file permanently. 
      - `rm -f <file-name>` - Forces deletion of file in certain scenarios when the file is unable to delete. For example, if the file is open, etc.
      - `rm -i <file-name>` - Used to remove (delete) files and directories from the file system. The system will display a prompt for each item, asking you to confirm whether you want to delete it. You can then respond with "y" (yes) or "n" (no).
      - `rm -rf <file-name>` - Forcefully remove a directory recursively.
      - `locate <file-name>` - locates the file.
      - `locate ".txt"` - displays all the files that end with an extension of .txt
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
     
      -  - `cp <file1-name> <file2-name>` - copy file1 contents in file2.

    - `diff <file1-name> <file2-name>` - compares the contents of two file line by line and outputs the lines that do not match.
    
    - `sort <file-name>` - sorts alphabetically.
        - `-r` - sorts in reverse order
        - `-f` - case insensitive sorting
        - `-n` - returns result in numerical order
    - `sort <file-name> | uniq` - removes duplicate entries. 
    - `paste <file1-name> <file2-name>` - combines fields from file1 and file2.
    - `join <file1-name> <file2-name>` - combines lines from two files based on a common field or key. 
    - Zipping files: `zip <zip-file-name> <file1-name> <file2-name>`
    - Unzipping files: `unzip <file-name>`
    - `cut -c 1-2 <file-name>` - shows first 2 columns of file.
    - `which [command]` - locates and displays source of file 
    - `whereis [command]` - locates and displays source of file. It also looks for packages in a broader range of system directories.
    - `file <file/directory-name>` - To find the type of files/directories.
    
    - `cat <file-name>` - displays contents of file.
    - `cat > <file-name>` - creates a new file. `>` basically means where do you want to output.
    - `cat <file1-name> <file2-name>` - prints the contents of two files.
    - `cat <file1-name> <file2-name> > <file3-name>` - merges file1 and file2 contents in file3. 
    - `cat <file1-name> | tr a-z A-Z > <file2-name>` - `|` is known as pipe which helps in executing multiple commands simultaneously. The `tr` command is used to translate the contents of a file and `>` is used to redirect it into another file.
    - `echo "message"` - prints message
    - `echo "message" > file-name` - adds message in a file.
    - `echo "message" >> existing-file-name` - appends message in an already existing file.
    - `echo $variable` - contents of specific environment variable are displayed.
    - `less <file-name>` - displays the contents of a file one page at a time. We can switch to the next page by click the space bar.
    - `sed 's/pattern/replacement/' filename` -  searches for pattern in  file and replaces them with the given replacement text.
    - `wc <file>` - prints the number of lines, words and characters in file.
      - `-l` - prints just the number of lines.
    
  - <b> Directory Operations: </b>
    - `open .` - opens current directory in files
    - `pwd` - displays the present working directory
    - `mkdir <dir-name>` - creates a new directory.
    - `mkdir <dir1-name> <dir2-name>` - creates a new directory in existing directory.
    - `mkdir -p <dir1-name> <dir2-name> <dir3-name>` - creates a new directory in between existing directories.
    - `cd folder-name`
    - `cd` - go to home directory
    - `cd ..` - go back </br>
      . means current directory and .. means previous directory
    - `cd ../folder-name` --> in the previous directory there is another directory.
    - `rm -r folder-name` - removes a folder permanently.
    - `rmdir <dir-name>` - to remove an empty directory.
      - `rmdir -rf <dir-name>` - removes a non-empty directory.
    - `find .` - find in current directory.
    - `find ..` - find in previous directory.
    - `find <folder-name>` - find in folder.   

  - <b> Environmental Variables: </b>
    - `env` - displays environmental variables

  - <b> Processes: </b>
    - `ps` - Displays information about processes currently running on the system.
        - `ps aux` - Shows a detailed list of all running processes.
        - `ps -e` - Lists all processes.
        - `ps -ef` - Provides a full listing with additional details.
        - `ps -eLf` - Displays one line of information for every thread.
    - `pstree` - Displays the processes running on the system in the form of a tree diagram showing the relationship between a process and 
                 its parent process and any other processes that it created.
    - `top` - Provides an interactive real-time view of system processes.
    - `htop` - Enhanced version with a more user-friendly interface and additional features.
    - `pidstat` - Reports statistics for processes, including CPU, memory, and I/O usage.
    - `vmstat` - Provides information about system-wide virtual memory statistics and can offer insights into process behavior.
    - `iotop` - Monitors I/O usage by processes and helps identify processes causing high I/O loads.
    - `w` - Displays information about currently logged-in users, their activities, and system load.
    - `top` - Provides a dynamic real-time view of system processes and resource usage. provides a dynamic real-time view of system processes 
              and resource usage. 
    - `uptime` - Provides a summary of system uptime and load averages.
  
  - <b> Text Editors: </b>
    - `nano <file>` - start the editor and edit file.
    - `gedit <file>` - start the text editor and edit file.
    - `vi <file>` - start the editor and edit file.
    - `emacs <file>` - Start emacs and edit file.
  
  - <b> System Commands: </b>
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
      - `getent group <user-name>` - to check user exists or not
      - `lsof` - shows all open files.
          - `lsof -u <user-name>` - shows open files for particular user.
    
  - <b> Permissions:<br> </b>
    There are three types of permissions: **read, write and execute** and there are three types of owners: **user, group and others.**
    - `find . -perm 777` - shows all files that have read, write and execute permissions. <br>
    `chmod` command is use to change file modes or permissions.
    - `chmod u=rwx, g=rx, o=r <file-name>` - changes the user, group and others permission of a file. <br>
    - We can also use octal numbers to change permissions. `chmod 777 <file-name>` - sets read, write and execute permissions to all owners. Here the number 777 is divided into 3 categories - user, group, others. 4 stands for read, 2 stands for write, 1 stands for execute and 0 stands for no permission. So, if we want to set read and write permissions to all the owners i.e. 4 + 2 = 5 --> `chmod 555 <file-name>` 
    - `chown root <file-name>` - changes the file owner to root.<br>
    root is a super user account used for administrative purposes and has the highest number of access rights in the system.
    - `find . -perm 777` - displays files that have permission to read, write and execute.
    
  - <b> Search operations: </b>
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
    - `grep -win <keyword> ./ .txt` - searching a keyword in all text files in current directory.
    - `grep -rwin <keyword> .` - searching recursively in current directory.
    - `grep -wirl <keyword> .` - displays all the files that have particular keyword.
    - `grep -wirc <keyword> .` - displays count of files that contain particular keyword.
    - `strings <file> | grep <my_string>` - searches for my_string in file.
    - `history` - shows history of all the commands we are using.
    - Piping output of one command into other commands using grep:<br>
      `history | grep "<command>"` - shows history of a particular command.
    
  - <b> What are jobs?<br> </b>
  It is a process started by the shell. We can use `jobs` command to list the running jobs.
  
  - <b> Network Operations: </b>
    - `cat \etc\hosts` - displays the contents of /etc/hosts that contains the mappings of IP addresses to hostnames.
    - `host [options] <hostname or IP address>` - allows to query DNS records and retrieve information about domain names or IP addresses.
    - `ping <hostname>` - checks the status of the remote host.
    - `route [options] [command]` - used to view and manipulate routing table.
      - `route -n` - displays the current routing table.
    - `traceroute <address>` - prints the route taken by the packet to reach the network host.
    - `wget <url>` - use to download files from the internet. 
      - `wget -o <custom-file-name> <url>` - to set custom name for the downloaded file.
    - `curl <url>` - reads a URL.
    - `hostname` - use to obtain the dns name.
      - `-i` - shows IP address.
    - `nslookup <url/IP address>` - to check IP address for particular domain.
    - `netstat` - shows all active ports 
    - `telnet`

  - <b> Finding Documentation: </b>
    - `man command_name` - To view the manual page of a specific command.
        - `man -f <command_name>` - To list all pages on the topic. Generates the same result as typing `whatis`.
        - `man -k <command_name>` - To list all pages that discuss a specific topic (even if the specified subject is not present in the                 name). Generates the same result as typing `apropos`.
        - `man -a <command_name>` -  Used to display the manual pages for a specified command from all available manual page sections.
        - `info <topic name>` - To view help for a particular topic. The system then searches for the topic in all available info files.
        - `<command_name> --help` - Help provides basic information about shell commands.
        
  - <b> Basic Packaging Commands(deb): </b>
    - `dpkg --install foo.deb` - Install package.
    - `apt install foo` - Install package, dependencies.
    - `dpkg --remove foo.deb` - Remove package.
    - `apt autoremove foo` - Remove package, dependencies.
    - `dpkg --install foo.deb` - Update package.
    - `apt install foo` - Update package, dependencies.
    - `apt dist-upgrade` - Update entire system.
    - `dpkg --list` - Show all installed packages.
    - `dpkg --listfiles foo` - Get information on package.
    - `dnf list "foo"	apt-cache search foo` - Show packages named foo.
    - `apt-cache dumpavail foo` - Show all available packages.
    - `dpkg --search file` - What package is file part of?

  - <b> Basic shortcuts: </b>
      - `CTRL-L` - Clears the screen
      - `CTRL-D` - Exits the current shell
      - `CTRL-Z` - Puts the current process into suspended background
      - `CTRL-C` - Kills the current process
      - `CTRL-H` - Works the same as backspace
      - `CTRL-A` - Goes to the beginning of the line
      - `CTRL-W` - Deletes the word before the cursor
      - `CTRL-U` - Deletes from beginning of line to cursor position
      - `CTRL-E` - Goes to the end of the line
      - `Tab` - Auto-completes files, directories, and binaries
      - `CTRL+K` - removes everything after the cursor.
      - `CTRL+R` - backward search / reverse intelligent search.
      - Running previous commands using history number/name: `!<history-number>` or `!<command-name>`
      - `CTRL+L` or `clear` - used to clear terminal.
      - `CTRL+L` (In Files) - used to access path of specific directory.
      - We can run multiple commands using `;`<br>
        Example: `git init;git add .;git commit -m "message";git push`
      - `!!(bang bang)` - executes previous command. 
    
  - <b> Operators</b>
      - I/O Redirection:
          - `>` - Redirects standard output to a file, overwriting the file if it already exists.
          - `>>` - Redirects standard output to a file, appending the output to the file if it already exists.
          - `<` - Redirects standard input from a file.
          - `2>` - Redirects standard error to a file.
          - `2>>` - Redirects standard error to a file, appending to the file if it already exists.
          - `&>` - Redirects both standard output and standard error to a file.
          - `|` - Redirects the output of one command as input to another command (pipeline).
            
    - `&` - it will create a process in the background so that other commands can be running. We can check the background process using `ps` command and kill it if needed. Example: `ping google.com & facebook.com`
    - `&&` - The command that is succeeding this operator will only execute when the previous one is finish executing. Example: `echo "first" && "second"`
    - `||` - The command that is after the OR operator will only execute if the execution of previous command fails. Example: `echo "first" || echo "second"`
    - `!` - can be use to delete all the files except one particular file.
      Example: `rm -rf !(<file-name>)`
    - `\` - used to split long commands and execute them as single command.
    - `{}` - combination operator use to group commands. </br>

  - <b> Wildcards </b>
    - `?` - Matches any single character.
    -  `*` - Matches any string of characters.
    - `[set]` - Matches any character in the set of characters, for example [adf] will match any occurrence of a, d, or f.
    - `[!set]` - Matches any character not in the set of characters.
