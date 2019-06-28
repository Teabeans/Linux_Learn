## NAVIGATION + ORIENTATION<br/>
`[tab]`<br/>
Autocomplete - Attempts to autocomplete the line with the likely name of files or directories.

`[Ctrl + L/R Arrows]`<br/>
Jump cursor L/R by word, rather than character

`[Ctrl + A]`<br/>
Jump to start of line, often coupled with `[Ctrl + K]` to clear the line

`[Ctrl + E]`<br/>
Jump to end of line.

`[Ctrl + K]`<br/>
Delete from cursor to end of line. If executed from start of line, clears the line.

`[Ctrl + W]`<br/>
Clear from prior to cursor location to start of current word. If executed from after a word, deletes the word.<br/>
> _e.g._
```
abcdefg hijkLmnop >> [Ctrl+W] >> abcdefg Lmnop
            ^                ^
```

`[Alt + Shift + 3]`<br/>
Does not execute the current command, but enters it as a comment into history.

`[Ctrl + C]`<br/>
Cancel the current line without committing it to history.

`[Ctrl + XX]`<br/>
Generate a second cursor on the line (default at start of line). Toggle between using `[Ctrl + XX]`.

`[Ctrl + L]`<br/>
Clear the prompt without a commit to history.

`$ clear`<br/>
Clear the prompt **with** a commit to history.

`[Ctrl + R]`<br/>
Search the command history (type in the search term). Goes in reverse order and by specificity

`$ man <ARG1>`<br/>
MANual (MAN)- an interface to the on-line reference manuals. Displays usage manual for the command `ARG1`

`$ alias`<br/>
Lists all aliases in the environment

`$ history <ARG1>`<br/>
List the user's command history. `ARG1` optionally lists the latest `ARG1` commands

`$ dpkg --get-selections`<br/>
List all installed packages (programs)

`$ pwd`<br/>
Print Working Directory (PWD) - Prints current directory

## ACCESS + PERMISSIONS<br/>

`$ whoami`<br/>
Prints the effective user ID.

`$ groups`<br/>
Prints the groups the effective user ID is a member of.

`$ hostname`<br/>
Prints the local hostname. Same as content of the file at `/etc/hostname`

`$ passwd`<br/>
Set the password for the current user ID

`$ sudo passwd <ARG1>`<br/>
Set the password for the user `ARG1` (obviously, use caution if `ARG1 == root` and manage this password well)

`$ usermod`<br/>
USER MODification (USERMOD) - Modify a user account. For more details, see `$ man usermod`

`$ chmod <ARG1> <ARG2>`<br/>
CHange MODe (CHMOD) - Changes a file or directory mode (permission) bits. <br/>
> _e.g._ - `chmod u=rwx,g=rx,o=r theFile` <br/>
> The **U**ser may **R**ead, **W**rite, and e**X**ecute <br/>
> The **G**roup may **R**ead and e**X**ecute <br/>
> **O**thers may **R**ead <br/>

> **NOTE:** Permissions may also be set using octal notation, which consists of (3) digits in range 0 to 7. Each digit is a sum of the values 4, 2, 1, and 0, which correspond to permissions as follows:
> * (4) == `READ`
> * (2) == `WRITE`
> * (1) == `EXECUTE`
> * (0) == `NO PERMISSION`
<a/>
> The (3) digits represent (User)(Group)(Other) permissions, with the prior `chmod` example being represented as follows:
> `chmod 754 theFile`
> **NOTE:** Under the hood, these values are encapsulated by 3 bits:
```
 U  G  O
[0][0][0] == 0
[0][0][1] == 1
[0][1][0] == 2
[1][0][0] == 4
[1][1][1] == 7
```


`$ ls -l <ARG1>`<br/>
LiSt (LS) folder directory as a List (-L). `ARG1` defines the file name to match. Displays permission bits.


## MAINTENANCE + UPKEEP<br/>

`$ sudo <ARG1>`<br/>
SUperuser DO (SUDO) - Elevates the user to superuser privileges for the purposes of executing ARG1.

`$ sudo apt-get update`<br/>

`$ sudo apt-get upgrade`<br/>

`$ sudo apt-get intall <ARG1>`<br/>

> _e.g._
> * $ sudo apt-get install emacs
> * $ sudo apt-get install git

`$ <ARG1> | <ARG2> `<br/>
Pipe (`|`) - Connects the output of `ARG1` to the input of `ARG2`

`$ ls`<br/>
LiSt (LS) directory contents - Prints directory contents. Color encodings as follows:
1. Blue - Directory
2. Green - Executable or recognized data file
3. Light Blue - Symbolic Link
4. Yellow on Black - Device
5. Pink - Image File
6. Red - Archive
7. Red on Black - Broken Link

For more information, see `man dir_colors`

`$ cd`<br/>
Change Directory (CD) - Changes the working directory (does nothing without arguments)

`$ cd /<DIR1>/<DIR2>`<br/>
Change directory to `/DIR1/DIR2`

`$ cd ..`<br/>
Changes the directory down one level

`$ cd ../..`<br/>
Changes the directory down two levels

`$ cd ../../<ARG1>`<br/>
Changes the directory down two levels, then up to ARG1

`$ <ARG1> --version`<br/>
Generally, output the installed version of the `ARG1` package.

`$ top`<br/>
Display the process manager.
> **NOTE:** `top` contains multiple command line and interactive options. For more information, see `man top`.

`$ nano <ARG1>`

`$ emacs <ARG1>`

`



## NETWORK<br/>
`$ dnsdomainname`<br/>
Show the system's DNS domain name


## FILES + DIRECTORIES<br/>
`$ touch <ARG1>`<br/>
TODO

`$ rm <ARG1>`<br/>
ReMove (RM) - Remove files or directories
> **NOTE:** Remove does not remove directories. Use the `-r` option to do so.

`$ rm -rf <ARG1>`<br/>
Removes all folders recursively (`-r`) and without prompting (forced `-f`)
> **CAUTION:** Use extreme care when executing a recursive deletion.

`mkdir <ARG1>`<br/>
MaKe DIRectory (MKDIR) - Makes a new directory of name `ARG1` in the current working directory
