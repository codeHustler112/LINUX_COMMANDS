# Linux_Commands
linux's most used commands for quick references

## **LINUX_BASICS**

Absolute Basics - Bash key Features:

| Key or key combination     | Function                                                                                                         |
|---------------------------|---------------------------------------------------------------------------------------------------                |
| Ctrl+A                    | Move cursor to the beginning of the command line.                                                                 |
| Ctrl+C                    | End a running program and return the prompt.                                                                      |
| Ctrl+D                    | Log out of the current shell session, equal to typing exit or logout.                                             |
| Ctrl+E                    | Move cursor to the end of the command line.                                                                       |
| Ctrl+H                    | Generate backspace character.                                                                                     |
| Ctrl+L                    | Clear this terminal.                                                                                              |
| Ctrl+R                    | Search command history.                                                                                                           |
| Ctrl+Z                    | Suspend a program.                                                                                                                |
| ArrowLeft and ArrowRight   | Move the cursor one place to the left or right on the command line, allowing insertion of characters at other positions.                                                                                                                                                      |
| ArrowUp and ArrowDown     | Browse command history. Go to the line that you want to repeat, edit details if necessary, and press Enter to save time.                                                                                                                                                          |
| Shift+PageUp and Shift+PageDown | Browse terminal buffer (to see text that has "scrolled off" the screen).                                                   |
| Tab                       | Command or filename completion; when multiple choices are possible, the system will provide options.                             |
| Tab Tab                   | Shows file or command completion possibilities.                                                                                  |



# Commands

## man
The `man` command is short for "manual." It is used to display the manual pages for various commands, providing detailed information about their usage, options, and examples. The manual pages serve as a valuable resource for understanding and utilizing different commands effectively.

## info
The `info` command is used to access Info pages, which are an alternative form of documentation commonly found in GNU software. Info pages provide detailed information, similar to manual pages, but often offer more extensive and hierarchical content. They allow for navigating through different sections and subtopics to explore a command or topic in-depth.

## whatis
The `whatis` command is used to search the "whatis" database, which contains brief descriptions of various commands, files, or other entities on the system. It provides a concise summary of the queried item, allowing users to quickly identify its purpose or functionality.

## apropos
The `apropos` command is used to search the "whatis" database for strings or keywords related to specific topics or commands. It helps users find relevant commands, files, or other entities based on their descriptions or functionalities. This command is particularly useful when trying to discover new tools or when unsure about the exact command name.


Here are proper examples of using the commands `man`, `info`, `whatis`, and `apropos`:

- To view the manual page for the `ls` command, use: `man ls`
- To access the Info page for the topic "gcc" (GNU Compiler Collection), use: `info gcc`
- To search the "whatis" database for the term "grep" (search tool), use: `whatis grep`
- To search for commands or entities related to the topic "network," use: `apropos network`

These examples demonstrate how to use each command with the appropriate arguments to access the desired information. Remember to replace `command-name` and `search-term` with the actual command or term you want to explore or search for.

NOTE: Some commands don't have separate documentation because they are part of another command. `cd`, `exit`, `logout`, and `pwd` are such exceptions.

## **FILE AND FILE-SYSTEMS ON LINUX**

**On a UNIX system, everything is a file; if something is not a file, it is a process.**
In simple terms, this means that in a UNIX system, everything is treated as a file. Although there are special files like named pipes and sockets that are more than just regular files, it's easier to think of everything as a file. This includes directories, programs, services, texts, images, and even devices like input and output devices. The system considers them all as files, making it simpler to work with and manage them.

Here's the information formatted in a table with descriptions:


| Symbol | Meaning        | Description                                                                                                                         |
| ------ | -------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| -      | Regular file   | Most files are regular files that contain normal data, such as text files, executable files or programs, and input/output data.    |
| d      | Directory      | Directories are special files that serve as containers for organizing and storing other files and directories.                       |
| l      | Link           | Links create connections between different locations in the file system, allowing a file or directory to be visible in multiple places. |
| c      | Special file   | Special files are used for input and output mechanisms, often located in the `/dev` directory.                                      |
| s      | Socket         | Sockets are special files that provide inter-process networking, similar to TCP/IP sockets, protected by file system access control.  |
| p      | Named pipe     | Named pipes act as a way for processes to communicate with each other without using network socket semantics.                         |
| b      | Block device   | Block devices represent physical or virtual devices that transfer data in fixed-size blocks, such as hard drives or SSDs.             |

The `-l` option to` ls` displays the file type, using the first character of each input line:

The file system tree in a UNIX-based system starts at the root directory, represented by a forward slash (/). This directory is the top-level directory that contains all other directories and files. It is commonly referred to as the root directory.

Directories located directly below the root directory are often prefixed with a slash `(/)` to indicate their position and avoid confusion with directories that may have the same name. It is recommended to explore the root directory when starting with a new system to get an overview of its contents.

Here is an overview of some important directories you may encounter:

**Directory	Content**

| Directory    | Description                                                                                   |
|--------------|-----------------------------------------------------------------------------------------------|
| /bin         | Common programs shared by the system, system administrators, and users.                       |
| /boot        | Startup files and the kernel (e.g., vmlinuz) for booting the system.                           |
| /dev         | Contains references to CPU peripheral hardware represented as special files.                   |
| /etc         | Stores important system configuration files, similar to the Control Panel in Windows.         |
| /home        | Home directories of common users.                                                             |
| /initrd      | (On some distributions) Information required for booting.                                      |
| /lib         | Library files required by the system and users' programs.                                      |
| /lost+found  | Every partition has a lost+found directory for recovering files saved during failures.         |
| /misc        | Used for miscellaneous purposes.                                                              |
| /mnt         | Standard mount point for external file systems, such as CD-ROMs or digital cameras.            |
| /net         | Standard mount point for remote file systems.                                                  |
| /opt         | Typically contains additional and third-party software.                                        |
| /proc        | A virtual file system providing information about system resources.                            |
| /root        | The home directory for the administrative user (root).                                         |
| /sbin        | Programs for system use and system administration tasks.                                       |
| /tmp         | Temporary space for the system, cleaned upon reboot. Avoid saving important work here.         |
| /usr         | Programs, libraries, and documentation for user-related programs.                              |
| /var         | Storage for variable and temporary files created by users, log files, mail queue, etc.         |

Please note that this table provides a brief description of each directory, and there may be additional subdirectories and files within each directory.

To find out the partition on which a directory is located, you can use the df command with a dot (.) as an option. It displays the partition information for the current directory, including the used and available space.

Example:
$ df -h .
Filesystem            Size  Used Avail Use% Mounted on
/dev/hda7             980M  163M  767M  18% /
`By running this command, you can determine the partition and the amount of space utilized on that partition.`

In a file system, each file is represented by an inode, which acts as a unique identifier containing essential information about the file. This information includes details about the file's ownership, as well as its physical location on the hard disk.

Every partition in the system has its own set of `inodes`, allowing files with the same inode number to exist across different partitions.

Each inode corresponds to a data structure on the hard disk, storing various properties of a file, including the actual location of the file's data. During the initialization of a hard disk for data storage, such as during system installation or when adding additional disks, a specific number of inodes per partition is created. This number determines the maximum number of files, including directories, special files, and links, that can coexist on that partition at any given time. Typically, it is expected to have approximately 1 inode for every 2 to 8 kilobytes of storage. It is important to note that the inode does not contain the file name or directory information, as these are stored in separate directory files. By correlating file names with inode numbers, the system can construct a tree-like structure that users can comprehend. If desired, users can display inode numbers using the `-i` option with the `ls `command. The inodes have their dedicated space on the disk, separate from the actual file data.

## **The Path**
When executing commands in the system, it is usually unnecessary to provide the full path to the command. For example, even though we know that the ls command is located in the /bin directory (verified with which -a ls), we don't need to enter the command /bin/ls to list the contents of the current directory.

This convenience is made possible by the PATH environment variable. The PATH variable contains a list of directories where executable files can be found, eliminating the need for users to type out or remember specific command locations. The PATH variable typically includes directories with "bin" in their names. You can use the echo command to display the contents of the PATH variable:

rogier:> **echo $PATH
        /opt/local/bin:/usr/X11R6/bin:/usr/bin:/usr/sbin/:/bin**

## Absolute and Relative Paths
Paths in a file system can be categorized as either absolute paths or relative paths. Understanding the difference between these two types of paths is crucial for navigating and accessing files and directories effectively.

**Absolute Paths:**

An absolute path refers to the complete and exact location of a file or directory within the file system hierarchy. It starts from the root directory, denoted by a forward slash ("/"), and includes all the intermediate directories necessary to reach the desired file or directory.

For example:

`/home/user/Documents/file.txt`: This is an absolute path that specifies the exact location of the file "file.txt" within the "Documents" directory of the "user" directory in the "home" directory.

`/var/log/syslog`: This absolute path points to the "syslog" file located in the "log" directory of the "var" directory.

Absolute paths provide an unambiguous and fixed reference to a file or directory regardless of the current working directory. They always start with a forward slash and can be used to access files and directories from anywhere in the file system.

**Relative Paths:**

A relative path specifies the location of a file or directory relative to the current working directory. It does not begin with a forward slash and relies on the current context to determine the complete path.

Relative paths are typically shorter and more concise than absolute paths. They are commonly used when referring to files and directories within the same directory or in related directories.

For example:

Suppose the current working directory is `/home/user/`, and there is a file named "data.txt" located in the same directory. The relative path to access this file would be data.txt. This path assumes that the file is in the current working directory.

If there is a subdirectory named "images" within the current working directory, and a file named "pic.jpg" resides inside that subdirectory, the relative path to access the file would be `images/pic.jpg`. This path indicates the location of the file relative to the current working directory.

Relative paths provide flexibility and convenience by allowing you to navigate and access files and directories relative to your current position in the file system.

It's important to note that the interpretation of relative paths can vary depending on the context. When changing the current working directory, the meaning of a relative path may change accordingly.

## Important Files and Directories


1. The Kernel
The kernel is like the heart of the Linux system. It manages communication between the hardware and peripherals, starts and stops processes and server processes, and performs many other important tasks. In short, the kernel is the most crucial file in the system.

2. The Shell
2.1 What is a Shell?
The shell is a way to communicate with the computer. It can be compared to a language that allows users to interact with the system. Unlike graphical interfaces where the computer leads the conversation, the shell allows users to take the initiative and have a two-way conversation with the system. It provides flexibility, automation, and a powerful tool for both beginners and advanced users.

2.2 Shell Types
There are different shell types, just like there are different languages and dialects spoken by people. Some common shell types include:

`sh or Bourne Shell`: The original shell used on UNIX systems.
`bash or Bourne Again SHell`: The standard GNU shell, widely used and recommended for beginners.
`csh or C Shell`: Resembles the syntax of the C programming language.
`tcsh or Turbo C Shell`: Enhanced version of C Shell with improved user-friendliness and speed.
`ksh or Korn shell`: Popular among UNIX users, but can be challenging for beginners.
To switch between shells, simply enter the name of the desired shell in the active terminal. Each shell has its own appearance and functionality.

3. Your Home Directory
Your home directory is the default destination when you connect to the system. It usually resides in the /home directory but can vary depending on the system configuration. The path to your home directory is stored in the HOME environment variable, so you don't need to worry about it. You can store files, create directories, and organize your data within your home directory. However, there may be limits on the amount of data you can store, depending on system settings.

4. Configuration Files
Most configuration files are stored in the /etc directory. These files control various aspects of the system's behavior and can be viewed using the cat command. Common configuration files include those for mail servers, web servers, cron jobs (scheduled tasks), system defaults, network settings, authentication modules, and more. These files are usually well-commented and self-explanatory.

5. Devices
Devices, such as peripherals connected to your computer, are represented as entries in the /dev directory. Linux handles devices in a unified way, making it easier for users and the system to interact with them. Some common device names include CD drives, serial ports, printers, sound cards, USB devices, and more.

6. Variable Files
Variable files are stored in the /var directory and hold data that frequently changes, such as log files, mailboxes, spoolers, and temporary files. These files are typically kept separate from system files for security and organization purposes. It's common for the /var directory to be on a separate partition to prevent issues like disk space filling up due to excessive log files or user activity.

## **Commands related to removing files:**

To remove a single file: `**rm <filename>**`

To remove an empty directory: `**rmdir <directory>**`

To remove a non-empty directory (including all its files and subdirectories): `**rm -r <directory>**`

To remove a directory and its contents without prompting for confirmation: `**rm -rf <directory>**`

To remove multiple files at once: `**rm <file1> <file2> <file3> ...**`

To remove files matching a specific pattern using wildcards: `**rm <pattern>**`

To prompt for confirmation before removing each file: `**rm -i <filename>**`

*Note: Be cautious when using the rm command, especially with the -r and -f options, as they can permanently delete files and directories without further confirmation. It's always a good practice to double-check the files you intend to remove before executing the command.*

## **Commands related to using the ls command:**

List files and directories in the current directory: **`ls`**

List all files and directories, including hidden files: **`ls -a`**

List files and directories in long format (including permissions, size, owner, etc.): **`ls -l`**

List a specific directory in long format: **`ls -l <directory>`**

List only the directory itself (not its contents) in long format: **`ls -ld <directory>`**

List files and directories in reverse order of the last change: **`ls -ltr`**

List files with their corresponding file types indicated by colors (if enabled): **`ls --color=auto`**

List files using the default suffix scheme for file types: **`ls --classify`**

Read the full documentation and functionality of the ls command: **`info coreutils ls`**

List of file/folders along with their inode numbers: **`ls -i`**

## Here's the table with the color scheme:

| Color  | File Type              |
|--------|------------------------|
| blue   | directories            |
| red    | compressed archives    |
| white  | text files             |
| pink   | images                 |
| cyan   | links                  |
| yellow | devices                |
| green  | executables            |
| flashing red | broken links       |

## Default suffix scheme for ls:

| Character | File Type            |
|-----------|----------------------|
| nothing   | regular file         |
| /         | directory            |
| *         | executable file      |
| @         | link                  |
| =         | socket               |
| \|        | named pipe           |

**Type `ls /dev -F` and check out suffix scheme**

This table provides the mapping between colors, characters, and file types used in the ls command's output.

*Note: The ls command is highly customizable and has many more options and features. You can refer to the man page (man ls) or the Info pages for more detailed information on how to utilize the command effectively.*

The file command is used to determine the type of a file. It applies tests to check properties, magic numbers, and language tests to make an educated guess about the file's format. mike:~> `file vi.gif`
vi.gif: GIF image data, version 89a, 88 x 31  
mike:~> `file /dev/log`
/dev/log: socket

## Commands related to creating directories, moving files, and copying files:

Making a directory/folder: **`mkdir <name>`**

Creating directories and subdirectories in one step: `**mkdir -p <dir>/<sub-dir>/<sub-dir>/<sub-dir>**`

The `mv` command is used to move or rename files: `**mv <source file/files> <destination directory>**`

Coping from old to new file/directory(empty): `**cp <old> <new>**`
`
The -R option allows recursive copying, which means copying all files and subdirectories within a directory: `**cp -R <old> <new>**`

## Finding Files

`**find <path> -name <searchstring>**`: This can be interpreted as "Look in all files and subdirectories contained in a given path, and print the names of the files containing the search string in their name" (not in their content).

`locate` can be used as well for finding files, it's better for machine performance.

*NOTES: The `"which"` command is used to search the directories specified in the user's search path for a specific executable file. It is particularly useful for troubleshooting "Command not Found" issues.*

The `"grep"` command is a powerful text-searching tool used in Unix-like operating systems.

Searching for a specific word in a file: `**grep "apple" fruits.txt**`

Searching for a pattern using regular expressions: `**grep "[0-9]{3}-[0-9]{4}" contacts.txt**`

Searching recursively in a directory: `**grep "error" -r /var/log/**`

**Viewing Files** 
`cat <filename>` ,` head or tail -n <filename>` head command helps view the first "n" lines on the file and tail command helps view the last "n" lines on the file. 

**Creating symbolic links**
The command to make links is `ln`. In order to create symlinks, you need to use the -s option:

`ln -s targetfile linkname`

**File security**

**Access Mode Codes**

Code | Meaning
-----|---------
0 or -|The access right that is supposed to be on this place is not granted.
4 or r|Read access is granted to the user category defined in this place.
2 or w|Write permission is granted to the user category defined in this place.
1 or x|Execute permission is granted to the user category defined in this place.

**User Group Codes**

Code | Meaning
-----|---------
u|User permissions
g|Group permissions
o|Permissions for others

There are also operators to manipulate the permissions:

| **Task**                 | **Operator** |
| ------------------------ | ------------ |
| Grant a level of access  | +            |
| Remove a level of access | -            |
| Set a level of access    | =            |

**Using chmod**

`chmod u+rwx,go-rwx <file>` is used to modify the permissions of the file using the chmod command.

Here's the breakdown of the command:

`u+rwx:` Grants` read (r)`, `write (w)`, and `execute (x)` permissions to the `user (owner)` of the file.
`,`: Separates the permission specification for the user from the permission specification for the group and others.
`go-rwx:` Removes` (-) `all permissions `(rwx)` for both the group and others on the file hello.

Using `chmod` with numeric arguments:

| Command          | Meaning                                                                     |
|------------------|-----------------------------------------------------------------------------|
| chmod 400 file   | To protect a file against accidental overwriting.                            |
| chmod 500 directory | To protect yourself from accidentally removing, renaming or moving files from this directory. |
| chmod 600 file   | A private file only changeable by the user who entered this command.         |
| chmod 644 file   | A publicly readable file that can only be changed by the issuing user.       |
| chmod 660 file   | Users belonging to your group can change this file, others don't have any access to it at all. |
| chmod 700 file   | Protects a file against any access from other users, while the issuing user still has full access. |
| chmod 755 directory | For files that should be readable and executable by others, but only changeable by the issuing user. |
| chmod 775 file   | Standard file sharing mode for a group.                                       |
| chmod 777 file   | Everybody can do everything to this file.                                    |

**Sticky bit**

In Linux, there is a special feature called the sticky bit within the permission system. The sticky bit can be applied to directories, and its purpose is to restrict the deletion or renaming of files within that directory to only the owner. Other users may or may not have the ability to edit the files, but only the owner has the privilege to delete or rename them. You can set the sticky bit on a folder using the following command:
`chmod +t someDirectory/`

When the sticky bit is set, the permission string for the directory will end with a `t`, such as `drwxrwxr-t`. To remove the sticky bit, you can use the command:

`chmod -t someDirectory/`

By utilizing the sticky bit, you can ensure that important files within a directory remain protected from accidental deletion or renaming by users other than the owner.

**Here's the table for the new commands in Files and the file system:**

| Command                   | Meaning                                                      |
|---------------------------|--------------------------------------------------------------|
| bash                      | GNU shell program.                                          |
| cat file(s)               | Send content of file(s) to standard output.                  |
| cd directory              | Enter directory. cd is a bash built-in command.              |
| chgrp newgroup file(s)    | Change the group ownership of file(s) to newgroup.            |
| chmod mode file(s)        | Change access permissions on file(s).                        |
| chown newowner[:newgroup] file(s) | Change file owner and group ownership.                |
| cp sourcefile targetfile  | Copy sourcefile to targetfile.                               |
| df file                   | Reports on used disk space on the partition containing file. |
| echo string               | Display a line of text.                                      |
| export                    | Part of bash that announces variables and their values to the system. |
| file filename             | Determine file type of filename.                             |
| find path expression      | Find files in the file system hierarchy.                     |
| grep PATTERN file         | Print lines in file containing the search pattern.           |
| head file                 | Send the first part of file to standard output.              |
| id                        | Prints real and effective user name and groups.              |
| info command              | Read documentation about command.                            |
| less file                 | View file with a powerful viewer.                            |
| ln targetfile linkname    | Make a link with name linkname to targetfile.                |
| locate searchstring       | Print all accessible files matching the search pattern.      |
| ls file(s)                | Prints directory content.                                   |
| man command               | Format and display online (system) manual pages for command. |
| mkdir newdir              | Make a new empty directory.                                  |
| mv oldfile newfile        | Rename or move oldfile.                                      |
| newgrp groupname          | Log in to a new group.                                       |
| pwd                       | Print the present or current working directory.              |
| quota                     | Show disk usage and limits.                                  |
| rm file                   | Removes files and directories.                               |
| rmdir file                | Removes directories.                                         |
| tail file                 | Print the last part of file.                                 |
| umask [value]             | Show or change new file creation mode.                       |
| wc file                   | Counts lines, words, and characters in file.                 |
| which command             | Shows the full path to command.                              |

And remember, it is highly recommended to read the manual pages for detailed information about each command.

## Processes

| (Part of) Command | Meaning                                                                                            |
|-------------------|----------------------------------------------------------------------------------------------------|
| regular_command   | Runs this command in the foreground.                                                               |
| command &         | Run this command in the background (release the terminal).                                         |
| jobs              | Show commands running in the background.                                                           |
| Ctrl+Z            | Suspend (stop, but not quit) a process running in the foreground (suspend).                        |
| Ctrl+C            | Interrupt (terminate and quit) a process running in the foreground.                                |
| %n                | Every process running in the background gets a number assigned to it. Use %n to refer to a job by its number, for example, fg %2. |
| bg                | Reactivate a suspended program in the background.                                                  |
| fg                | Puts the job back in the foreground.                                                               |
| kill              | End a process (also see Shell Builtin Commands in the Info pages of bash).                         |

The `ps` command is one of the tools for visualizing processes. This command has several options which can be combined to display different process attributes.

The `'ps'` command provides a snapshot of the current state of active processes, capturing their information at a specific moment. On the other hand, the `'top'` program offers a more detailed and up-to-date view. It continuously updates the results obtained from 'ps' (with various options) every five seconds, generating a fresh list of processes that are putting the most strain on the system. *Additionally, 'top' incorporates additional details such as swap space usage and CPU status, gathering this information from the proc file system.*

*NOTE: The relations between processes can be visualized using the `pstree` command.*

`**kill -l**` command displays a list of signal names and their corresponding numbers. Signals are used to communicate with processes and manage their behavior.
OUTPUT: 1) SIGHUP	2) SIGINT	3) SIGQUIT	4) SIGILL	5) SIGTRAP
6) SIGABRT	7) SIGBUS	8) SIGFPE	9) SIGKILL	10) SIGUSR1
11) SIGSEGV	12) SIGUSR2	13) SIGPIPE	14) SIGALRM	15) SIGTERM
16) SIGSTKFLT	17) SIGCHLD	18) SIGCONT	19) SIGSTOP	20) SIGTSTP
21) SIGTTIN	22) SIGTTOU	23) SIGURG	24) SIGXCPU	25) SIGXFSZ
26) SIGVTALRM	27) SIGPROF	28) SIGWINCH	29) SIGIO	30) SIGPWR
31) SIGSYS	34) SIGRTMIN	35) SIGRTMIN+1	36) SIGRTMIN+2	37) SIGRTMIN+3
38) SIGRTMIN+4	39) SIGRTMIN+5	40) SIGRTMIN+6	41) SIGRTMIN+7	42) SIGRTMIN+8
43) SIGRTMIN+9	44) SIGRTMIN+10	45) SIGRTMIN+11	46) SIGRTMIN+12	47) SIGRTMIN+13
48) SIGRTMIN+14	49) SIGRTMIN+15	50) SIGRTMAX-14	51) SIGRTMAX-13	52) SIGRTMAX-12
53) SIGRTMAX-11	54) SIGRTMAX-10	55) SIGRTMAX-9	56) SIGRTMAX-8	57) SIGRTMAX-7
58) SIGRTMAX-6	59) SIGRTMAX-5	60) SIGRTMAX-4	61) SIGRTMAX-3	62) SIGRTMAX-2
63) SIGRTMAX-1	64) SIGRTMAX	

Signal Name | Signal Number | Meaning
--- | --- | ---
SIGTERM | 15 | Terminate the process in an orderly way.
SIGINT | 2 | Interrupt the process. A process can ignore this signal.
SIGKILL | 9 | Interrupt the process. A process cannot ignore this signal.
SIGHUP | 1 | For daemons: reread the configuration file.

**States of process**

| State of process |  Description |
| ------------- | ------------- |
|  `R` | The process is running |
|  `S` | Interruptable sleep |
|  `D` | Uninterruptable sleep |
|  `Z` | Zombie |
|  `T` | Stopped |

Command | Meaning | Usage
--- | --- | ---
at | Queue jobs for later execution. | `at [-f file] time`
atq | Lists the user's pending jobs. | `atq [-q queue]`
atrm | Deletes jobs, determined by their job number. | `atrm <job>`
batch | Executes commands when system load level permits. | `batch`
crontab | Maintain crontab files for individual users. | `crontab [-u user] file`
halt | Stop the system. | `halt`
init run level | Process control initialization. | `init <runlevel>`
jobs | Lists currently executing jobs. | `jobs [-l]`
kill | Terminate a process. | `kill [-signal] pid`
mesg | Control write access to your terminal. | `mesg [y/n]`
netstat | Display network connections, routing tables, interface statistics, masquerade connections, and multicast memberships. | `netstat [-options]`
nice | Run a program with modified scheduling priority. | `nice [-n increment] command`
pgrep | Display processes. | `pgrep [-signal] pattern`
ps | Report process status. | `ps [-options]`
pstree | Display a tree of processes. | `pstree [-options]`
reboot | Stop the system. | `reboot`
renice | Alter the priority of running processes. | `renice [-n increment] [-p pid]`
shutdown | Bring the system down. | `shutdown [-options]`
sleep | Delay for a specified time. | `sleep <duration>`
time | Time a command or report resource usage. | `time command`
top | Display top CPU processes. | `top`
uptime | Show how long the system has been running. | `uptime`
vmstat | Report virtual memory statistics. | `vmstat [-options]`
w | Show who is logged on and what they are doing. | `w [-husf]`
wall | Send a message to everybody's terminals. | `wall [-n] message`
who | Show who is logged on. | `who [-Hu]`
write | Send a message to another user. | `write user [terminal]`

## I/O redirection
There are three types of I/O, which each have their own identifier, called a file descriptor:

`standard input: 0 : <`

`standard output: 1 : >`

`standard error: 2`

Output redirection with `>` and `|` e.g. `cat test1 test2 > test3` this will redirect the contents of test1 and test2 files to test3 as well as ovewrite the content of test3. Use `>>` operator to append content.

Redirecting "nothing" to an existing file is equal to emptying the file: `> list` This process is called *truncating*.

Create a new empty file : `> newlist`
`cat file | mail someone` or `mail abc@somewhere.org < file` 

`tee` command to copy input to standard output and one or more output files in one move.
`date | tee file1 file2` tee called on through a pipe (|).
`uptime | tee -a file2` -a option to tee results in appending input to the file(s).

**A program that takes input, performs operations on it, and produces the output on the standard output is known as a `filter`. Filters are frequently used to modify the structure of output.**
1. https://www.gnu.org/software/grep/manual/grep.html `grep`
2. https://cheat.sh/sort `sort`

**Text Editor:**  enter the `vimtutor` command in your shell or command line after installing vim.
##

You can view a comprehensive list of all variables currently defined for your session by using the `"printenv"` command.

**Common environment variables:**

| Variable name   | Stored information                                        |
|-----------------|----------------------------------------------------------|
| DISPLAY         | Used by the X Window system to identify the display server |
| DOMAIN          | Domain name                                              |
| EDITOR          | Stores your favorite line editor                          |
| HISTSIZE        | Size of the shell history file in number of lines         |
| HOME            | Path to your home directory                               |
| HOSTNAME        | Local host name                                          |
| INPUTRC         | Location of definition file for input devices             |
| LANG            | Preferred language                                       |
| LD_LIBRARY_PATH | Paths to search for libraries                             |
| LOGNAME         | Login name                                               |
| MAIL            | Location of your incoming mail folder                     |
| MANPATH         | Paths to search for man pages                             |
| OS              | String describing the operating system                    |
| OSTYPE          | More information about version, etc.                      |
| PAGER           | Used by programs like `man` for handling large outputs    |
| PATH            | Search paths for commands                                 |
| PS1             | Primary prompt                                           |
| PS2             | Secondary prompt                                         |
| PWD             | Present working directory                                |
| SHELL           | Current shell                                            |
| TERM            | Terminal type                                            |
| UID             | User ID                                                  |
| USER(NAME)      | User name                                                |
| VISUAL          | Your favorite full-screen editor                         |
| XENVIRONMENT    | Location of your personal settings for X behavior         |
| XFILESEARCHPATH | Paths to search for graphical libraries                   |

`echo $VARIBLE_NAME` to check out a specific variable.
In order to change the content of a variable use `export VARIABLE = value` e.g. `export PATH=$PATH:/path to directory`

*NOTE:When you export a variable in a session, it is valid only for that specific session and its child processes. Once you restart the computer or start a new session, the exported variables are no longer available. To make the changes to environment variables persistent across system reboots or new sessions, you would need to set them in configuration files that are read during the system startup or login process. The specific files and methods for setting persistent environment variables may vary depending on the operating system and shell you are using.*

**https://tldp.org/HOWTO/Bash-Prompt-HOWTO/ Bash Prompt HOWTO**
**https://tldp.org/ The Linux Documentation Project**

| Command    | Meaning                                                 | Usage                                                    |
|------------|---------------------------------------------------------|----------------------------------------------------------|
| aptitude   | Manage packages Debian-style.                           | `aptitude install <package>`                              |
| automount  | Automatically include newly inserted file systems.       | `automount -m <mountpoint>`                               |
| dpkg       | Debian package manager.                                 | `dpkg -i <package.deb>`                                   |
| dselect    | Manage packages Debian-style.                            | `dselect`                                                |
| loadkeys   | Load keyboard configuration.                            | `loadkeys <keymap>`                                      |
| lsof       | Identify processes.                                     | `lsof -i :<port>`                                        |
| mount      | Include a new file system into the existing file system tree. | `mount <device> <mountpoint>`                       |
| ntpdate    | Set the system time and date using a time server.        | `ntpdate <time_server>`                                   |
| quota      | Display information about allowed disk space usage.      | `quota -u <username>`                                    |
| recode     | Convert files to another character set.                 | `recode <encoding> <inputfile> > <outputfile>`             |
| rpm        | Manage RPM packages.                                    | `rpm -i <package.rpm>`                                   |
| setfont    | Choose a font.                                          | `setfont <fontfile>`                                     |
| timezone   | Set the timezone.                                       | `timezone <timezone>`                                    |
| tzconfig   | Set the timezone.                                       | `tzconfig`                                               |
| ulimit     | Set or display resource limits.                         | `ulimit -n <limit>`                                      |
| up2date    | Manage RPM packages.                                    | `up2date -u`                                             |
| urpmi      | Manage RPM packages.                                    | `urpmi <package>`                                        |
| yum        | Manage RPM packages.                                    | `yum install <package>`                                  |

*Please note that the above usage examples are simplified and may require additional options or arguments depending on the specific use case. Make sure to consult the command's documentation or man page for more detailed information on how to use each command.*

Commands related to printing:

| Command    | Meaning                                          | Usage                                      |
|------------|--------------------------------------------------|--------------------------------------------|
| lpr or lp  | Print file                                       | `lpr <file>` or `lp <file>`                 |
| lpq or lpstat | Query print queue                                | `lpq` or `lpstat`                          |
| lprm or cancel | Remove print job                               | `lprm <jobID>` or `cancel <jobID>`          |
| acroread   | PDF viewer                                       | `acroread <file.pdf>`                      |
| groff      | Formatting tool                                  | `groff -ms <file>`                         |
| gv         | PostScript viewer                                | `gv <file.ps>`                             |
| printconf  | Configure printers                              | `printconf`                                |
| xdvi       | DVI viewer                                       | `xdvi <file.dvi>`                          |
| xpdf       | PDF viewer                                       | `xpdf <file.pdf>`                          |
| *2ps       | Convert file to PostScript                       | `<command> <file> > output.ps`             |

*Please note that the above usage examples are simplified and may require additional options or arguments depending on the specific use case. Make sure to consult the command's documentation or man page for more detailed information on how to use each command.*

## Archiving data using the tar command, as well as compressing and unpacking the archives using gzip and bzip2.

1. **Preparing Your Data:**
        **Archiving with tar:**
                -The `tar` command is used to create archive files by concatenating and compressing listed files.
                -Use the `-c` option to create an archive and the `-f` option to specify the archive file name.
                -Example: `tar cvf archive.tar files/` creates an archive named archive.tar containing the files/ directory.
                -Example: `tar cvf archive.tar file1 file2` creates an archive named archive.tar containing file1 and file2.
2. **Incremental Backups with tar:**

        -tar supports creating incremental backups using the `-N` option.
        -With -N, you can specify a date, and tar will include files modified more recently than the specified date in the backup.
        -Example: `tar -N backup.tar -cvp files/` creates an incremental backup of files modified since the backup.tar archive.
        -Example: `tar -N backup.tar -cvp newfile` creates an incremental backup including only the newfile that is more recent than the backup.tar archive.
3. **Compressing and Unpacking with gzip or bzip2:**

        -Data, including tarballs, can be compressed using `gzip` or `bzip2`.
        -Use gzip to compress files, adding the `.gz` extension to the file name.
        -Example: `gzip file.txt` compresses file.txt and creates `file.txt.gz`.
        -Use `gzip -d` or `gunzip` to uncompress .gz files.
        -Example: `gzip -d file.txt.gz` uncompresses file.txt.gz.
        -Use `bzip2` for improved compression, creating smaller files than gzip.
        -Example: `bzip2 file.txt` compresses file.txt and creates file.txt.bz2.
        -Use `bzip2 -d` or `bunzip2` to uncompress .bz2 files.
        -Example: `bzip2 -d file.txt.bz2` uncompresses file.txt.bz2.

4. **Unpacking Compressed Archives with tar:**

        -tar can directly handle compressed archives using the appropriate options.
        -Use `tar zxvf file.tar.gz` to extract and uncompress a .tar.gz or .tgz archive.
        -Use `tar jxvf file.tar.bz2` to extract and uncompress a .tar.bz2 archive.

**Data Encryption with GNU Privacy Guard(`gpg`)**
generate a key: `gpg --key-gen`
get information about your key: `gpg --list-keys`
encrypt a .tar archive: `gpg -e -r (part of) uid archive` , `-e` option tells gpg to encrypt, the `-r` option indicates who to encrypt for.

*Note: Manual page for gpg*










 













