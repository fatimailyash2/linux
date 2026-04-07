**pwd** - print working directory - tells the current path present in

**ls** - list - lists the contents of the current working directory (eg ls Desktop)

**cd** - change directory - changes the path/location from the current path (eg cd ..)

**man** - manual - displays the manual pages for commands and provides detailed information about their usage, shows the possible options we can run with the command and the results (eg man ls)

**--help** - describes a tool (eg ls --help)

**apropos** - searches the descriptions for instances of a given keyword (eg apropos ls)

**whoami** - displays current user

**clear** - clears the terminal

**-p** - port - state the port number in the terminal (eg -p 2220)

**cat** - concatenate - displays the contents of a file (eg cat ls)

**cp** - copy - copies a file (eg cp ls <filename>) \[sudo must be used for this command, tf sudo cp ls <filename>. if command has already been entered, state "sudo !!"]

**sudo** - superuser do - allows user to execute commands with administrative privileges (use sudo !! if command is accidentally run without sudo)

**rm** - remove - deletes a file

**adduser** - adds a new user to the system (eg sudo adduser <username>) \[sudo command is user here because this command is an sbin file command]

**which** - tell us which command is being used from what location if the same command is present in two different locations ["which ls" tells us if we're currently using the ls command from "/usr/bin" or "/bin/"]

**ssh** - secure shell - protocol that allows clients to access and execute commands or actions on remote computers

**uname** - prints system information, 
        -a, --all
              print all information, in the following order, except omit -p and -i if unknown:

       -s, --kernel-name
              print the kernel name

       -n, --nodename
              print the network node hostname

       -r, --kernel-release
              print the kernel release

       -v, --kernel-version
              print the kernel version

       -m, --machine
              print the machine hardware name

       -p, --processor
              print the processor type (non-portable)

       -i, --hardware-platform
              print the hardware platform (non-portable)

       -o, --operating-system


**echo** - displays/prints lines of text, create new text (.txt) files 
    - echo "text" > ex.txt (redirect the output of the first command. This will create the file (or overwrite it if it already exists))
    - echo "more text" >> ex.txt [appended text] (append the output of the subsequent commands to the file without deleting its existing content.)
    *use cat to display the contents of a text file in the terminal*

**grep** - global regular expression print - finds keywords in the contents of a file (eg grep "text" filename.txt)

to add sorted results to a new or existing text file, use the command "grep "KEYWORD" filename.txt > newfile.txt"

-----

**find** - finds a file from current directory (eg find filename.txt)

**touch** - create an empty file

In Linux, any file or directory name that starts with a dot (.) is considered hidden. For example, [echo "Hidden file" > .hidden file] creates a hidden file.

**mkdir** - make directory - creates a new directory

The -l option (that's a lowercase L, not the number 1) provides a "long" format listing. You'll see additional details like file permissions, owner, size, and modification date (eg ls -l).

"-a ", will show all files, including the hidden .hiddenfile we created.

The command "ls -la" will show all files in their long formats.

"cp file2.txt testdir/" copies a file to another directory, i.e, the testdir directory.

"cp -r testdir testdir_copy" creates a copy of a directory. "-r " stands for recursive, and is required to ensure all contents are copied.

**mv** - move - moving and renaming files (eg mv filename destination)

"mv testdir/newname.txt ./original_file1.txt" This moves newname.txt out of testdir and renames it to original_file1.txt in the current directory.

"rm -i file2.txt", in this command, "-i " prompts for confirmation before deletion of a file.

**rmdir** - removes/deletes ONLY EMPTY directories

**-f** - force - forcefully removes files without being prompted, even if they are write-protected.

Now, let's combine -r and -f. The rm -rf command is extremely powerful and potentially dangerous. It removes directories recursively (-r) and forces removal without prompting (-f).
Be ABSOLUTELY SURE you know what you are deleting before running rm -rf. A small typo could delete critical system files or your personal data. There is no undo. For example, rm -rf / could attempt to delete your entire system (if you have permissions). Always double-check the path.

For ls, -R means "recursive listing" (list subdirectories), while -r means "reverse sort order". For cp and rm, the recursive option is -r (lowercase).

**Paths**: Using ~ to refer to your home directory (e.g., ~/Desktop is the same as home/Desktop).

"cat -n /tmp/hello" 
Output: 1 Hi,
        2 I am Labby!
The -n here is called an option or a flag. It tells cat to number all output lines.

**head** - used to view the beginning or head of a file

"head -n1 /tmp/hello" 
Output: Hi,
Here, -n1 is an option that tells head to show only the first line. The 1 can be changed to any number to show that many lines.

"head -c1 /tmp/hello"
Output: H
The -c1 option tells head to show only the first byte (character) of the file. Like with -n, you can change the 1 to any number to see that many bytes. In each file, each character is typically 1 byte.

**tail** - used to show the end of the file

"tail -n1 /tmp/hello"
Output: I am Labby!

**diff** - compare two files and see the differences between them

Just like with files, the order matters when comparing directories. *diff dir1 dir2* shows what's in dir1 but not in dir2, while *diff dir2 dir1* shows the opposite.

-----

"diff file1 file2"
Output: 1c1
< this is file1
---
> this is file2

Let's break down what this output means. The diff command produces output that describes what changes are needed to make the first file identical to the second file. It doesn't matter which file was created or modified first; diff only compares their contents at the time you run the command.

1c1: This indicates that line 1 in the first file needs to be changed to match line 1 in the second file.
< this is file1: The < symbol indicates a line from the first file (file1).
---: This is a separator between the lines from file1 and file2.
> this is file2: The > symbol indicates a line from the second file (file2).
In simple terms, diff is showing us that the content of line 1 is different between the two files. To make file1 match file2, the line "this is file1" would need to be replaced with "this is file2".

basically, the line "this is file1" in file1 needs to be changed to "this is file2" in file1 to make file1 and file2 identical.

-----

"diff -r ~/Desktop ~/Code" [comparing directories]
Output: Only in /home/labex/Desktop: code.desktop
Only in /home/labex/Desktop: gedit.desktop
Only in /home/labex/Desktop: gvim.desktop
Only in /home/labex/Desktop: xfce4-terminal.desktop

This output shows that the Desktop directory contains four files that are not in the Code directory.

-----

**ps** - process status - lists the processes running in the linux box and what their status is

**$** - you are logged in as a user on the system

**useradd** - same as adduser, but does not ask for any details like password, name, etc, just adds a new user directly [sudo command is used here]

**usermod** - user modification - modify a user account [sudo command is used here]

**su** - switch user - become another user (eg su - fatima) [sudo command is used here]

"sudo visudo" - the reccommended way to access/edit the sudoers file (sudoers file controls which users and groups can execute commands with elevated (typically root) privileges.)

**userdel** - delete a user [sudo command is used here]

**groupadd** - adds a new group [sudo command is used here]

**groupdel** - delete an existing group

use the commands "logout", "exit", or ctrl+d to logout of the current user account

**gpasswd** - remove a user from a group (sudo gpasswd -d [user] [group])

"sudo usermod -aG [group] [user]" - "a" stands for append, this adds the group without removing the user from their existing groups. "G" specifies extra groups that the user belongs to. if this command is run without "a" Linux will replace all the user’s groups with just the new group.this can break permissions and lock users out of stuff.

**groups** - tells you what groups you are a member of

**chown** - change owner/ownership - modify both the user and group ownership of a file. Ownership determines who has control over the file. [sudo is used here] (eg sudo chown root:root example.txt, root:root means the user root, and the group root)

-----

"mkdir -p new-dir/subdir" creates the new-dir directory and its subdir subdirectory. The -p option tells mkdir to create parent directories as needed. Without -p, if new-dir didn't exist, creating new-dir/subdir would fail.

-----

"sudo chown -R root:root new-dir" The -R option tells chown to operate recursively, changing the ownership of all files and subdirectories within new-dir. This is crucial; without -R, only the new-dir directory's ownership would change, but the files and subdirectories within it would still be owned by labex.

-----

**chmod** - change mode - modify the permissions of files and directories [sudo is required]

"-rw-rw-r-- 1 root root 0 Jul 29 15:11 example.txt" The -rw-rw-r-- part represents the file permissions. This is where the numeric and symbolic notations come in. Let's break it down:

The first character (-) indicates this is a regular file. Other common indicators are d for directory and l for symbolic link.
The next three characters (rw-) represent the owner's permissions (read and write, but not execute).
r stands for read permission: The owner can open and read the file.
w stands for write permission: The owner can modify the file.
x stands for execute permission: The owner can run the file (if it's a program or script). A - means the permission is denied.
The next three (rw-) are for the group. They have the same meaning as above, but apply to members of the file's group.
The last three (r--) are for others (everyone else). They also have the same meaning, but apply to users who are neither the owner nor members of the file's group.

-----

"sudo chmod 700 example.txt" In this command:

700 is a numeric representation of permissions:
The first digit (7) represents the owner's permissions.
The second digit (0) represents the group's permissions.
The third digit (0) represents the others' permissions.
Each digit is a number from 0 to 7, calculated by adding the values for read (4), write (2), and execute (1) permissions:

4: Read permission
2: Write permission
1: Execute permission
0: No permission
So, 7 (first digit) gives the owner read (4), write (2), and execute (1) permissions: 4+2+1=7
0 (second digit) gives the group no permissions (0+0+0=0).
0 (third digit) gives others no permissions (0+0+0=0).

Therefore, 700 means: Owner: read, write, execute. Group: none. Others: none.

-----

"ls -ld ~/test-dir" The -d option in ls -l tells ls to list the directory itself, rather than its contents. Without -d, ls would list the files and subdirectories inside test-dir, which is empty right now.

-----

"echo '#!/bin/bash\necho "Hello, World"' > script.sh" This command does two things:

It creates a new file named script.sh. The .sh extension is commonly used for shell scripts. shell scripts are executable files that contain a series of commands that are executed in sequence.
It writes two lines into this file:
#!/bin/bash (called a shebang) tells the system this is a bash script. The shebang line specifies the interpreter that should be used to execute the script. In this case, it's /bin/bash, which is the path to the Bash interpreter.
echo "Hello, World" is a command that will print "Hello, World" when the script runs. The echo command simply displays the text that follows it.
\n is a newline character, ensuring the commands are on separate lines in the file.

-----

"chmod u+x script.sh" In this command:

u refers to the user (owner). Other options are g for group, o for others, and a for all (user, group, and others).
+x adds execute permission. The + symbol adds a permission, while the - symbol removes a permission.
So, u+x means "add execute permission for the owner."

-----

"sudo grep -w 'joker' /etc/passwd" --> "-w" means match the whole word only (only "joker", not "joker123" or "jokerabc"). "grep" scans files (or command output) and prints the lines that contain a word or pattern (basically find lines containing a word inside files or command output). other commands include "-i", which ignores uppercase and lowercase, and "-n", which shows line numbers.
Output: joker:x:5001:5001::/home/joker:/bin/sh
joker: The username.
x: Indicates the password is stored securely in the /etc/shadow file.
5001: The User ID (UID) assigned to this account.
5001: The Group ID (GID) assigned to this account.
:/home/joker: The designated home directory path (though it isn't physically created on the disk yet).
:/bin/sh: The default command shell the user will use.

-----

"sudo useradd -m bob" The -m option tells the system to create a home directory for the user. A home directory is like a personal folder where a user can store their files and settings.

-----

"drwxr-x--- 2 bob bob 57 Jan 19 13:33 /home/bob" 57 is the size of the directory in bytes
Jan 19 13:33 is when the directory was created
/home/bob is the location of the directory

-----

"sudo usermod -aG sudo joker" Here's what this does:

usermod is the command to modify user accounts
-aG means "append to Group" (add to a group without removing from other groups)
sudo is the group we're adding the user to
joker is the user we're modifying

-----

"sudo passwd -l joker" The -l option locks the password. 
"sudo passwd -u joker" The -u option unlocks the password.

-----

**passwd** - set passsword for user (eg sudo passwd user) [sudo is required]

**uptime** - checks how long the system is running, current system load, shows system uptime, and load average

**top** - starts the monitoring interface which observes system's current performance, includes checking CPU and memory usage, and seeing which processes are running.
This display shows:

System summary: Current time, uptime, users, and load averages
Task summary: Total processes and their states (running, sleeping, etc.)
CPU usage: Breakdown of CPU utilization by category
Memory usage: Total, free, used, and available memory
Process list: Running processes sorted by CPU usage with PID, user, and resource consumption
The display updates automatically every few seconds, providing real-time system monitoring.

press **q** to exit the monitoring interface

**tar** - tape archive - creates and manipulates archive files, common compression format is gzip, which adds the .gz extension to the filename.
The tar command uses different options (flags) to control its behavior:

c: Create a new archive
z: Compress the archive using gzip
f: Specify the filename of the archive
So tar -czf archive.tar.gz file1 file2 creates a new compressed archive named archive.tar.gz containing file1 and file2.

You can use a wildcard (*) to select multiple files that match a pattern. For example, *_2023-*.log will match all files that end with .log and have _2023- in their name.

"tar -tf filename.tar.gz" lists only the names of the files and directories in the archive

"tar -tvf filename.tar.gz" provides a detailed list, similar to ls -l output, including file permissions, ownership, size, and timestamp.

-----

**dmesg** - view kernel messages [sudo is required]
. Pipeline for filtering: You need to send the output of dmesg to grep to filter for specific keywords. Use the pipe operator | to connect them.
. Handle multiple keywords: Since you need to search for both "fail" OR "error" in a case-insensitive manner, consider using the grep options -i (for case-insensitive) and -E (for extended regular expressions, which allows you to use the | symbol between your search terms).
. eg "sudo dmesg | grep [your_options (i.e -E , -i , -r)] "term1|term2" > ~/project/boot_issues.txt"

-----

**dpkg** - d-package - installs, removes, and queries .deb packages directly, maintaining a local database of software

**apt** - advanced package tool - automates the installation, removal, and updating of software packages by managing dependencies and retrieving software from online repositories, making system maintenance efficient

**aptitude** - a package managing tool more advanced than apt, provides a visual interface rather than a command-line interface like apt

**snap** - a command-line interface for managing snaps, which are self-contained, sandboxed software packages that work across many different Linux distributions. Developed by Canonical, the snap tool interacts with a background service called snapd to handle installation, updates, and removal of applications. https://www.geeksforgeeks.org/linux-unix/snap-package-manager-on-ubuntu/ 

**ps** - process status - used to display information about currently running processes, provides a snapshot of processes at the time the command is executed

**daemon** - processes that run in the background and perform services like networking, printing, and SSH, daemon processes end with the letter "d", (eg SSHd) 

-----

"ps -aux"

a - Show processes for all users, not just your own.
u - Show the processes in user-oriented format, which includes the username, CPU/memory usage, and start time.
x - Include processes without a controlling terminal, such as background daemons.

Output: 
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.1 169084  5460 ?        Ss   10:00   0:01 /sbin/init

Column meanings:
**USER**
The username of the process owner.
Shows who started the process (root, your username, etc.).
**PID**
Process ID, a unique number identifying this process.
Used for killing, inspecting, or controlling processes.
**%CPU**
Percentage of CPU being used by the process right now.
On multicore systems, >100% is possible if a process uses multiple cores.
**%MEM**
Percentage of physical RAM used by the process.
**VSZ** (Virtual Memory Size)
The total virtual memory the process can access (in kilobytes).
Includes code, data, and memory mapped files.
**RSS** (Resident Set Size)
The portion of memory actually in RAM (not swapped out), in kilobytes.
**TTY**
Terminal associated with the process.
? means no terminal, common for daemons or background processes.
**STAT**
Process state. Common codes:
R = Running
S = Sleeping (idle)
D = Uninterruptible sleep (usually I/O wait)
Z = Zombie (finished but parent hasn't collected it)
Additional letters: s (session leader), + (foreground process group), etc.
**START**
Time or date the process started.
**TIME**
Total CPU time the process has used since it started.
**COMMAND**
The command or program that started the process, often including arguments.

-----

**systemd** - master daemon, service manager, initialization system, system boots, kernel boots, systemd boots and performs services like mounting file systems, starting all services and forking other daemons, systemd refers to daemons as "units"

**systemctl** - controls daemons

"sudo systemctl stop sshd" - stops the ssh service 
"sudo systemctl status ssh" - displays the status of the ssh service
"sudo systemctl start sshd" - starts the ssh service
"sudo systemctl restart sshd" - restarts the ssh service
"sudo systemctl reload sshd" - reloads/refreshes the ssh service
"sudo systemctl reload-or-restart sshd" - either reloads or restarts the ssh service

"sudo systemctl disable ntp" - ntp or network time protol service does not start when the system is booted again
"sudo systemctl enable ntp" - ntp service starts when the system is booted again

"sudo systemctl is-active ntp" 
"sudo systemctl is-enabled ntp"

**sudo systemctl list-units** - lists all the active units/daemons 

"sudo systemctl list-units -t service" - lists all the daemons/units that are services, meaning they end with .service. "-t" means type
"sudo systemctl list-units | grep "servicename" - finds a service from the list of daemons

**sudo systemctl list-unit-files --all** - finds all services that are not parsed (a document that a computer program has analyzed, broken down into its component parts, and converted from raw, unformatted text into a structured, machine-readable format), or saved into memory

**journalctl** - logs for systemd stuff

"sudo journalctl -xe"
-x (--catalog): Adds explanatory help text to the log messages. For known errors, it includes descriptions, possible solutions, and links to documentation in the output to help you understand the root cause of a failure.
-e (--pager-end): Immediately jumps to the very end of the journal in the pager (usually less). This allows you to see the most recent log entries without having to scroll through thousands of older lines.