`cd`
---
![Image](cd1_no_argument.jpg) <br>
The absolute path to my working directory beforehand is `/Users/dpoedyasmara/Desktop/CSE 15L/lecture1` <br>
The output changes my working directory to my home directory which is /Users/dpoedyasmara. This is because there is no argument which specifies what directory I want to change my working directory to, so it defaults to change to my home directory.
This output is not an error.<br>
![Image](cd1_directory_argument.jpg) <br>
The absolute path to my working directory beforehand is `/Users/dpoedyasmara/Desktop/CSE 15L/lecture1` <br>
The output of this command changes my working directory to the directory 'messages' within my current working directory. This is because the arugment I provided was a relative path to the 'messages' directory so this was where my working directory was changed to.
This output is not an error <br>
![Image](cd1_file_argument.jpg) <br>
The absolute path to my working directory beforehand is `/Users/dpoedyasmara/Desktop/CSE 15L/lecture1/messages` <br>
The output of this command is `cd: not a directory: en-us.txt`. This is because the argument I provided was a relative path to a text file instead of a directory. This caused an error to output because the command `cd` (change directory) requires a directory argument in order to work. 

`ls`
---
![Image](ls_no_argument.jpg) <br>
![Image](ls_directory_argument.jpg) <br>
![Image](ls_file_argument.jpg) <br>

`cat`
---
![Image](cat_no_argument.jpg) <br>
![Image](cat_directory_argument.jpg) <br>
![Image](cat_file_argument.jpg) <br>
