# **Linux Commands**

**1. pwd Command**

The [pwd](https://www.javatpoint.com/linux-pwd) command is used to display the location of the current working directory.

**Syntax:**
```
pwd
```
2. mkdir Command

The mkdir command is used to create a new directory under any directory.

Syntax:

mkdir \<directory name\>

3. rmdir Command

The rmdir command is used to delete a directory.

Syntax: rmdir \<directory name\>

**4. ls Command**

The [ls](https://www.javatpoint.com/linux-ls) command is used to display a list of content of a directory.

**Syntax:**

**5. cd Command**

The [cd](https://www.javatpoint.com/linux-cd) command is used to change the current directory.

**Syntax:** cd  **\<**** directory ** name** \>**

6 . touch Command

The touch command is used to create empty files. We can create multiple empty files by executing it once.

Syntax:touch  **\<file**  name **\>**

7. **cat Command**

The cat command is a multi-purpose utility in the Linux system. It can be used to create a file, display content of the file, copy the content of one file to another file, and more.

Syntax:cat [OPTION]... [FILE]..

To create a file, execute it as follows:

cat  **\>**   **\<file**  name **\>**

 Enter file content

Press " **CTRL+ D**" keys to save the file. To display the content of the file, execute it as follows:

cat  **\<file**  name **\>**

9 **. cp Command**

The cp command is used to copy a file or directory.

Syntax:

To copy in the same directory:cp  **\<**** existing ** file name** \> ** ** \< ****new**  file name **\>**

To copy in a different directory:

Output:

1. 12. head Command
2. The head command is used to display the content of a file. It displays the first 10 lines of a file.

Syntax:head  **\<**** file ** name** \>**

13. tail Command

The tail command is similar to the head command. The difference between both commands is that it displays the last ten lines of the file content. It is useful for reading the error message.

Syntax:tail  **\<**** file ** name** \>**

19. useradd Command

The useradd command is used to add or remove a user on a Linux server.

Syntax:

useradd  username

20. passwd Command

The passwd command is used to create and change the password for a user.

Syntax: passwd  **\<**** username ****\>**

21. groupadd Command

The groupadd command is used to create a user group.

Syntax:

groupadd \<group name\>

24. grep Command

The grep is the most powerful and used filter in a Linux system. The 'grep' stands for "global regular expression print." It is useful for searching the content from a file. Generally, it is used with the pipe.

Syntax: command | grep  **\<**** searchWord ****\>**

30. wc Command

The wc command is used to count the lines, words, and characters in a file.

Wc \<file name\>

37. date Command

The date command is used to display date, time, time zone, and more.

Syntax:date

38. cal Command

The cal command is used to display the current month's calendar with the current date highlighted.

Syntax: cal

40. time Command

The time command is used to display the time to execute a command.

Syntax: time

42. df Command

The df command is used to display the disk space used in the file system. It displays the output as in the number of used blocks, available blocks, and the mounted directory.

Syntax:df

45. clear Command

Linux clear command is used to clear the terminal screen.

Syntax:clear

47. ssh Command

Linux ssh command is used to create a remote connection through the ssh protocol.

Syntax:ssh user\_name@host(IP/Domain\_name) **\</**** p ****\>**

49. ping Command

The ping command is used to check the connectivity between two nodes, that is whether the server is connected. It is a short form of "Packet Internet Groper."

Syntax:ping  **\<**** destination ****\>**

50. whoami

It tells you about the system's username.

1. who

1. w

This command tells about the users who are logged in and what are they doing.

Syntax: w

To create a new user by useradd command, execute the useradd command followed by username as follows:
```
sudo useradd mubeen
```
To set the password for the newly created user, execute the below command:
```
sudo passwd  mubeen
```
The su command allows you to run a shell as another user.

**Syntax:**
```
 su  **\<**** username ****\>**
```
**Command line tools**  includes commands like useradd, userdel, passwd, etc. These are mostly used by the server administrators.

Third and very rare tool is to  **edit the local configuration files**  directly using vi.
```
  /etc/passwd
```
#
# **Vi Editor with Commands**

![Shape1](RackMultipart20230515-1-belqa4_html_2acc6d3ffb00c92e.gif)

## What is vi

The vi editor is elaborated as  **vi** sual editor. It is installed in every Unix system. In other words, it is available in all Linux distros. It is user-friendly and works same on different distros and platforms. It is a very powerful application. An improved version of vi editor is  **vim**.

**The vi editor has two modes:**

- **Command Mode:**  In command mode, actions are taken on the file. The vi editor starts in command mode. Here, the typed words will act as commands in vi editor. To pass a command, you need to be in command mode.
 Press I or Press Insert to enter into insertmode
- **Insert Mode:**  In insert mode, entered text will be inserted into the file. The  **Esc**  key will take you to the command mode from insert mode.

By default, the vi editor starts in command mode. To enter text, you have to be in insert mode, just type  **'i'**  and you'll be in insert mode. Although, after typing  **i ** nothing will appear on the screen but you'll be in insert mode. Now you can type anything.

To exit from insert mode press  **Esc ** key, you'll be directed to command mode.

| **Commands** | **Action** |
| --- | --- |
| :wq | Save and quit |
| :w | Save |
| :q | Quit |
| :w fname | Save as fname |
| ZZ | Save and quit |
| :q! | Quit discarding changes made |
| :w! | Save (and write to non-writable file) |

To switch from command to insert mode:

| **Command** | **Action** |
| --- | --- |
| i | Start typing before the current character |
| I | Start typing at the start of current line |
| a | Start typing after the current character |
| A | Start typing at the end of current line |
| o | Start typing on a new line after the current line |
| O | Start typing on a new line before the current line |

# **! quit forcefully**

To move around a file:

| **Commands** | **Action** |
| --- | --- |
| j | To move down |
| k | To move up |
| h | To move left |
| l | To move right |

To delete:

| **Commands** | **Action** |
| --- | --- |
| x | Delete the current character |
| X | Delete the character before the cursor |
| r | Replace the current character |
| xp | Switch two characters |
| dd | Delete the current line |
| D | Delete the current line from current character to the end of the line |
| dG | delete from the current line to the end of the file |

