### Introduction to UNIX
Certainly! Let's dive into each of the topics you've mentioned:

1. **Kernel and Shell**:
   - **Kernel**:
     - The kernel is the core component of an operating system.
     - It manages hardware resources (CPU, memory, devices) and provides services to other programs.
     - The kernel interacts directly with hardware and operates at a low level.
   - **Shell**:
     - The shell is a user interface that allows users to interact with the operating system.
     - It interprets commands entered by users and translates them into instructions for the kernel.
     - Shells provide features like command history, tab completion, and scripting capabilities.
     - Shells can be built-in (internal) or external commands.

2. **UNIX as a Multiuser OS**:
   - UNIX is designed to support multiple users simultaneously.
   - Multiple users can access different resources on a computer at the same time.
   - UNIX systems allow users to share resources (CPU time, memory, disk storage) concurrently.
   - Mainframe computers act as servers, and personal computers act as clients.

3. **Internal and External UNIX Commands**:
   - **Internal Commands**:
     - Built into the shell.
     - Execute directly from the shell without searching the PATH variable.
     - Examples: `source`, `cd`, `fg`.
   - **External Commands**:
     - Not built into the shell.
     - Located in directories specified by the PATH variable.
     - Executed by spawning a new process.
     - Examples: `ls`, `cat`.

### The File system
1. **Absolute and Relative Pathnames**:
   - **Absolute Pathname**:
     - Specifies the location of a file or directory from the root directory (/).
     - Always starts with a slash (/).
     - Example: `/home/user/file.txt`
   - **Relative Pathname**:
     - Related to the current working directory (pwd).
     - Does not start with a slash.
     - Example: `subdir/file.txt`
   - Use `.` (current directory) and `..` (parent directory) in relative paths.
3 . **What Does the Directory File Contain?**
In UNIX-like operating systems, directories do not directly contain files. Instead, they contain the names of files paired with references to so-called inodes.
An inode is a data structure that contains both the file’s actual data (content) and its metadata (such as owner, permissions, timestamps, etc.). However, the inode itself does not store the file name.
When you create a file, the operating system assigns it an inode number. The directory associates the file name with this inode number.
In summary, a directory contains a mapping of file names to their corresponding inode numbers.
What Does cd Do When Used Without an Argument?
The cd (change directory) command is used to navigate the file system by changing the current working directory.
When you use cd without specifying any directory name, it takes you to your home directory (the default starting location for a user)
4. **UNIX File System Structure**:
   - UNIX file system is a hierarchical tree structure.
   - Root directory (/) is the top-level directory.
   - Directories contain files and subdirectories.
   - Example: `/home/user/documents/notes.txt`

5. **`tar` Command**:
   - Used for archiving files and directories.
   - Creates a single archive file (usually with `.tar` extension).
   - Common options:
     - `-c`: Create an archive.
     - `-x`: Extract files from an archive.
     - `-v`: Verbose mode (show progress).
     - `-f`: Specify the archive file name.
   - Example: `tar -cvf archive.tar dir1 file1.txt`

Feel free to ask if you need further clarification or want to explore any specific topic! 🚀🔍

Source: Conversation with Copilot, 5/29/2024
(1) Internal and External Commands in Linux - GeeksforGeeks. https://www.geeksforgeeks.org/internal-and-external-commands-in-linux/.
(2) Linux - Difference between internal and external commands - CareerRide. https://www.careerride.com/Linux-internal-external-commands.aspx.
(3) What is internal and external commands in Unix? – Short-Question. https://short-question.com/what-is-internal-and-external-commands-in-unix/.
(4) Internal and external commands in Linux - ComputerNetworkingNotes. https://www.computernetworkingnotes.com/linux-tutorials/internal-and-external-commands-in-linux.html.
(5) Internal vs External Linux shell commands - LinuxConfig.org. https://linuxconfig.org/internal-vs-external-linux-shell-commands.
(6) Difference between Shell and Kernel - GeeksforGeeks. https://www.geeksforgeeks.org/difference-between-shell-and-kernel/.
(7) What is a Shell in Linux [A Comprehensive Summary] - LinuxSimply. https://linuxsimply.com/what-is-a-shell-linux/.
(8) Architecture of Linux Operating System - LinuxSimply. https://linuxsimply.com/linux-basics/introduction/architecture-of-linux-operating-system/.
(9) Difference Between Kernel and Shell - Pediaa.Com. https://pediaa.com/difference-between-kernel-and-shell/.
(10) What is the Linux kernel? - Red Hat. https://www.redhat.com/en/topics/linux/what-is-the-linux-kernel.
(11) Multi-User Operating System - GeeksforGeeks. https://www.geeksforgeeks.org/multi-user-operating-system/.
(12) Is UNIX An example of multi-user operating system?. https://yourwiseanswers.com/is-unix-an-example-of-multi-user-operating-system/.
(13) Multi-user systems - Computer Science Wiki. https://computersciencewiki.org/index.php/Multi-user_systems.
(14) Introduction to UNIX System - GeeksforGeeks. https://www.geeksforgeeks.org/introduction-to-unix-system/.
(15) Multi-User Operating Systems: Tracing the Legacy from Unix. https://cloudaffle.com/series/linux-permissions/multi-user-operating-systems/.
(16) Absolute path vs relative path in Linux/Unix. https://www.youtube.com/watch?v=sB77xnFhsJs.
(17) Absolute and Relative Paths. https://www.youtube.com/watch?v=ephId3mYu9o.
(18) What Is A Relative Path? | What Is An Absolute Path?. https://www.youtube.com/watch?v=J3Zkb9ona8E.
(19) Absolute and Relative Pathnames in UNIX - GeeksforGeeks. https://www.geeksforgeeks.org/absolute-relative-pathnames-unix/.
(20) Absolute vs Relative Path in Linux: What's the Difference?. https://linuxhandbook.com/absolute-vs-relative-path/.
(21) Absolute Pathname Definition - LINFO. https://www.linfo.org/absolute_pathname.html.
(22) ls - Absolute path to Relative Path in Unix - Stack Overflow. https://stackoverflow.com/questions/12189961/absolute-path-to-relative-path-in-unix.
### BASIC FILE attibutes
Certainly! Let's dive into each of your questions:

1. **Is It Possible for Two Files to Have the Same Inode Number?**
   - Yes, it is possible for two files to have the same inode number, but there are specific conditions:
     - If the files are part of different partitions or filesystems, they can share the same inode number.
     - Inodes are unique within a partition but not across the entire system.
     - Each partition has its own set of inodes, and the same inode number can be reused when a file is removed.
     - For example, if you have two files with the same inode number, they might be on different partitions or filesystems.

2. **What Is an Inode (i-node)?**
   - An inode (index node) is a data structure in a Unix-style file system that describes a file or directory.
   - Each inode stores attributes (metadata) and disk block locations of the object's data.
   - Inodes are created when the file system is initialized and are used to manage files and directories.
   - The inode contains information such as file size, permissions, timestamps, and pointers to data blocks.

3. **Output of `cat foo foo foo`**:
   - The `cat` command concatenates and displays the contents of files.
   - In this case, it will display the contents of the file named `foo` three times in a row.

4. **Difference Between Absolute and Relative Permissions**:
   - **Absolute Permissions**:
     - Specify permissions directly using octal notation (e.g., 755, 644).
     - Apply permissions universally to the owner, group, and others.
     - Examples: `chmod 755 file.txt` (read, write, execute for owner; read and execute for group and others).
   - **Relative Permissions**:
     - Modify existing permissions based on the current state.
     - Use `+` and `-` signs to add or remove permissions.
     - Examples: `chmod +x script.sh` (add execute permission), `chmod g-w file.txt` (remove write permission for group).

5. **Significance of Read, Write, and Execute on a Directory**:
   - Read (r): Allows listing the contents of the directory (e.g., using `ls`).
   - Write (w): Permits creating, deleting, and renaming files within the directory.
   - Execute (x): Enables changing into the directory (using `cd`) and viewing metadata of files inside it.

6. **Components of Inode Table**:
   - An inode typically contains:
     - File type (regular file, directory, device, etc.).
     - Owner and group IDs.
     - File size.
     - Timestamps (last modification, last access, last inode change).
     - Permissions (read, write, execute).
     - Pointers to data blocks (direct, indirect, double indirect, triple indirect).

7. **Utility of Umask**:
   - The `umask` sets default permissions for newly created files and directories.
   - It is subtracted from the maximum permissions (usually 666 for files and 777 for directories).
   - Umask is user-specific and affects the current shell session.
   - If the umask value is 023, the default permissions for files will be 644 (rw-r--r--).

8. **Use of `touch` Command**:
   - The `touch` command updates the access and modification timestamps of a file.
   - If the file doesn't exist, it creates an empty file with the specified name.
   - Common usage: `touch filename.txt`.

9. **Links (Hard Links vs. Symbolic Links)**:
   - **Hard Links**:
     - Point directly to the same inode as the original file.
     - Share the same data blocks and metadata.
     - Cannot link directories.
     - Changes to one hard link affect all others.
   - **Symbolic Links (Symlinks)**:
     - Point to the path of another file or directory.
     - Refer to the target by name, not inode.
     - Can link directories.
     - Changes to the original file do not affect symlinks.

Feel free to ask if you need further clarification on any of these topics! 🚀🔍

Source: Conversation with Copilot, 5/29/2024
(1) Inode in Operating System - GeeksforGeeks. https://www.geeksforgeeks.org/inode-in-operating-system/.
(2) inode - Wikipedia. https://en.wikipedia.org/wiki/Inode.
(3) Understanding UNIX / Linux filesystem Inodes - nixCraft. https://www.cyberciti.biz/tips/understanding-unixlinux-filesystem-inodes.html.
(4) Absolute, Relative, Fixed Positioning: How Do They Differ?. https://css-tricks.com/absolute-relative-fixed-positioining-how-do-they-differ/.
(5) Excel Formulas: Relative and Absolute Cell References - GCFGlobal.org. https://edu.gcfglobal.org/en/excelformulas/relative-and-absolute-cell-references/1/.
(6) What is absolute permission Unix? – Profound-tips. https://profound-tips.com/advice/what-is-absolute-permission-unix/.
(7) Absolute vs. Relative: What’s the Difference?. https://www.difference.wiki/absolute-vs-relative/.
(8) how can 2 unix files have the same inode, but the reference count for .... https://stackoverflow.com/questions/23671083/how-can-2-unix-files-have-the-same-inode-but-the-reference-count-for-the-inode.
(9) I have two same files in different directories with same inodes. https://stackoverflow.com/questions/56418742/i-have-two-same-files-in-different-directories-with-same-inodes.
(10) Two files can have a same inode number in the same file system .... https://www.sarthaks.com/2489824/two-files-can-have-a-same-inode-number-in-the-same-file-system.
(11) How do inode numbers from ls -i relate to inodes on disk. https://unix.stackexchange.com/questions/498495/how-do-inode-numbers-from-ls-i-relate-to-inodes-on-disk.
(12) Can two files have the same inode number? - LinuxQuestions.org. https://www.linuxquestions.org/questions/linux-newbie-8/can-two-files-have-the-same-inode-number-423094/.
(13) How to Use the chmod Command on Linux - How-To Geek. https://www.howtogeek.com/437958/how-to-use-the-chmod-command-on-linux/.
(14) Understanding Linux File Permissions - OSTechNix. https://ostechnix.com/linux-file-and-directory-permissions/.
(15) Linux Permissions: The Meaning of 755 and rwxr-xr-x. https://www.ssdnodes.com/blog/linux-permissions/.
(16) Classic SysAdmin: Understanding Linux File Permissions. https://www.linuxfoundation.org/blog/blog/classic-sysadmin-understanding-linux-file-permissions.
(17) unix - What does "cat foo foo foo does"? - Stack Overflow. https://stackoverflow.com/questions/7203866/what-does-cat-foo-foo-foo-does.
(18) Linux and Unix cat command tutorial with examples | George Ornbo. https://shapeshed.com/unix-cat/.
(19) The cat command | Coding Computing Coach. https://codingcomputing.github.io/linux/cat.html.
(20) http redirect - In UNIX what "cat file1 - Stack Overflow. https://stackoverflow.com/questions/3887771/in-unix-what-cat-file1-file1-does.
(21) The Cat Command in Linux — Concatenation Explained with Bash ... - Medium. https://medium.com/@zerodaystarts/the-cat-command-in-linux-concatenation-explained-with-bash-examples-2bd6fb38e40b.
(22) undefined. https://linux.die.net/man/1/namei%29.


### The shell
Certainly! Let's address each of your questions:

1. **Command Substitution**:
   - Command substitution allows you to capture the output of a command and use it as part of another command.
   - It is denoted by `$(command)` or backticks (`` `command` ``).
   - Example:
     ```bash
     current_date=$(date)
     echo "Today's date is: $current_date"
     ```
     This captures the output of `date` and assigns it to the `current_date` variable.

2. **Difference between `who | tee user.1st | wc -l` and `who | tee /dev/tty | wc -l`**:
   - `who | tee user.1st | wc -l`:
     - Redirects the output of `who` to both the file `user.1st` and standard output.
     - Counts the lines in the output.
   - `who | tee /dev/tty | wc -l`:
     - Redirects the output of `who` to both the terminal (`/dev/tty`) and standard output.
     - Counts the lines in the output.

3. **Why the Shell Is Called a "Command Interpreter"?**:
   - The shell interprets and executes commands entered by the user.
   - It acts as an interface between the user and the operating system.
   - The shell interprets user input, processes commands, and communicates with the kernel.

4. **Values of Expressions**:
   - Given `x = 10`:
     - `(i) x$x$`: Evaluates to `x10x`.
     - `(ii) $x$x`: Evaluates to `1010`.

5. **Shell Parameters**:
   - These special variables provide information about the shell and its execution:
     - `$!`: Process ID of the last background command.
     - `$#`: Number of arguments passed to the script or function.
     - `$@`: All arguments passed to the script or function as separate words.
     - `$*`: All arguments passed to the script or function as a single word.
     - `$0`: Name of the script or shell being executed.

6. **Utility of Wildcard Characters**:
   - Wildcards (such as `*`, `?`, and `[...]`) allow flexible pattern matching in filenames.
   - Examples:
     - `ls *.txt`: Lists all files with the `.txt` extension.
     - `Is ab?cd`: Matches filenames like `abcde`, `ab1cd`, etc.
     - `Is a[b-d][2-4]*d`: Matches filenames like `ab2cd`, `ad3ef`, etc.

7. **Types of Shell Variables**:
   - Shell variables include:
     - Environment variables (e.g., `PATH`, `HOME`).
     - User-defined variables (created during script execution).

8. **Significance of Shell Variables**:
   - `PS2`: Secondary prompt (used for multiline commands).
   - `TERM`: Terminal type (affects terminal behavior).
   - `PATH`: Specifies directories to search for executable files.

9. **Interpreting Instructions**:
   - `ls -a*`: Lists files starting with `a`.
   - `cp ?aa* ?ab*`: Copies files with names like `aa1.txt` to `ab2.txt`.



Feel free to ask if you need further clarification! 🚀🔍

Source: Conversation with Copilot, 5/29/2024
(1) Using Command Substitution in Bash Shell - Linux Handbook. https://linuxhandbook.com/bash-command-substitution/.
(2) Command substitution - Wikipedia. https://en.wikipedia.org/wiki/Command_substitution.
(3) Command Substitution for Bash Shell Scripting Beginners. https://www.putorius.net/command-substitution-bash.html.
(4) What is command substitution in a shell? [duplicate]. https://unix.stackexchange.com/questions/440088/what-is-command-substitution-in-a-shell.
(5) Shell Scripting - Command Substitution - GeeksforGeeks. https://www.geeksforgeeks.org/shell-scripting-command-substitution/.
(6) What Are the Special Dollar Sign Shell Variables? - Baeldung. https://www.baeldung.com/linux/shell-special-dollar-sign-variables.
(7) How to Pass Arguments to a Bash Shell Script - Linux Handbook. https://linuxhandbook.com/bash-arguments/.
(8) shell - How do I find information on bash special parameters .... https://stackoverflow.com/questions/20272085/how-do-i-find-information-on-bash-special-parameters-0.
(9) Why $0 is not a positional parameter? - Unix & Linux Stack Exchange. https://unix.stackexchange.com/questions/412707/why-0-is-not-a-positional-parameter.
(10) What are the special dollar sign shell variables? - Stack Overflow. https://stackoverflow.com/questions/5163144/what-are-the-special-dollar-sign-shell-variables.
(11) Why was the word "shell" used to describe a command-line interface?. https://unix.stackexchange.com/questions/14934/why-was-the-word-shell-used-to-describe-a-command-line-interface.
(12) operating system - shells vs command interpreters vs command line .... https://stackoverflow.com/questions/21464073/shells-vs-command-interpreters-vs-command-line.
(13) Command Interpreter - The Complete Guide to Bash Programming - Educative. https://www.educative.io/courses/guide-to-bash-programming/command-interpreter.
(14) What Is the Bash Shell, and Why Is It So Important to Linux? - How-To Geek. https://www.howtogeek.com/726559/what-is-the-bash-shell-and-why-is-it-so-important-to-linux/.
(15) Shell (computing) - Wikipedia. https://en.wikipedia.org/wiki/Shell_%28computing%29.
(16) shell - What is the purpose of 'tee'? - Super User. https://superuser.com/questions/1356841/what-is-the-purpose-of-tee.
(17) Tee-Object (Microsoft.PowerShell.Utility) - PowerShell. https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-7.4.
(18) Men's T20 World Cup 2024 teams, format, venues and how to ... - Sky Sports. https://www.skysports.com/cricket/news/12123/13140731/men-s-t20-world-cup-2024-teams-format-venues-and-how-to-follow-on-sky-sports.
(19) shell - How do I escape the wildcard/asterisk character in bash .... https://stackoverflow.com/questions/102049/how-do-i-escape-the-wildcard-asterisk-character-in-bash.
(20) Wildcard Selection in Bash – Developers ultimate guide: Linux Bash .... https://pressbooks.senecapolytechnic.ca/uli101/chapter/wildcard-selection-in-bash/.
(21) How to use wildcards, by The Linux Information Project (LINFO). https://www.linfo.org/wildcard.html.
(22) Intro to regular expressions: Shell wildcards - a type of regex. https://csiro-data-school.github.io/regex/02-shell-wildcards/index.html.
(23) undefined. http://en.wikipedia.org/wiki/Thompson_shell.
(24) undefined. http://www.multicians.org/shell.html.


### Customizing the environment

1. **System Variables**:
   - System variables are global and apply to the entire operating system. They are accessible by all users and programs running on the system.
   - These variables provide critical information about system resource locations, configurations, and behavior.
   - Let's delve into the descriptions of some commonly used system variables:

   - **HOME**:
     - The `HOME` variable points to the user's home directory.
     - It specifies the default location where user-specific files (such as configuration files) are stored.
     - For example, in Unix-like systems, it typically points to `/home/username`.

   - **PATH**:
     - The `PATH` variable defines a list of directories where the system looks for executable files (commands).
     - When you run a command in the terminal or a script, the system checks these directories to find the corresponding executable.
     - Adding folders to the `PATH` allows for easier execution of commands and scripts.

   - **LOGNAME**:
     - The `LOGNAME` variable contains the login name of the current user.
     - It helps identify the user who is currently logged in.

   - **PWD**:
     - The `PWD` variable holds the current working directory (i.e., the directory where you are currently located).
     - It's useful for scripts and programs that need to know the context of their execution.

   - **PS1 and PS2**:
     - `PS1` (Primary Prompt) and `PS2` (Secondary Prompt) are variables that define the appearance of the command prompt in the terminal.
     - `PS1` is the main prompt displayed before you enter a command.
     - `PS2` is the continuation prompt shown when a command spans multiple lines.

   - **SHELL**:
     - The `SHELL` variable specifies the default shell (command interpreter) for the user.
     - It points to the path of the shell executable (e.g., `/bin/bash`).

   - **IFS (Internal Field Separator)**:
     - The `IFS` variable defines the delimiter used to split strings into fields.
     - It affects how commands like `read` or `for` loop through input data.

2. **Utilities of Environment Variables**:
   - Environment variables serve several purposes:
     - **Configuration**: They allow you to customize system behavior and application settings.
     - **Security**: They store sensitive information (e.g., API keys, passwords) securely.
     - **Dynamic Behavior**: They add flexibility by allowing scripts to adapt based on the environment.
     - **Resource Paths**: They point to critical directories (e.g., Temp folder, Program Files) used by various programs.
     - **Script Conciseness**: They make scripts more concise by storing reusable values.

Remember that changing environment variables can impact system behavior, so always double-check before modifying them. 🚀🔍\


### Filters

1. Write an awk script to find the frequency of words present in the text file MATTER. Print only those words whose frequency is 5 or more.

Create an `awk` script named `word_frequency.awk`:
```sh
#!/usr/bin/awk -f

{
  for (i = 1; i <= NF; i++) {
    words[tolower($i)]++
  }
}

END {
  for (word in words) {
    if (words[word] >= 5) {
      print word, words[word]
    }
  }
}
```
Run the script:
```sh
awk -f word_frequency.awk MATTER
```

2. A file named MARKS consists of name, Marks1, Marks2, Marks3 and Marks4 fields, separated by commas. Print the marks of those whose average marks are equal to or greater than 50%, in descending order of average marks, followed by alphabetical order of name in the following format:
```
Sl. No.
Name
Avg. Marks
```
Write the program (shell script or awk script) to accomplish the above task.

Create an `awk` script named `process_marks.awk`:
```sh
#!/usr/bin/awk -f

BEGIN {
  FS = ","
}

{
  avg = ($2 + $3 + $4 + $5) / 4
  if (avg >= 50) {
    students[$1] = avg
  }
}

END {
  n = 0
  PROCINFO["sorted_in"] = "@val_num_desc"
  for (name in students) {
    sorted_students[++n] = name
  }
  
  PROCINFO["sorted_in"] = "@ind_str_asc"
  asort(sorted_students)
  
  printf "Sl. No.\tName\tAvg. Marks\n"
  for (i = 1; i <= n; i++) {
    name = sorted_students[i]
    printf "%d\t%s\t%.2f\n", i, name, students[name]
  }
}
```

Run the script:
```sh
awk -f process_marks.awk MARKS
```

3. Explain the differences between grep and sed commands in UNIX.

**`grep` (Global Regular Expression Print):**
- Purpose: Used primarily for searching text using patterns.
- Functionality: Searches for lines that match a specified pattern and outputs the matching lines.
- Syntax: `grep [options] pattern [file...]`
- Example: `grep "hello" file.txt`

**`sed` (Stream Editor):**
- Purpose: Used for text manipulation and transformation.
- Functionality: Can perform complex text manipulations such as search and replace, insertion, deletion, and more.
- Syntax: `sed [options] 'script' [file...]`
- Example: `sed 's/hello/world/g' file.txt` (replaces all instances of "hello" with "world" in the file)

**Key Differences:**
- `grep` is used mainly for searching text patterns and printing matching lines, whereas `sed` is a full-fledged stream editor capable of performing a variety of text transformations.
- `grep` outputs matching lines, while `sed` can modify the text content directly and output the modified text.
- `grep` can use regular expressions for pattern matching, while `sed` uses regular expressions for search and replace operations.

4. What are the two ways to specify pattern and action to the awk command?

1. **Command-Line:** You can specify the pattern and action directly in the command line.
   ```sh
   awk '/pattern/ { action }' filename
   ```
   Example:
   ```sh
   awk '/error/ { print $0 }' logfile.txt
   ```

2. **Script File:** You can write a series of `awk` commands in a script file and then execute it.
   Create a script file `script.awk`:
   ```awk
   /pattern/ {
     action
   }
   ```
   Run the script:
   ```sh
   awk -f script.awk filename
   ```

5. Write a simple awk program that asks for a word and a file name and then tells you the number of occurrences of that word in that file.

Create a shell script named `count_word.sh`:
```sh
#!/bin/bash

echo -n "Enter the word: "
read word
echo -n "Enter the filename: "
read filename

awk -v word="$word" '
{
  for (i = 1; i <= NF; i++) {
    if ($i == word) {
      count++
    }
  }
}
END {
  print "The word \"" word "\" appears " count " times in the file " FILENAME
}
' "$filename"
```

Make the script executable:
```sh
chmod +x count_word.sh
```

Run the script:
```sh
./count_word.sh
```

This script prompts the user to enter a word and a filename, then uses `awk` to count the occurrences of the word in the specified file.


### Filters01
1. Write an awk script to find the frequency of words present in the text file MATTER. Print only those words 
whose frequency is 5 or more. 

answer:-
To find the frequency of words in the text file “MATTER” and print only those words whose frequency is 5 or more, you can use the following AWK script:
awk '{for(i=1;i<=NF;i++) 
a[$i]++} END {for(k in a) 
if(a[k]>=5) 
print k,a[k]}' MATTER

This script counts the occurrences of each word and prints only those with a frequency of 5 or more.


2. A file named MARKS consists of name, Marks1, Marks2, Marks3 and Marks4 fields, separated by comma. 
Print the marks of those whose average marks are equal to or greater than 50%, in descending order of 
average marks, followed by alphabetical order of name in the following format : 
Sl. No. 
Name 
Avg. Marks 

answer:-
Assuming the “MARKS” file has the following format (name, Marks1, Marks2, Marks3, Marks4 separated by commas):
John,80,75,90,85
Alice,70,85,80,95
...

To print the marks of those whose average marks are equal to or greater than 50%, in descending order of average marks, followed by alphabetical order of name:
awk -F, '{avg = ($2 + $3 + $4 + $5) / 4; if (avg >= 50) print $1, avg}' MARKS | sort -k2nr -k1

This script calculates the average marks, filters based on the condition, and sorts the output.


3. Explain the differences between grep and sed commands in UNIX. 

answer:-
grep:
Searches for lines matching a regex pattern and prints those matching lines.
Used for simple text matching and printing.
sed:
Stream Editor.
Used for string replacement and more complex text transformations.


4. What are the two ways to specify pattern and action to the awk command?

answer:-
Pattern:
A condition that is matched against each line of input.
Tells AWK what to look for in the content of the files.
Action:
Set of commands executed when a match is found within a line.
Defines what to do once a pattern is matched.


5. Write a simple awk program that asks for a word and a file name and then tells you the no. of occurrences of that word into that file.
answer:-
To count the occurrences of a word in a file:
awk -v word="your_word" '{count += gsub(word, word)} END {print count}' your_file

Replace “your_word” with the desired word and “your_file” with the actual file name.


///











### The Process 
1. What is meant by daemon process? Name any two daemon processes.
**Daemon Process**:
   - A **daemon process** (or simply a **daemon**) is a computer program that runs as a **background process**, independent of direct user control.
   - Daemons perform various system tasks, such as managing hardware, handling network requests, or providing services.
   - Examples of daemon processes:
     - **syslogd**: Implements system logging facility.
     - **sshd**: Serves incoming SSH connections.
     - **cron**: Executes defined tasks at scheduled times.


2. What is Job? 
**Job**:
   - A **job** refers to a unit of work or a task that a process needs to perform.
   - Jobs can be executed by processes or scheduled by system utilities (e.g., cron jobs).


3. How is process created? Mention briefly the role of the fork and exec system calls in process creation. 
**Process Creation**:
   - When a new process is created:
     1. The operating system assigns a **unique Process Identifier (PID)** to it and inserts an entry in the process table.
     2. Memory space is allocated for the program, data, stack, and the **Process Control Block (PCB)**.
     3. The PCB is initialized with relevant information (e.g., PID, parent's PID, program counter, stack pointer).
     4. The process transitions from the 'New' state to the 'Ready' state, competing for CPU time.


4. What are fork and exec system calls meant for? How are they different? 
   - **fork()**:
     - Creates a new process by duplicating the calling process.
     - The child process is an exact duplicate of the parent, except for specific differences (e.g., unique PID).
     - Returns the child's PID to the parent and 0 to the child.
   - **exec()**:
     - Replaces the current process image with a new one.
     - Loads the program into memory and runs it from the entry point.
     - Various forms of exec() allow specifying the program path and arguments.


5. What is zombie state? What is zombie process? 
   - A **zombie process** is a terminated process that remains in the process table.
   - It exists until its parent process reaps it (reads exit status and other information).
   - Zombies waste system resources and can fill up the process table.


6. What is the significance of the PID and the PPID? 
   - **PID (Process Identifier)**: A unique numeric ID assigned to each process.
   - **PPID (Parent Process ID)**: The PID of the parent process that created the current process.


7. What do the terms UID, PID and PPID stand for? For a currently executing process how can you obtain 
these values? 
   - **UID (User Identifier)**: Identifies the user associated with the process.
   - **PID (Process Identifier)**: Unique numeric ID for the process.
   - **PPID (Parent Process ID)**: PID of the parent process.


8. Describe Race Condition & Critical Section. 
   - **Race Condition**: Occurs when multiple processes access shared resources concurrently, leading to unpredictable behavior.
   - **Critical Section**: A portion of code that must be executed atomically to avoid race conditions.


9. With the help of proper diagram, explain the various states of a process. Give a brief statement describing 
each state. 
   - Diagram:
     ```
     New -> Ready -> Running -> Blocked -> Terminated
     ```
   - Brief descriptions:
     - **New**: Process is being created.
     - **Ready**: Process is ready to run but waiting for CPU time.
     - **Running**: Process is actively executing.
     - **Blocked**: Process is waiting for an event (e.g., I/O).
     - **Terminated**: Process has completed execution.

10. Explain 'Booting' process in UNIX O.S. 

    - **Booting** refers to the process of starting up a computer system.
    - In UNIX, the boot process involves loading the kernel, initializing hardware, and launching system services.

11. What is a background process? How can a process be run in background?
    - A **background process** runs independently of the user's current session.
    - To run a process in the background, use the `&` symbol after the command (e.g., `command &`).
