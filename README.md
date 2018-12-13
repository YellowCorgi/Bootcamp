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
