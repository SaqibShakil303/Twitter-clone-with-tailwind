### Experiment No. – 01 
Introduction to the UNIX system: log in, log out, basic commands 
1. Use putty to log in to your UNIX account. 
2. Create a file named lab1 by using the script utility. 
3. Show the ID number of the terminal that you are using. 
4. Show your user ID (only your user id, nothing else should show up) 
5. Show all users who are currently logged in, use the utility that displays the user’s 
name 
6. Exit from the script utility. 
7. Start the script utility again, make sure to append to the same file lab1 so you don’t 
lose your previous work. 
8. Use one command to show the calendar for the previous month, current month, and 
next month. 
To do this step, you will first need to look up the man page of the utility in order to 
find the right option. Don’t show the man page in the script output file (look up the 
man page before starting script). 
9. Start the calculator and show the result of the division problem: 1 / 3, show the result 
with 2 digits after the decimal point. 
10. Show the current date and time. 
11. End the script session.

Certainly! Let's address each of the tasks:

1. **Logging In Using PuTTY**:
   - To log in to your UNIX account using PuTTY:
     - Download and install PuTTY from the [PuTTY Download Page](https://www.putty.org/).
     - Launch PuTTY.
     - Enter the hostname or IP address of your UNIX server.
     - Select the SSH protocol.
     - Click the "Open" button to connect.
     - Enter your username and password when prompted.

2. **Creating a File Named "lab1" Using the Script Utility**:
   - You can create a file named "lab1" using the following command:
     ```bash
     touch lab1
     ```

3. **Showing the Terminal ID Number**:
   - To display the terminal ID number (TTY), use the following command:
     ```bash
     tty
     ```

4. **Showing Your User ID (UID)**:
   - To display your user ID (UID), use the following command:
     ```bash
     id -u
     ```

5. **Showing All Users Currently Logged In**:
   - To display all users currently logged in, use the following command:
     ```bash
     who
     ```

6. **Exiting from the Script Utility**:
   - To exit from the script utility, simply close the terminal or type `exit`.

7. **Starting the Script Utility Again and Appending to the Same File "lab1"**:
   - To start the script utility again and append to the same file "lab1":
     - Use the same commands as before to create and edit the file.

8. **Showing the Calendar for Previous, Current, and Next Month**:
   - To display the calendar, use the following command:
     ```bash
     cal
     ```

9. **Starting the Calculator and Showing the Result of 1 / 3**:
   - To calculate 1 / 3 with 2 digits after the decimal point:
     ```bash
     echo "scale=2; 1 / 3" | bc
     ```

10. **Showing the Current Date and Time**:
    - To display the current date and time:
      ```bash
      date
      ```

11. **Ending the Script Session**:
    - Simply close the terminal or type `exit`.


### Experiment No. – 02 
This lab covers basic file utilities and filename expansion. 
1. Use the script utility to capture the screen output and save into a file with your choice 
of filename 
2. Use one command to create 3 empty files called test3.2, slide12, and cis2. 
3. Use wildcards to list all filenames that have the letter s in the name 
4. Use wildcards to list all filenames that have the letter s as the third character in the 
name 
5. Use wildcards to list all filenames that have the number 1 or 3 in the name 
6. Use wildcards to list all filenames that have at least 2 digits, and the digits don’t have 
to be next to each other. (A digit is a numeric value between 0 and 9) 
7. Copy file lab1-2 (the last lab assignment) to test3.2, use the interactive option and 
answer yes when prompted 
8. Use an option of the ls command to see the size in bytes of file test3.2 
9. Rename test3.2 to temp2 
10. Run a command to prove that test3.2 doesn’t exists 
11. List all files that you worked with in this lab. Use wildcards to make your command as 
short as possible (use the fact that the files all have some common character in their 
names) 
12. Use one command to delete all 3 files that you created in this lab. 
13. Exit script. Save the script output.

Certainly! Let's tackle each task step by step:

1. **Capturing Screen Output Using the `script` Utility**:
   - The `script` utility allows you to capture terminal session output.
   - To start recording, run:
     ```bash
     script my_session_output.txt
     ```
   - Perform your tasks, and when done, type `exit` to stop recording.
   - The output will be saved in the file `my_session_output.txt`.

2. **Creating Empty Files**:
   - To create the three empty files, run:
     ```bash
     touch test3.2 slide12 cis2
     ```

3. **Listing Filenames with the Letter 's'**:
   - To list filenames containing the letter 's', use:
     ```bash
     ls *s*
     ```

4. **Listing Filenames with 's' as the Third Character**:
   - To list filenames where 's' is the third character, use:
     ```bash
     ls ??s*
     ```

5. **Listing Filenames with 1 or 3**:
   - To list filenames containing either '1' or '3', use:
     ```bash
     ls *[13]*
     ```

6. **Listing Filenames with at Least 2 Digits**:
   - To list filenames with at least two digits (numeric values), use:
     ```bash
     ls *[0-9]*[0-9]*
     ```

7. **Copying `lab1-2` to `test3.2` Interactively**:
   - To copy `lab1-2` to `test3.2` interactively, run:
     ```bash
     cp -i lab1-2 test3.2
     ```

8. **Checking File Size of `test3.2` in Bytes**:
   - To see the size of `test3.2` in bytes, use:
     ```bash
     ls -l --block-size=1 test3.2
     ```

9. **Renaming `test3.2` to `temp2`**:
   - To rename `test3.2`, run:
     ```bash
     mv test3.2 temp2
     ```

10. **Proving Non-Existence of `test3.2`**:
    - To verify that `test3.2` doesn't exist, use:
      ```bash
      ls test3.2
      ```

11. **Listing All Files with Common Character**:
    - To list all files worked on (assuming a common character), use:
      ```bash
      ls *common_character*
      ```

12. **Deleting All 3 Created Files**:
    - To delete the three files, run:
      ```bash
      rm test3.2 slide12 cis2
      ```

13. **Exiting the Script Session**:
    - Type `exit` to exit the `script` session.

Feel free to ask if you need further assistance! 🚀🔍

Source: Conversation with Copilot, 5/27/2024
(1) logging - Save Screen (program) output to a file - Stack Overflow. https://stackoverflow.com/questions/14208001/save-screen-program-output-to-a-file.
(2) Capture all the output of a script to a file (from the script itself). https://unix.stackexchange.com/questions/424652/capture-all-the-output-of-a-script-to-a-file-from-the-script-itself.
(3) unix - How to capture shell script output - Stack Overflow. https://stackoverflow.com/questions/48809076/how-to-capture-shell-script-output.
(4) Terminal Commands to Take a Screenshot | Baeldung on Linux. https://www.baeldung.com/linux/command-line-screenshot.
(5) How to Create an Empty File in Linux | Touch Command. https://www.geeksforgeeks.org/touch-command-in-linux-with-examples/.
(6) File Management in Unix / Linux | Lecture #2 | Unix Shell Scripting Tutorial. https://www.youtube.com/watch?v=eimpjkuovZk.
(7) 5 Tips to Create an Empty File in Linux / Unix | Linux Commands. https://www.youtube.com/watch?v=aGLY5zQFii8.
(8) How to create multiple empty files using command prompt in Windows. https://stackoverflow.com/questions/60677379/how-to-create-multiple-empty-files-using-command-prompt-in-windows.
(9) linux - Unix Shell create multiple directories and random files(empty .... https://stackoverflow.com/questions/27112613/unix-shell-create-multiple-directories-and-random-filesempty-inside.
(10) linux - Portable way to get file size (in bytes) in the shell - Stack .... https://stackoverflow.com/questions/1815329/portable-way-to-get-file-size-in-bytes-in-the-shell.
(11) How to check the file size in Linux/Unix bash shell scripting. https://www.cyberciti.biz/faq/howto-bash-check-file-size-in-linux-unix-scripting/.
(12) Unix command to check the filesize - Stack Overflow. https://stackoverflow.com/questions/25845057/unix-command-to-check-the-filesize.
(13) How to Get the Size of a File or Directory in Linux. https://www.howtogeek.com/450366/how-to-get-the-size-of-a-file-or-directory-in-linux/.
(14) How to Display File Size in MB, KB or GB in Ubuntu Linux - Linux Handbook. https://linuxhandbook.com/show-file-size-linux/.
(15) 10 Practical Examples Using Wildcards to Match Filenames in Linux - Tecmint. https://www.tecmint.com/use-wildcards-to-match-filenames-in-linux/.
(16) A Quick Introduction to Unix/Wildcards - Wikibooks. https://en.wikibooks.org/wiki/A_Quick_Introduction_to_Unix/Wildcards.
(17) Wildcards in Linux explained with 10 examples | FOSS Linux. https://www.fosslinux.com/44230/wildcards-in-linux-examples.htm.
(18) bash - Listing filenames with wildcards and spaces - Unix & Linux Stack .... https://unix.stackexchange.com/questions/693071/listing-filenames-with-wildcards-and-spaces.
(19) Cp Command in Linux (Copy Files) | Linuxize. https://linuxize.com/post/cp-command-in-linux/.
(20) cp command in Linux with examples - Linux command line tutorial. https://bing.com/search?q=UNIX+command+to+copy+file+with+interactive+option.
(21) cp command in Linux with examples - Linux command line tutorial. https://linuxconfig.org/cp.
(22) How to Copy Files and Directories in Linux | cp Command. https://www.geeksforgeeks.org/cp-command-linux-examples/.
(23) how to copy directory in Linux with Examples - Techgoeasy. https://techgoeasy.com/copy-directory-linux/.


### Experiment No. – 05 
This lab covers shell scripts. 
1. Write a shell script that will add two numbers which are supplied as command line 
argument. Also check for sufficient number of command line arguments. 
2. Write a shell script to find out largest number from given three numbers. Numbers are 
supplied as command line argument. Print error if sufficient arguments are not 
supplied. 
3. Write a shell script to print numbers as 5, 4, 3, 2, 1 using while loop. 
4. Write a shell script using case statement to perform basic mathematical operations as 
follows: 
i. Addition
ii. Subtraction 
iii. Multiplication 
iv. division 
 
5. Write a shell script to display current date, time, username, and current directory. 
6. Write a shell script to print given number in reverse order. (If the number is 123 it 
must print as 321.) 
7. Write a shell script to print the sum of all digits of a given number. (If the number is 
123 its sum of all digits will be 1+2+3 = 6.) 
8.  Write a shell script to calculate 5.12 + 2.5 (real number calculation) at $ prompt in 
Shell. 
9. Write a shell script to perform real number calculation and store the result to in a third 
variable. 
10. Write a shell script to determine whether a given file exists or not. The file name is 
supplied as command line argument. Also check for sufficient number of command 
line arguments.

Certainly! Let's address each of the tasks:

1. **Adding Two Numbers from Command Line Arguments**:
   - To add two numbers supplied as command line arguments, create a shell script (e.g., `add_numbers.sh`) with the following content:
     ```bash
     #!/bin/bash
     if [ $# -ne 2 ]; then
         echo "Error: Insufficient arguments. Usage: $0 <num1> <num2>"
         exit 1
     fi

     num1=$1
     num2=$2
     sum=$((num1 + num2))
     echo "Sum: $sum"
     ```

2. **Finding the Largest Number from Three Command Line Arguments**:
   - To find the largest number from three command line arguments, create a shell script (e.g., `largest_number.sh`) with the following content:
     ```bash
     #!/bin/bash
     if [ $# -ne 3 ]; then
         echo "Error: Insufficient arguments. Usage: $0 <num1> <num2> <num3>"
         exit 1
     fi

     largest=$1
     for num in "$@"; do
         if [ "$num" -gt "$largest" ]; then
             largest="$num"
         fi
     done

     echo "Largest number: $largest"
     ```

3. **Printing Numbers in Reverse Order Using a While Loop**:
   - To print numbers from 5 to 1 in reverse order, create a shell script (e.g., `reverse_numbers.sh`) with the following content:
     ```bash
     #!/bin/bash
     num=5
     while [ "$num" -ge 1 ]; do
         echo "$num"
         num=$((num - 1))
     done
     ```

4. **Performing Basic Mathematical Operations Using a Case Statement**:
   - Create a shell script (e.g., `math_operations.sh`) with the following content:
     ```bash
     #!/bin/bash
     echo "Enter operation (+, -, *, /):"
     read operation

     case "$operation" in
         +) echo "Addition: $(($1 + $2))" ;;
         -) echo "Subtraction: $(($1 - $2))" ;;
         \*) echo "Multiplication: $(($1 * $2))" ;;
         /) echo "Division: $(($1 / $2))" ;;
         *) echo "Invalid operation" ;;
     esac
     ```

5. **Displaying Current Date, Time, Username, and Current Directory**:
   - To display this information, create a shell script (e.g., `system_info.sh`) with the following content:
     ```bash
     #!/bin/bash
     echo "Current date: $(date)"
     echo "Username: $USER"
     echo "Current directory: $PWD"
     ```

6. **Printing a Given Number in Reverse Order**:
   - To reverse a given number (e.g., 123), create a shell script (e.g., `reverse_number.sh`) with the following content:
     ```bash
     #!/bin/bash
     echo "Enter a number:"
     read num

     reversed=""
     while [ "$num" -gt 0 ]; do
         digit=$((num % 10))
         reversed="${reversed}${digit}"
         num=$((num / 10))
     done

     echo "Reversed number: $reversed"
     ```

7. **Printing the Sum of Digits of a Given Number**:
   - To calculate the sum of digits of a number (e.g., 123), create a shell script (e.g., `sum_of_digits.sh`) with the following content:
     ```bash
     #!/bin/bash
     echo "Enter a number:"
     read num

     sum=0
     while [ "$num" -gt 0 ]; do
         digit=$((num % 10))
         sum=$((sum + digit))
         num=$((num / 10))
     done

     echo "Sum of digits: $sum"
     ```

8. **Calculating Real Number Addition at the `$` Prompt**:
   - Simply type the following at the `$` prompt:
     ```
     echo "5.12 + 2.5" | bc
     ```

9. **Performing Real Number Calculation and Storing the Result in a Third Variable**:
   - To perform real number calculation and store the result, create a shell script (e.g., `real_calculation.sh`) with the following content:
     ```bash
     #!/bin/bash
     num1=5.12
     num2=2.5
     result=$(echo "$num1 + $num2" | bc)
     echo "Result: $result"
     ```

10. **Checking File Existence from Command Line Argument**
create a shell script that checks whether a given file exists or not. We’ll also ensure that the correct number of command line arguments is provided.

#!/bin/bash

# Check if the correct number of arguments is provided
if [ $# -ne 1 ]; then
    echo "Error: Insufficient arguments. Usage: $0 <filename>"
    exit 1
fi

filename="$1"

# Check if the file exists
if [ -e "$filename" ]; then
    echo "$filename exists."
else
    echo "$filename does not exist."
fi

Save the above script to a file (e.g., check_file.sh), make it executable (chmod +x check_file.sh), and then run it with the desired filename as an argument. It will display whether the file exists or not. If no argument is provided, it will show an error message.