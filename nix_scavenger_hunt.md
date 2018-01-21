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

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 

/Users/carlostorres/Documents/Seattle U/WATS3030/wats1030-intro-to-unix

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

LICENSE                         challenge_files                 nix_scavenger_hunt_stretch.md
README.md                       nix_scavenger_hunt.md           super_scavengers.md 

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

total 48
drwxr-xr-x    9 carlostorres  staff   288B Jan 20 21:13 .
drwxr-xr-x    4 carlostorres  staff   128B Jan 20 21:16 ..
drwxr-xr-x   13 carlostorres  staff   416B Jan 20 21:19 .git
-rw-r--r--    1 carlostorres  staff   1.1K Jan 20 21:13 LICENSE
-rw-r--r--    1 carlostorres  staff   2.7K Jan 20 21:13 README.md
drwxr-xr-x  111 carlostorres  staff   3.5K Jan 20 21:13 challenge_files
-rw-r--r--    1 carlostorres  staff   5.4K Jan 20 21:13 nix_scavenger_hunt.md
-rw-r--r--    1 carlostorres  staff   317B Jan 20 21:13 nix_scavenger_hunt_stretch.md
-rw-r--r--    1 carlostorres  staff   191B Jan 20 21:13 super_scavengers.md

There are a lot more details about the files in the directory when using this command such as the time it was added, user and the size of the files. 

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

The man command allows you to get a manual page. ls is a list directory of contents, 'a' means to not ignore entries starting with. 'l' is used to use a long format and 'h' is t make it into a readable format. 

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

Applications                    etc
Library                         home
Network                         installer.failurerequests
System                          net
Users                           private
Volumes                         sbin
bin                             tmp
cores                           usr
dev                             var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

/

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

/Users/carlostorres

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

3

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?*

the up arrow copies the previous command that was used

* Press the up arrow a few more times. *What do you see?*

it changes to the different commands that have been used in the current terminal. 

* Run the `history` command. *What do you see?*

This command displays all the command that I have typed to accomplish this exercise in the precise order that they were used. 

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

carlostorres

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

No

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

0:44  up  8:28, 1 user, load averages: 2.00 2.05 1.95

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

ps is used to report a snapshot of the current processes. I see all the times and files that I have accessed. 

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

This command shows us a realtime view of what is running in ur system. 

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*

2

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

it is located under the tmp file

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

2 Files

Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241


* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
I see a list of all the files for this assignement. 

LICENSE
README.md
challenge_files
files.txt
nix_scavenger_hunt.md
nix_scavenger_hunt_stretch.md
super_scavengers.md


* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

The ls-alh | more command lets you scroll up and down with the keyboard so that you can view the files easier. All the files dont come up at oncee you have to scroll down to see the rest of the files. 

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

root       556  0.0  0.6  63876  3456 ?        Ss   07:54   0:00 sshd: cabox [priv]
cabox      558  0.0  0.2  63876  1468 ?        S    07:54   0:00 sshd: cabox@pts/0
cabox      559  0.0  0.3  18124  2020 pts/0    Ss   07:54   0:00 -bash
cabox      569  0.0  0.2  15520  1144 pts/0    R+   07:57   0:00 ps aux
cabox      570  0.0  0.0   8700   316 pts/0    R+   07:57   0:00 grep --color=auto cabox

