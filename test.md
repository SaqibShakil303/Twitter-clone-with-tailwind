### Shell Programming

1. **Prime Number Check**:
1. Write a shell script to check whether an integer is prime or not.
   - To check whether an integer is prime or not, you can use the following shell script:
     ```bash
     #!/bin/bash
     echo "Enter an integer:"
     read num

     is_prime=1
     for ((i = 2; i <= num / 2; i++)); do
         if ((num % i == 0)); then
             is_prime=0
             break
         fi
     done

     if ((is_prime == 1)); then
         echo "$num is a prime number."
     else
         echo "$num is not a prime number."
     fi
     ```
   - Replace the sample input (`num`) with the actual integer you want to check.

2. **Words with Same Beginning and Last Character**:
2. Write a shell script to print only those words of the file FILE, whose beginning and last character are the same.
   - To print only those words from a file (e.g., `FILE`) whose beginning and last character are the same:
     ```bash
     #!/bin/bash
     awk 'substr($0, 1, 1) == substr($0, length) {print}' FILE
     ```
   - Replace `FILE` with the actual file name.

3. **Print Number in Reverse Order**:
3. Write a shell script to print a given number in reverse order.

   - To print a given number in reverse order:
     ```bash
     #!/bin/bash
     echo "Enter a number:"
     read n

     rev=0
     while [ $n -gt 0 ]; do
         sd=$((n % 10))
         rev=$((rev * 10 + sd))
         n=$((n / 10))
     done

     echo "Reverse number of entered digit is $rev"
     ```

4. **Delete Files Older Than 15 Days with Extension 'tmp'**:
4. Write a shell script to delete all files in root and its subdirectories having extension 'tmp', which have not been created or referred to in the last 15 days.
   - To delete files in root and its subdirectories with extension 'tmp' that haven't been accessed in the last 15 days:
     ```bash
     find / -type f -name '*.tmp' -atime +15 -exec rm -f {} \;
     ```
   - Adjust the path (`/`) and extension (`*.tmp`) as needed.
   #!/bin/bash

5. **Print Marks Above 50% in Descending Order**:
5. Write a script to print marks of students whose average marks are equal to or greater than 50%, sorted by average marks and name.
   - Assuming the "MARKS" file has the format: `Name,Marks1,Marks2,Marks3,Marks4`:
     ```bash
     #!/bin/bash
     awk -F, 'NR > 1 && ($2 + $3 + $4 + $5) / 4 >= 50 {print $1, ($2 + $3 + $4 + $5) / 4}' MARKS | sort -k2nr
     ```
   - This script calculates the average marks, filters based on the condition, and sorts the output.

Certainly! Let's address each of the topics:

6. **Compile and Execute All C Files in the Current Directory**:
6. Write a shell script that will compile & execute all C files in the current directory.
   - To compile and execute all C files in the current directory, you can use the following shell script:
     ```bash
     #!/bin/bash
     for file in *.c; do
         gcc -o "${file%.c}" "$file"
         "./${file%.c}"
     done
     ```
   - This script iterates through all `.c` files, compiles them, and executes the resulting executables.

7. **Factorial of a Number using Command Line Argument**:
7. Write a shell script that will display the factorial of a number supplied as a command-line argument.
   - To display the factorial of a number supplied as a command line argument:
     ```bash
     #!/bin/bash
     if [ $# -ne 1 ]; then
         echo "Usage: $0 <number>"
         exit 1
     fi

     num=$1
     fact=1
     for ((i = 1; i <= num; i++)); do
         fact=$((fact * i))
     done

     echo "Factorial of $num is $fact"
     ```

8. **Enter Elements into an Array and Display Summation**:
8. Write a shell script to enter elements into an array & display the summation of all the elements.
   - To enter elements into an array and display the summation:
     ```bash
     #!/bin/bash
     echo "Enter the number of elements:"
     read n

     echo "Enter $n elements:"
     for ((i = 0; i < n; i++)); do
         read arr[i]
     done

     sum=0
     for ((i = 0; i < n; i++)); do
         sum=$((sum + arr[i]))
     done

     echo "Sum of elements: $sum"
     ```

9. **Positional Parameters**:
9. What do you mean by positional parameters? How do you refer to positional parameters within shell scripts? Give a suitable example.
   - Positional parameters are arguments passed to a script or function when executed.
   - They are accessed using variables like `$1`, `$2`, `$3`, etc., representing the first, second, third, and subsequent parameters.
   - Example:
     ```bash
     #!/bin/bash
     echo "First argument: $1"
     echo "Second argument: $2"
     ```

10. **Display Command Line Arguments in Different Lines**:
10. Write a shell script that displays all the command-line arguments passed with the name of the program in different lines (1 argument in each line).
    - To display all command line arguments passed with the name of the program:
      ```bash
      #!/bin/bash
      echo "Program name: $0"
      for arg in "$@"; do
          echo "$arg"
      done
      ```

11. **Display User Information from /etc/passwd**:
11. Write a shell script that accepts a username from the user and displays all the information about the user from the `/etc/passwd` file in a customized format.
    - To accept a username and display information from `/etc/passwd`:
      ```bash
      #!/bin/bash
      echo "Enter a username:"
      read username

      grep "^$username:" /etc/passwd
      ```

12. **Check System Time and Greet User**:
12. Write a shell script that checks the system time and currently logged-in username and wishes him/her "GOOD MORNING" or "GOOD AFTERNOON" according to the time.
    - To check the system time and greet the user accordingly:
      ```bash
      #!/bin/bash
      current_hour=$(date +%H)

      if [ "$current_hour" -ge 0 ] && [ "$current_hour" -lt 12 ]; then
          echo "GOOD MORNING!"
      else
          echo "GOOD AFTERNOON!"
      fi
      ```

13. **Store File Information in a Backup File**:
13. Write a shell program to store the names, size, and permissions of all the regular files present in the current directory in a file named `backup`.

    - To store the names, size, and permissions of regular files in the current directory:
      ```bash
      #!/bin/bash
      find . -type f -exec ls -l {} \; > backup.txt
      ```

14. **Count Positive and Negative Numbers from Command Line**:
14. Write a shell script to input numbers at the command line and print a count of positive and negative numbers entered.
    - To input numbers at the command line and print the count of positive and negative numbers:
      ```bash
      #!/bin/bash
      pos_count=0
      neg_count=0

      for num in "$@"; do
          if [ "$num" -gt 0 ]; then
              pos_count=$((pos_count + 1))
          elif [ "$num" -lt 0 ]; then
              neg_count=$((neg_count + 1))
          fi
      done

      echo "Positive numbers: $pos_count"
      echo "Negative numbers: $neg_count"
      ```

🚀🔍🚀🔍

Source: Conversation with Copilot, 5/27/2024
(1) Shell Program to Calculate the Factorial of a Number. https://www.geeksforgeeks.org/shell-program-to-calculate-the-factorial-of-a-number/.
(2) shell script to find factorial of a number - Log2Base2. https://www.log2base2.com/shell-script-examples/loop/shell-script-to-find-factorial-of-a-number.html.
(3) Shell script find the factorial of a given number - Teachics. https://teachics.org/linux-shell-scripts/shell-script-find-the-factorial-of-a-given-number/.
(4) Shell script to find factorial of a number · GitHub. https://gist.github.com/manojjha/6b610a728a2a6cadd262a3491db8a893.
(5) How to Use Command Line Arguments in a Bash Script. https://www.baeldung.com/linux/use-command-line-arguments-in-bash-script.
(6) Bash all arguments print - Learn Linux Configuration. https://linuxconfig.org/how-do-i-print-all-arguments-submitted-on-a-command-line-from-a-bash-script.
(7) How to Pass Command Line Arguments to Bash Script - LinuxTechi. https://www.linuxtechi.com/command-line-arguments-in-linux-shell-scripting/.
(8) How do I parse command line arguments in Bash? - Stack Overflow. https://stackoverflow.com/questions/192249/how-do-i-parse-command-line-arguments-in-bash.
(9) How can I find the sum of the elements of an array in Bash?. https://stackoverflow.com/questions/13635293/how-can-i-find-the-sum-of-the-elements-of-an-array-in-bash.
(10) How to add array elements in shell script - Log2Base2. https://www.log2base2.com/shell-script-examples/array/how-to-add-array-elements-in-shell-script.html.
(11) powershell - How to add a sum of numbers in an array - Stack Overflow. https://stackoverflow.com/questions/58386503/how-to-add-a-sum-of-numbers-in-an-array.
(12) Bash- sum values from an array in one line - Stack Overflow. https://stackoverflow.com/questions/13682408/bash-sum-values-from-an-array-in-one-line.
(13) How to Use Positional Parameters in Bash Script? [2 Examples]. https://linuxsimply.com/bash-scripting-tutorial/parameters/positional-parameters/.
(14) What is a Positional Parameter? - Computer Hope. https://www.computerhope.com/jargon/p/positional-parameter.htm.
(15) Positional Parameters (Bash Reference Manual). https://www.gnu.org/software/bash/manual/html_node/Positional-Parameters.html.
(16) How to use positional parameters - Linux Bash Shell Scripting Tutorial Wiki. https://bash.cyberciti.biz/guide/How_to_use_positional_parameters.
(17) How to compile all the c files in given directory? [closed]. https://stackoverflow.com/questions/32029445/how-to-compile-all-the-c-files-in-given-directory.
(18) shell script - Compiling c/cpp files in a directory given as an input .... https://unix.stackexchange.com/questions/373974/compiling-c-cpp-files-in-a-directory-given-as-an-input.
(19) How to search subdirectories for .c files and compile them (shell .... https://stackoverflow.com/questions/16621187/how-to-search-subdirectories-for-c-files-and-compile-them-shell-scripting.
(20) Shell script to compile C files - Unix & Linux Stack Exchange. https://unix.stackexchange.com/questions/137066/shell-script-to-compile-c-files.

Source: Conversation with Copilot, 5/27/2024
(1) Delete files older than 10 days using shell script in Unix. https://stackoverflow.com/questions/13489398/delete-files-older-than-10-days-using-shell-script-in-unix.
(2) linux - Bash script to delete files older than x days with .... https://superuser.com/questions/375011/bash-script-to-delete-files-older-than-x-days-with-subdirectories.
(3) bash - Remove all files older than X days, but keep at least the Y .... https://stackoverflow.com/questions/20358865/remove-all-files-older-than-x-days-but-keep-at-least-the-y-youngest.
(4) Bash program to check if the Number is a Prime or not. https://www.geeksforgeeks.org/bash-program-to-check-if-the-number-is-a-prime-or-not/.
(5) how to check prime number in shell script - Code Examples & Solutions. https://www.grepper.com/answers/239972/how+to+check+prime+number+in+shell+script.
(6) Check if a Number Is a Prime in Bash | Baeldung on Linux. https://www.baeldung.com/linux/bash-prime-number-test.
(7) how to check prime number in shell script - IQCode. https://iqcode.com/code/shell/how-to-check-prime-number-in-shell-script.
(8) Shell Script to Check Prime Number – TecAdmin. https://tecadmin.net/shell-script-to-check-prime-number/.
(9) shell - Print a character repeatedly in bash - Stack Overflow. https://stackoverflow.com/questions/5799303/print-a-character-repeatedly-in-bash.

1. Write a shell script to check whether an integer is prime or not.

#!/bin/bash
echo -n "Enter a number: "
read num
if [ $num -lt 2 ]; then
  echo "$num is not a prime number."
  exit
fi

for ((i=2; i<=num/2; i++))
do
  if [ $((num % i)) -eq 0 ]; then
    echo "$num is not a prime number."
    exit
  fi

done

echo "$num is a prime number."
```

2. Write a shell script to print only those words of the file FILE, whose beginning and last character are the same.

#!/bin/bash
echo -n "Enter the filename: "
read filename

if [ ! -f "$filename" ]; then
  echo "File does not exist."
  exit
fi

while read -r line; do
  for word in $line; do
    if [[ ${word:0:1} == ${word: -1} ]]; then
      echo $word
    fi
  done
done < "$filename"
```

3. Write a shell script to print a given number in reverse order.

#!/bin/bash
echo -n "Enter a number: "
read num

reversed=0

while [ $num -ne 0 ]; do
  remainder=$((num % 10))
  reversed=$((reversed * 10 + remainder))
  num=$((num / 10))
done

echo "Reversed number: $reversed"
```

4. Write a shell script to delete all files in root and its subdirectories having extension 'tmp', which have not been created or referred to in the last 15 days.

#!/bin/bash
find / -type f -name "*.tmp" -atime +15 -exec rm -f {} \;
```

5. Write a script to print marks of students whose average marks are equal to or greater than 50%, sorted by average marks and name.

#!/bin/bash
awk -F, '
BEGIN { print "Sl. No.\tName\tAvg. Marks" }
{
  avg = ($2 + $3 + $4 + $5) / 4
  if (avg >= 50) {
    students[$1] = avg
  }
}
END {
  n = asort(students, sorted_students)
  for (i = 1; i <= n; i++) {
    print i "\t" sorted_students[i] "\t" students[sorted_students[i]]
  }
}
' MARKS
```

6. Write a shell script that will compile & execute all C files in the current directory.

#!/bin/bash

for file in *.c; do
  if [ -f "$file" ]; then
    gcc "$file" -o "${file%.c}"
    if [ $? -eq 0 ]; then
      echo "Running ${file%.c}:"
      ./"${file%.c}"
    else
      echo "Compilation of $file failed."
    fi
  fi
done
```
7. Write a shell script that will display the factorial of a number supplied as a command-line argument.


#!/bin/bash
factorial() {
  num=$1
  fact=1
  for ((i=2; i<=num; i++)); do
    fact=$((fact * i))
  done
  echo $fact
}

if [ $# -eq 1 ]; then
  result=$(factorial $1)
  echo "Factorial of $1 is $result"
else
  echo "Please provide a number."
fi
```

8. Write a shell script to enter elements into an array & display the summation of all the elements.

#!/bin/bash

echo -n "Enter the number of elements: "
read n
echo "Enter the elements:"

sum=0

for ((i=0; i<n; i++)); do
  read arr[$i]
  sum=$((sum + arr[$i]))
done

echo "Sum of the elements: $sum"
```

9. What do you mean by positional parameters? How do you refer to positional parameters within shell scripts? Give a suitable example.

**Positional Parameters:**
Positional parameters are variables that hold the arguments passed to a script or function. They are referenced using `$1`, `$2`, `$3`, etc., where `$1` is the first argument, `$2` is the second, and so on. `$0` refers to the name of the script itself.

**Example:**
#!/bin/bash

echo "Script name: $0"
echo "First argument: $1"
echo "Second argument: $2"
```
If you run the script as `./script.sh arg1 arg2`, it will output:
```
Script name: ./script.sh
First argument: arg1
Second argument: arg2
```

10. Write a shell script that displays all the command-line arguments passed with the name of the program in different lines (1 argument in each line).

#!/bin/bash
echo "Script name: $0"

for arg in "$@"; do
  echo "Argument: $arg"
done
```

11. Write a shell script that accepts a username from the user and displays all the information about the user from the `/etc/passwd` file in a customized format.

#!/bin/bash
echo -n "Enter username: "
read username

userinfo=$(grep "^$username:" /etc/passwd)

if [ -z "$userinfo" ]; then
  echo "User not found."
else
  IFS=: read -r uname pwd uid gid fullname home shell <<< "$userinfo"
  echo "Username: $uname"
  echo "Full Name: $fullname"
  echo "User ID: $uid"
  echo "Group ID: $gid"
  echo "Home Directory: $home"
  echo "Shell: $shell"
fi
```

12. Write a shell script that checks the system time and currently logged-in username and wishes him/her "GOOD MORNING" or "GOOD AFTERNOON" according to the time.

#!/bin/bash
hour=$(date +"%H")
username=$(whoami)

if [ $hour -lt 12 ]; then
  echo "GOOD MORNING, $username!"
else
  echo "GOOD AFTERNOON, $username!"
fi
```

13. Write a shell program to store the names, size, and permissions of all the regular files present in the current directory in a file named `backup`.

#!/bin/bash
ls -l | grep "^-" | awk '{print $9, $5, $1}' > backup
```
14. Write a shell script to input numbers at the command line and print a count of positive and negative numbers entered.

#!/bin/bash
positive=0
negative=0

for num in "$@"; do
  if [ $num -gt 0 ]; then
    positive=$((positive + 1))
  elif [ $num -lt 0 ]; then
    negative=$((negative + 1))
  fi
done

echo "Positive numbers: $positive"
echo "Negative numbers: $negative"
```

These scripts cover various common shell programming tasks, demonstrating the use of shell variables, loops, conditionals, and file operations. Adjustments may be necessary based on specific shell implementations and user requirements.



Certainly! Let's address each of the topics:

1. **Command Substitution**:
   - Command substitution is a mechanism in shell scripting where the output of a command replaces the command itself.
   - It allows you to use the output of a command as an argument to another command.
   - Syntax: `$(command)` or `` `command` ``
   - Example:
     ```bash
     # Assign the current date to a variable
     current_date=$(date +%Y-%m-%d)
     echo "Today's date is $current_date"
     ```

2. **Difference Between `who | tee user.1st | wc -l` and `who | tee /dev/tty | wc -l`**:
   - `who | tee user.1st | wc -l`:
     - Redirects the output of `who` to both the file `user.1st` and the standard output.
     - Counts the number of lines in the output.
   - `who | tee /dev/tty | wc -l`:
     - Redirects the output of `who` to both the terminal (standard output) and the standard output.
     - Counts the number of lines in the output.

3. **Why the Shell Is Called a "Command Interpreter"?**:
   - The shell acts as an interface between the user and the operating system kernel.
   - It interprets and processes commands entered by the user.
   - It converts user commands into a form that the kernel can understand.
   - Thus, it is called a "command interpreter."

4. **Values of `x$x$` and `$x$x` (Given x = 10)**:
   - `x$x$`: Evaluates to `1010`.
   - `$x$x`: Evaluates to `1010`.

5. **Shell Parameters**:
   - `$!`: Process ID of the last background command.
   - `$#`: Number of arguments passed to the script or function.
   - `$@`: All arguments passed to the script or function as separate words.
   - `$*`: All arguments passed to the script or function as a single word.
   - `$0`: Name of the script or shell being executed.

6. **Utility of Wildcard Characters**:
   - Wildcard characters (such as `*`, `?`, and `[...]`) allow pattern matching in filenames.
   - Examples:
     - `ls *.txt`: Lists all files with the `.txt` extension.
     - `cp ?aa* ?ab*`: Copies files with names starting with `aa` followed by any characters to files with names starting with `ab`.

7. **Types of Shell Variables**:
   - Environment variables (e.g., `PATH`, `HOME`, `LOGNAME`).
   - Local variables (defined within a script or function).
   - Special variables (e.g., `$0`, `$#`, `$@`, `$*`, `$!`).

8. **Significance of Shell Variables**:
   - `PS2`: Secondary prompt (used when input spans multiple lines).
   - `TERM`: Terminal type (used for terminal emulation).
   - `PATH`: List of directories where executable files are searched.
   - Other variables like `IFS` (input field separator) are also significant.

Certainly! Let's interpret the given instructions:

1. **`ls -a*`**:
   - This command lists the contents of the current directory, including hidden files (those starting with a dot `.`).
   - The `-a` option stands for "all" and includes hidden files.
   - The `*` is a wildcard character that matches any sequence of characters.
   - So, it lists all files and directories (including hidden ones) whose names start with the letter `a`.

2. **`cp ?aa* ?ab*`**:
   - This command copies files from one location to another.
   - The `?` is a wildcard character that matches any single character.
   - The `aa*` matches any file or directory name that starts with `aa`.
   - The `?ab*` matches any file or directory name that starts with any single character followed by `ab`.

In summary:
- The first command lists hidden files starting with the letter `a`.
- The second command copies files or directories whose names start with `aa` to new names starting with `ab`. For example, if there's a file named `aafile.txt`, it will be copied to `abfile.txt`. Similarly, if there's a directory named `aadir`, it will be copied to `abdir`.



Feel free to ask if you need further clarification on any of these topics! 🚀🔍

Source: Conversation with Copilot, 5/27/2024
(1) What Are the Special Dollar Sign Shell Variables? - Baeldung. https://www.baeldung.com/linux/shell-special-dollar-sign-variables.
(2) What are the special dollar sign shell variables? - Stack Overflow. https://stackoverflow.com/questions/5163144/what-are-the-special-dollar-sign-shell-variables.
(3) Bash Special Variables ($0, $?, $#, $@, $$, $*) – TecAdmin. https://tecadmin.net/bash-special-variables/.
(4) How to properly handle wildcard expansion in a bash shell script?. https://stackoverflow.com/questions/258211/how-to-properly-handle-wildcard-expansion-in-a-bash-shell-script.
(5) Wildcards - Linux Bash Shell Scripting Tutorial Wiki - nixCraft. https://bash.cyberciti.biz/guide/Wildcards.
(6) How to use wildcards, by The Linux Information Project (LINFO). https://www.linfo.org/wildcard.html.
(7) Linux wildcards | How do wildcards work in Linux with examples? - EDUCBA. https://www.educba.com/linux-wildcards/.
(8) ICC Twenty20 World Cup 2024: Full schedule, venues and complete squads. https://www.thehindu.com/sport/cricket/icc-twenty20-world-cup-2024-full-schedule-venues-and-complete-squads/article68145690.ece.
(9) ICC Men's T20 World Cup, 2024. https://www.t20worldcup.com/.
(10) Vaughan's mouth-shutting reply to Pakistan journalist's 'will you .... https://www.hindustantimes.com/cricket/michael-vaughan-mouth-shutting-reply-pakistan-journalist-will-you-apologise-if-we-win-t20-world-cup-ipl-eng-vs-pak-101716714224080.html.
(11) Shell Scripting - Command Substitution - GeeksforGeeks. https://www.geeksforgeeks.org/shell-scripting-command-substitution/.
(12) Command substitution - Wikipedia. https://en.wikipedia.org/wiki/Command_substitution.
(13) Command Substitution for Bash Shell Scripting Beginners. https://www.putorius.net/command-substitution-bash.html.
(14) Command substitution in the C shell - IBM. https://www.ibm.com/docs/en/aix/7.2?topic=commands-command-substitution-in-c-shell.
(15) Using Command Substitution in Bash Shell - Linux Handbook. https://linuxhandbook.com/bash-command-substitution/.
(16) Why was the word "shell" used to describe a command-line interface?. https://unix.stackexchange.com/questions/14934/why-was-the-word-shell-used-to-describe-a-command-line-interface.
(17) operating system - shells vs command interpreters vs command line .... https://stackoverflow.com/questions/21464073/shells-vs-command-interpreters-vs-command-line.
(18) Command Interpreter - The Complete Guide to Bash Programming - Educative. https://www.educative.io/courses/guide-to-bash-programming/command-interpreter.
(19) Introduction to Linux Shell and Shell Scripting - GeeksforGeeks. https://www.geeksforgeeks.org/introduction-linux-shell-shell-scripting/.
(20) Difference between Terminal, Console, Shell, and Command Line. https://www.geeksforgeeks.org/difference-between-terminal-console-shell-and-command-line/.
(21) undefined. http://en.wikipedia.org/wiki/Thompson_shell.
(22) undefined. http://www.multicians.org/shell.html.


Customizing the Environment 
1. What are system variables? Give description of the following: 
HOME, PATH, LOGNAME, PWD, PSI, PS2, SHELL, IFS 
2. What are the utilities of environment variables? 

Certainly! Let's explore system variables and their descriptions, as well as the utilities of environment variables:

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

Remember that changing environment variables can impact system behavior, so always double-check before modifying them. 🚀🔍
Source: Conversation with Copilot, 5/27/2024
(1) How to Edit Environment Variables on Windows 10 or 11. https://www.howtogeek.com/787217/how-to-edit-environment-variables-on-windows-10-or-11/.
(2) Windows Environment Variables – The Ultimate Guide For ... - ITechtics. https://bing.com/search?q=environment+variables+utilities.
(3) Environment Variables - The Open Group. https://pubs.opengroup.org/onlinepubs/009695399/basedefs/xbd_chap08.html.
(4) Environment Variables: What They Are and How To Use Them - Kinsta. https://kinsta.com/knowledgebase/what-is-an-environment-variable/.
(5) EnvironmentVariables - Community Help Wiki. https://help.ubuntu.com/community/EnvironmentVariables.
(6) What Is the Difference Between User Variables and System ... - Baeldung. https://www.baeldung.com/cs/user-vs-system-variables.
(7) What are environment variables in Windows? - Digital Citizen. https://www.digitalcitizen.life/simple-questions-what-are-environment-variables/.
(8) What are System & User Environment Variables in Windows 11/10. https://www.thewindowsclub.com/system-user-environment-variables-windows.

