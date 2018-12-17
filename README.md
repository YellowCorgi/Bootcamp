# Bootcamp
Linux Bootcamp notes
01. ls command shows directories in our home
>learner@:~$ Unix command prompt
>ls /bin
>>> bin can be replaced with boot, dev, etc, home, lib, lib64, media, mnt,
opt, proc, root, run, sbin, srv, sys, tmp, usr, var
those touch the forward slash and must be individual
or can be back to back: /etc/perl and so on
>>>>> the ls /etc/perl output is CPAN Net
02. Unix tree
root level (/)
ls lets you search directories
03. pwd command will print the working directory where you are
/home/learner where learner is the subdirectory of directory called home
04. new directory and subdirectory
mkdir
learner@:~$ mkdir learning_unix (which is the new name)
learner@:~$ ls
(a_directory another_directory learning_unix) the output lists
05. changing from one directory or subdirectory to another using cd Command
learner@:~$ cd learning_unix
this will then make the search directory the new one
mkdir supports command line options
>>> learner@:~$ mikdir -p outer/inner (spaces around the -p)
this created a folder (outer) with a sub folder (inner)
06. root directory
the placement of the / determines where you go
/home/learner/
This says go to the learner directory that is beneath the home
the home is the top level of the root
home/learner/
this says go to the learner directory that is beneath the home directory that is
located wherever you are at the moment. It is not the HOME directory.


18.12.10

#####Command-Line Bootcamp#####
07. using two dots (..) let you move upwards one level in the directory or to
the parent directory where you currently are. going up two levels (../..)

learner@~$ cd learning_unix/
learner@: learning_unix$ cd ..
learner@:~$ cd ..
learner@:home$
08. absolute and relative path
cd .. lets us change directories relative to where you currently are
>absolute location means you know how to get there and in what order
>>Learner@:learning_unix$ cd ../../../tmp
>relative location means you know less but it is in that current directory
>> learner@:learning_unix$ cd /tmp
09. finding your way back HOME
~ is the signal for the home directory, cd and pwd also work
10. ls command more useful
using .. along with ls lists directories that are above
>learner@:learning_unix$ cd ~/learning_unix/outer/
learner@:outer$ ls ../../
a_direcory another_directory learning_unix

>> adding l gives a longer output
learner@:learning_unix$ ls -l /HOME
total 4
drwxr-xr-x 6 learner learner 4096 Dec 2 08:31 Learner

ls -l
ls -R
ls -l -t -r
ls -lh
11. manual for unix commands using man command
man man is the command for the manuals manual
>> space is to scroll down
>> b to back
>> q to quit
12. removing directories. you must be outside of it to delete it
>>rmdir
learner@:learning_unix$ rmdir outer/inner/
### this removes only inner/ and must be repeated with just outer to delete outer
13. using tab completion
tying less characters and then pressing tab to select what auto completion
14. create Empty files with the touch command
learner@:learning_unix$ touch heaven.txt
learner@:learning_unix$ touch earth.txt
learner@:learning_unix$ ls earth.txt heaven.txt
15. Moving files (mv)
>> mv heaven.txt temp/ (or whatever file folder is)
it can also be done by (mv *.txt temp/) or (mv *t temp/) or (mv *ea* temp/)
* is a wild character which means match anything
####? does something#####
16. renaming files
mv renames the files and also moves the files
>learner@:learning_unix$ touch rags
>learner@:learning_unix$ mv rags temp/riches
>learner@:learning_unix$ mv temp/riches temp/rags


18.12.17
The website was down..it was having difficulty finding the server.
(websocket connection error. open devtools for more information)

17. Moving directories
>learner@:learning_unix$ mkdir temp2
>learner@:learning_unix$ mv temp2 temp
>learner@:Learning_unix$ ls temp/
>>earth.txt heaven.txt rags temp2
Temp2 was a new directory and it was then moved into the temp home directory
This is just like moving files
18. Removing files
rmdir is the remove command while mkdir is the make command
>>>rm command removes everything. rmdir will not remove directories with files
>> adding -i helps check what you are deleting (y completion for yes delete)
>learner@:learning_unix$ cd temp
>learner@:temp$ ls
earth.txt heaven.txt rags temp2
>learner@:temp$ rm -i earth.txt heaven.txt rags
rm: remove regular empty file earth.txt?
>y
rm: remove regular empty file heaven.txt?
>y
rm: removed regular empty file rags?
>y
>learner@:temp$ ls
temp2
>>>>> lesson 15 wild card *
>>>>> rm -i *.txt

>learner@:temp$ rmdir temp2/temp3/
(this removed only temp3)
>learner@:temp$ rmdir temp2/
>learner@:temp$ cd ..
>learner@:learning_unix$ rmdir temp
19.copying files
>>>>cp command
>learner@:learning_unix$ touch file1
>learner@:learing_unix$ cp file1 file2
>learner@"learning_unix$ ls
file1 file2
This copy was from the same directory
>learner@:learning_unix$ touch ~/file3
>learner@:learning_unix$ ls ~
command_line_course file3 learning_unix linux_bootcamp
>learner@:learning_unix$ cp ~/file3 .
>learner@:learning_unix$ ls
file1 file2 file3
>>>>> current directory can be represented by a (.)

clean up this a_directory
>learner@:learning_unix$ rm -i file*
This removed them all at one time instead of individual
20. Copy directories
cp lets you copy directories as well as files
##man cp to see how the -R or -r options let you copy a directory recursively##
21.viewing files with less
>>>>less allows you to view files but not edit them
(like searches)
>>> echo puts some text in a file by redirecting it to a > (file redirection)
( > can over write previous >)

>learner@:learning_unix$ echo "call me ishmael."
call me ishmael.
>Learner@:learning_unix$ echo "call me ishmael." > opening_lines.txt
>learner@:learning_unix$ ls
opening_lines.txt
>learner@:learning_unix$ less opening_lines.txt

## using h takes you through the help command.
## scroll forward a page through space
## go forward or backward through j or k
## q for quit
22. Viewing files with cat
cat command displays the contents of the file/s and then returns you to the
command line. Can also be used to combine multiple files and copy existing files

>learner@:learning_uni$ echo "The primroses were over." >> opening_lines.txt
>learner@:learning_unix$ cat opening_lines.txt
Call me Ishmael.
The primroses were over.
#### using >> instead of > added a line instead of over writing the previous >

>learner@:learning_unix$ cat opening_lines.txt > file_copy.txt
(MAKE A COPY OF EXISTING file)
>learner@:learning_unix$ rm file_copy.txt
and thus removing the copy
23. Counting characters, words and lines in a file. (on atom i have 218:74)
>learner@:learning_unix$ ls
opening_lines.txt
>learner@:learning_unix$ ls -l
total 4
-rw-r--r-- 1 learner learner 0 Dec 2 09:09 opening_lines.txt
>learner@:learning_unix$ wc opeing_lines.txt
2 7 42 opeing_lines.txt
>learner@:learning_unix$ wc -l opeing_lines.txt
2 opening_lines.txt
24. Editing small text files with nano
nano is the system for most unix systems
## emacs and vi are also editing systems
>learner@:learning_unix$ nano opening_lines.txt
"you simply type the text you want to include in the file"
## bottom of the nano window shows commands of control + a letter
control + X is exit

((There is a weird glitch and 25 and 26 seem to be the same thing? ope nope 25
is just labeled 26 and 26 is labeled 26... nice))
25. The $path environment variable
echo command displays the contents of something known (environment variables)
>learner@:learning_unix$ echo $USER
Learner
>learner@:learning_unix$ echo $HOME
/home/Learner
>learner@:learning_unix$ echo $PATH
/home/learner/.nvm/versions/node/v5.1.0/bin:/usr/local/sbin:/usr/local/bin:/usr
/sbin:/usr/bin:/sbin:/bin

#This shows directories that are expected to contain programs that i can run
26. Matching lines in files with grep
#grep searches files to find lines that match a certain pattern
##ignore case when matching (-i)
##only match whole words (-w)
##show lines that don't match a pattern (-v)
## use wildcard characters and other patterns to allow for alternatives (8,.,[])

(use nano to add the following lines. use WriteOut to save)
>learner@:learning_unix$ nano opening_lines.txt
"Now is the winter of our discontent."
"All children, except one, grow up"
"The Galactic Empire was dying."
"In a hole in the ground there lived a hobbit."
"it was a pleasure to burn."
"it was a bright, cold day in april, and the clocks were striking thirteen."
"it was love at first sight."
"i am an invisible man."
"it was the day my grandmother exploded."
"when he was nearly thirteen, my brother jem got his arm badly broken at the elbow."
"marley was dead, to begin with."

>learner@:learning_unix$ grep was opening_lines.txt
The Galactic Empire was dying.
It was a pleasure to burn.
It was a bright, cold day in April, and the clocks were striking thirteen.
It was love at first sight.
It was the day my grandmother exploded.
When he was nearly thirteen, my brother Jem got his arm badly broken at the elbow.
Marley was dead, to begin with.

>learner@:learning_unix$ grep -v was opening_lines.txt
Call me Ishmael.
The primroses were over.
Now is the winter of our discontent.
All children, except one, grow up.
In a hole in the ground there lived a hobbit.
I am an invisible man.

>learner@:learning_unix$ grep all opening_lines.txt
Call me Ishmael.

>learner@:learning_unix$ grep -i all opening_lines.txt
Call me Ishmael.
All children, except one, grow up.

>learner@:learning_unix$ grep in opening_lines.txt
Now is the winter of our discontent.
The Galactic Empire was dying.
In a hole in the ground there lived a hobbit.
It was a bright, cold day in April, and the clocks were striking thirteen.
I am an invisible man.
Marley was dead, to begin with.

>learner@:learning_unix$ grep -w in opening_lines.txt
In a hole in the ground there lived a hobbit.
It was a bright, cold day in April, and the clocks were striking thirteen.

learner@:learning_unix$ grep -w o.. opening_lines.txt
Now is the winter of our discontent.
All children, except one, grow up.

>learner@:learning_unix$ grep [aeiou]t opening_lines.txt
In a hole in the ground there lived a hobbit.
It was love at first sight.
It was the day my grandmother exploded.
When he was nearly thirteen, my brother Jem got his arm badly broken at the elbow.
Marley was dead, to begin with.

>learner@:learning_unix$ grep -w -i [aeiou]t opening_lines.txt
It was a pleasure to burn.
It was a bright, cold day in April, and the clocks were striking thirteen.
It was love at first sight.
It was the day my grandmother exploded.
When he was nearly thirteen, my brother Jem got his arm badly broken at the elbow.

27. working with columns
##csv and tsv files
##Curl will download any URL and print it to STDOUT
>download a test file
cd curl https://raw.githubusercontent/com/Blahah/command_line_bootcamp/master
/testfiles/grades.txt > grades.txt
less testfile.vcf

extract information
>cut -f 5 grade.txt
This provided us with all the rows for column 5

remove from file
>cut -f -2,4-7,9 grades.txt > grades_no_cheaters.txt
This moved the cheaters to the new text
- means up to that value and those values inbetween

add the removed to the end of the file
>cut -f 3,8 grades.txt | paste grade_no_cheaters.txt - > sorted_grades.txt

28. Combining unix with pipes... pipe is the | symbol... which is literally a pipe
you can send the output from one command or program to another command
as long as it can accept it.
>learner@:learning_unix$ grep was opening_lines.txt | wc -c
316
### searched the specified files for 'was' and piped them to word count
>learner@:learning_unix$ grep was opening_lines.txt | sort | head -n 3 | wc -c
130
##the output was sent to sort (alphanumerically). sort was sent to head (first 10
lines of a file). -n showed us only 3 lines of that 10. these 3 lines were then
sent to word count.

#### test each step of the pipe as it is built###

29. Miscellaneous Unix power commands
  1. View penultimate 10 lines of a file with head and tail commands
>tail -n 20 file.txt | head
  2. Show lines of a file that begin with a start codon (^ matches start line patterns)
>grep "^ATG" file.txt
  3. cut out the 3rd column of a tab-delimited text file
  also sort it to only unique lines (remove duplicates)
>cut -f 3 file.txt | sort -u
  4. count how many lines in a file contain the words cat or bat
>grep -c '[bc]at' file.txt
  5. turn lower case text to upper case
>tr 'a-z' 'A-Z' < file.txt
  6. Change all occurrences of 'Chr1' to 'Chromosome 1' and output to new file
> sed 's/Chr1/Chromosome 1/g' file.txt > file2.txt
