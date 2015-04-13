# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *
/home/cabox/workspace  
* Discover more about this filesystem. 
Use `ls` (the "list" command)to see what is in this directory. 

LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. 
The results are listed alphabetically and vertically, include dates of fork (presumably) and size of files. 

* The `man` ("manual") command tells you more about how any given command works. Run `man` to see instructions about how to use `man`. 
Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. 
This worked in Terminal but not CA. 
ls a:  -a      Include directory entries whose names begin with a dot (.).
ls l: (The lowercase letter ``ell''.)  List in long format.  (See
             below.)  If the output is to a terminal, a total sum for all the
             file sizes is output on a line before the long listing.
ls h:   When used with the -l option, use unit suffixes: Byte, Kilobyte,
             Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the
             number of digits to three or less using base 2 for sizes.
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. 

bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var  

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/                                                                                                                                           

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/home/cabox  
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
2015_special_stuff.demo
cloaked-wookie.demo
scooter-double-mamba.demo   

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
cabox@box-codeanywhere:~/workspace$  

* Press the up arrow on your keyboard. *What just happened?*
cd ..

* Press the up arrow a few more times. *What do you see?*
Previous commands I typed in

* Run the `history` command. *What do you see?*
A history of all the commands I've inputted

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
Just me: cabox    pts/0        Apr  6 12:47 (54.69.152.243) 

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
14:05:43 up  1:18,  1 user,  load average: 0.00, 0.00, 0.00  

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
This seems to show what processes are running. The processes with 'aux' don't look like anything I've done, so it might be for a different user. 

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
WHoa. This shows me how long I've been working on this assignment, which processes are running (or sleeping), how many users are on this project, and the CPU and memory usage for my different  commands. 

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
cloaked-wookie.demo  credit_cards.txt  credit_cards2.txt 

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
two: 
Britt-Erdman.user:O'Harachester, WA 37261                                                                                                   
Lissie-Strosin.user:Jewessfurt, WA 00816-7241    

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
./serial-numbers/eaque_molestiae.txt:
Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt su
nt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia. 

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
A list of the files in this directory 

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
The number of files only takes up my screen. I have to choose "more" for more files to load into my display.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
-bash: syntax error near unexpected token `newline'   
