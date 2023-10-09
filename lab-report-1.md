### Lab Report 1

---
**1. Using "cd" command in the terminal**

*with no arguments.*
![Image](CD_no_arguments.png)

- The working directory was /home when "cd" was ran.
- The output remained the same and did not change the working directory. This occurred possibly because "cd"
is used to switch the current working directory to the given path directory, provided as an augment. Since 
no augment was provided, the current working directory was not changed, therefore the output 
remained the same.
- Output was not an error

*with a path to a directory as an argument.*
![Image](CD_with_directory_argument.png)

- The working directory was /home when "cd" was ran.
- The output changed as the working directory was now changed to the argument entered after the command "cd"
  in the terminal. Since "cd" now had a proper argument of a directory, the working directory was changed to
  the directory that was entered, /home/lecture1/messages, as "cd" changes the current working directory to the
  path directory entered as an argument after "cd".
- Output was not an error

*with a path to a file as an argument.* 
![Image](CD_with_file_argument.png)
- The working directory was /home when "cd" was ran.
- The output displayed an error message, because the command "cd" is only used to switch the current working
  directory to the path directory entered as an arguement.
- This is an error, because "cd" does not take files as a directory and only works if a directory path was provided
  as an arguement.

---
**2. Using "ls" command in the terminal**

*with no arguments.*
![Image](LS_with_no_arguments.png)

- The working directory was /home when "ls" was ran.
- Entering "ls" into the terminal outputs the list of files and folders from the current working directory. By entering
"ls" into the terminal, the terminal outputted the folder lecture1, because the current working directory was /home, and
the following folder or file inside /home was lecture1.
- Output was not an error

*with a path to a directory as an argument.*
![Image](LS_with_directory_argument.png)

- The working directory was /home when "ls" was ran.
- By entering "ls" into the terminal with a directory as an arguement, the terminal displayed the files that were inside the
folder. The argument was /home/lecture1/messages which displayed en-us.txt es-mx.txt ko.txt zh-cn.txt, which were all the
files in the folder messages.
- THe output was not an error

*with a path to a file as an argument.* \
![Image](LS_with_file_argument.png)

- The working directory was /home when "ls" was ran.
- "ls"

