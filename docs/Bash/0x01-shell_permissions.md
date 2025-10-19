# Shell permissions
`DevOps`
`Shell`
`Bash`

## Resources:
Read or watch:

- [Permissions](https://linuxcommand.org/lc3_lts0090.php)

man or help:

- chmod
- sudo
- su
- chown
- chgrp
- id
- groups
- whoami
- adduser
- useradd
- addgroup

## Learning Objectives
Permissions

- What do the commands `chmod`, `sudo`, `su`, `chown`, `chgrp` do
- Linux file permissions
- How to represent each of the three sets of permissions (owner, group, and other) as a single digit
- How to change permissions, owner and group of a file
- Why can’t a normal user `chown` a file
- How to run a command with root privileges
- How to change user ID or become superuser

Other Man Pages

- How to create a user
- How to create a group
- How to print real and effective user and group IDs
- How to print the groups a user is in
- How to print the effective userid

## Requirements

### General

- All your scripts should be exactly two lines long (`$ wc -l file` should print 2)
- All your files should end with a new line ([why?](https://unix.stackexchange.com/questions/18743/whats-the-point-in-adding-a-new-line-to-the-end-of-a-file/18789))
- The first line of all your files should be exactly `#!/bin/bash`
- A `README.md` file at the root of the repo, containing a description of the repository
- A `README.md` file, at the root of the folder of this project, describing what each script is doing
- You are not allowed to use backticks, `&&`, `||` or `;`
- All your scripts must be executable. To make your file executable, use the `chmod` command: `chmod u+x file`. Later, we’ll learn more about how to utilize this command.

## More Info

Example of line count and first line
```
exa@ubuntu:/tmp$ wc -l 12-file_type
2 12-file_type
exa@ubuntu:/tmp$ head -n 1 12-file_type
#!/bin/bash
exa@ubuntu:/tmp$
```
In order to test your scripts, you will need to use this command: `chmod u+x file`. We will see later what does `chmod` mean and do, but you can have a look at `man chmod` if you are curious.

Example
```
exa@ubuntu:/tmp$ ls
12-file_type
lll
exa@ubuntu:/tmp$ ls -la lll
-rw-rw-r-- 1 exa exa 15 Sep 19 21:05 lll
exa@ubuntu:/tmp$ cat lll
#!/bin/bash
ls
exa@ubuntu:/tmp$ ls -l lll
-rw-rw-r-- 1 exa exa 15 Sep 19 21:05 lll
exa@ubuntu:/tmp$ chmod u+x lll # you do not have to understand this yet
exa@ubuntu:/tmp$ ls -l lll
-rwxrw-r-- 1 exa exa 15 Sep 19 21:05 lll
exa@ubuntu:/tmp$ ./lll
12-file_type
lll
exa@ubuntu:/tmp$
```

## Tasks

### 0. My name is Betty
Create a script that switches the current user to the user `betty`.

- You should use exactly 8 characters for your command (+1 character for the new line)
- You can assume that the user `betty` will exist when we will run your script
```
exa@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
9
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `0-iam_betty`

### 1. Who am I
Write a script that prints the effective username of the current user.
```
exa@ubuntu:/tmp/h$ ./1-who_am_i
exa
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `1-who_am_i`

### 2. Groups
Write a script that prints all the groups the current user is part of.
```
exa@ubuntu:/tmp/h$ ./2-groups
exa adm cdrom sudo dip plugdev lpadmin sambashare
exa@ubuntu:/tmp/h$
```

Note: depending on the user, you will get a different output.

Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: ` 2-groups`

### 3. New owner
Write a script that changes the owner of the file `hello` to the user `betty`.
```
exa@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 exa exa 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 exa exa  0 Sep 20 14:18 hello
exa@ubuntu:/tmp/h$ sudo ./3-new_owner
exa@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 exa exa 30 Sep 20 14:23 3-new_owner
-rw-rw-r-- 1 betty  exa  0 Sep 20 14:18 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `3-new_owner`

### 4. Empty!
Write a script that creates an empty file called `hello`.

Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `4-empty`

### 5. Execute
Write a script that adds execute permission to the owner of the file `hello`.

- The file `hello` will be in the working directory
```
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 28 Sep 20 14:26 5-execute
-rw-rw-r-- 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ ./hello
bash: ./hello: Permission denied
exa@ubuntu:/tmp/h$ ./5-execute
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 28 Sep 20 14:26 5-execute
-rwxrw-r-- 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `5-execute`

### 6. Multiple permissions
Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file `hello`.

- The file `hello` will be in the working directory
```
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 36 Sep 20 14:31 6-multiple_permissions
-r--r----- 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ ./6-multiple_permissions
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 36 Sep 20 14:31 6-multiple_permissions
-r-xr-xr-- 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `6-multiple_permissions`

### 7. Everybody!
Write a script that adds execution permission to the owner, the group owner and the other users, to the file `hello`

- The file `hello` will be in the working directory
- You are not allowed to use commas for this script
```
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 28 Sep 20 14:35 7-everybody
-rw-r----- 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ ./7-everybody
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 28 Sep 20 14:35 7-everybody
-rwxr-x--x 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `7-everybody`

### 8. James Bond
Write a script that sets the permission to the file `hello` as follows:

- Owner: no permission at all
- Group: no permission at all
- Other users: all the permissions
- The file `hello` will be in the working directory You are not allowed to use commas for this script
```
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 28 Sep 20 14:40 8-James_Bond
-rwxr-x--x 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ ./8-James_Bond
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 28 Sep 20 14:40 8-James_Bond
-------rwx 1 exa exa 23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `8-James_Bond`

### 9. John Doe
Write a script that sets the mode of the file `hello` to this:
```
-rwxr-x-wx 1 exa exa 23 Sep 20 14:25 hello
```

- The file `hello` will be in the working directory
- You are not allowed to use commas for this script

Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `9-John_Doe`

### 10. Look in the mirror
Write a script that sets the mode of the file hello the same as olleh’s mode.

- The file `hello` will be in the working directory
- The file `olleh` will be in the working directory
```
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 42 Sep 20 14:45 10-mirror_permissions
-rwxr-x-wx 1 exa exa 23 Sep 20 14:25 hello
-rw-rw-r-- 1 exa exa  0 Sep 20 14:43 olleh
exa@ubuntu:/tmp/h$ ./10-mirror_permissions
exa@ubuntu:/tmp/h$ ls -l
total 8
-rwxrw-r-- 1 exa exa 42 Sep 20 14:45 10-mirror_permissions
-rw-rw-r-- 1 exa exa 23 Sep 20 14:25 hello
-rw-rw-r-- 1 exa exa  0 Sep 20 14:43 olleh
exa@ubuntu:/tmp/h$
```
Note: the mode of `olleh` will not always be 664. Make sure your script works for any mode.

Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `10-mirror_permissions`

### 11. Directories
Create a script that adds execute permission to all subdirectories of the __current directory__ for the owner, the group owner and all other users.

Regular files should not be changed.
```
exa@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 exa exa   24 Sep 20 14:53 11-directories_permissions
drwx------ 2 exa exa 4096 Sep 20 14:49 dir0
drwx------ 2 exa exa 4096 Sep 20 14:49 dir1
drwx------ 2 exa exa 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ ./11-directories_permissions
exa@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 exa exa   24 Sep 20 14:53 11-directories_permissions
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir0
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir1
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `11-directories_permissions`

### 12. More directories
Create a script that creates a directory called `my_dir` with permissions 751 in the working directory.
```
exa@ubuntu:/tmp/h$ ls -l
total 20
-rwxrwxr-x 1 exa exa   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir0
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir1
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir2
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ ./12-directory_permission s
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa   39 Sep 20 14:59 12-directory_permissions
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir0
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir1
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir2
drwxr-x--x 2 exa exa 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```

Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `12-directory_permissions`

### 13. Change group
Write a script that changes the group owner to `school` for the file `hello`

The file `hello` will be in the working directory
```
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa   34 Sep 20 15:03 13-change_group
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir0
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir1
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir2
drwxr-x--x 2 exa exa 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ sudo ./13-change_group
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa      34 Sep 20 15:03 13-change_group
drwx--x--x 2 exa exa    4096 Sep 20 14:49 dir0
drwx--x--x 2 exa exa    4096 Sep 20 14:49 dir1
drwx--x--x 2 exa exa    4096 Sep 20 14:49 dir2
drwxr-x--x 2 exa exa    4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 exa school   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `13-change_group`

### 14. Owner and group
Write a script that changes the owner to `vincent` and the group owner to `staff` for all the files and directories in the working directory.
```
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa   36 Sep 20 15:06 100-change_owner_and_group
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir0
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir1
drwx--x--x 2 exa exa 4096 Sep 20 14:49 dir2
drwxr-x--x 2 exa exa 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ sudo ./100-change_owner_and_group
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 100-change_owner_and_group
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
-rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `100-change_owner_and_group`

### 15. Symbolic links
Write a script that changes the owner and the group owner of `_hello` to `vincent` and `staff` respectively.

The file `_hello` is in the working directory
The file `_hello` is a symbolic link
```
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa   44 Sep 20 15:12 101-symbolic_link_permissions
-rw-rw-r-- 1 exa exa   23 Sep 20 14:25 hello
lrwxrwxrwx 1 exa exa    5 Sep 20 15:10 _hello -> hello
exa@ubuntu:/tmp/h$ sudo ./101-symbolic_link_permissions
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa      44 Sep 20 15:12 101-symbolic_link_permissions
-rw-rw-r-- 1 exa exa      23 Sep 20 14:25 hello
lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `101-symbolic_link_permissions`

### 16. If only
Write a script that changes the owner of the file `hello` to `betty` only if it is owned by the user exa.

- The file `hello` will be in the working directory
```
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa    exa      47 Sep 20 15:18 102-if_only
-rw-rw-r-- 1 exa exa      23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$ sudo ./102-if_only
exa@ubuntu:/tmp/h$ ls -l
total 24
-rwxrwxr-x 1 exa exa      47 Sep 20 15:18 102-if_only
-rw-rw-r-- 1 betty  exa      23 Sep 20 14:25 hello
exa@ubuntu:/tmp/h$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `shell_permissions`
- File: `102-if_only`
