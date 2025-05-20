# Project 
## **0x01. Shell, permissions**
---
## Table of Contents
- [Author Details](#author-details)
- [Project Description](#project-description)
- [Tasks](#tasks)
	- [0. My name is Betty](#0)
	- [1. Who am I](#1)
	- [2. Groups](#2)
	- [3. New owner](#3)
	- [4. Empty!](#4)
	- [5. Execute](#5)
	- [6. Multiple permissions](#6)
	- [7. Everybody!](#7)
	- [8. James Bond](#8)
	- [9. John Doe](#9)
	- [10. Look in the mirror](#10)
	- [11. Directories](#11)
	- [12. More directories](#12)
	- [13. Change group](#13)
	- [14. Owner and group](#14)
	- [15. Symbolic links](#15)
	- [16. If only](#16)
	- [17. Star Wars](#17)
---
## Author Details
- *a41s*

## Project Description
- Allowed editors: `vi`, `vim`, `emacs`
- All your scripts will be tested on Ubuntu 20.04 LTS
- All your scripts should be exactly two lines long (`$ wc -l file` should print 2)
- All your files should end with a new line ([why?](http://unix.stackexchange.com/questions/18743/whats-the-point-in-adding-a-new-line-to-the-end-of-a-file/18789))
- The first line of all your files should be exactly `#!/bin/bash`
- A `README.md` file, at the root of the folder of the project, describing what each script is doing
- You are not allowed to use backticks, `&&`, `||` or `;`
- All your files must be executable

## Tasks
#### 0
###### [Table of Contents](#table-of-contents)
**0. My name is Betty**
- Create a script that switches the current user to the user `betty`.
	- You should use exactly 8 characters for your command (+1 character for the new line)
	- You can assume that the user `betty` will exist when we will run your script
<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ tail -1 0-iam_betty | wc -c
  9
  julien@ubuntu:/tmp/h$
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `0-iam_betty`
---
#### 1
###### [Table of Contents](#table-of-contents)
**1. Who am I**
- Write a script that prints the effective username of the current user.
<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ./1-who_am_i
  julien
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `1-who_am_i`
---
#### 2
###### [Table of Contents](#table-of-contents)
**2. Groups**
- Write a script that prints all the groups the current user is part of.
<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ./2-groups
  julien adm cdrom sudo dip plugdev lpadmin sambashare
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `2-groups`
---
#### 3
###### [Table of Contents](#table-of-contents)
**3. New owner**
- Write a script that changes the owner of the file `hello` to the user `betty`.

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 4
  -rwxrw-r-- 1 julien julien 30 Sep 20 14:23 3-new_owner
  -rw-rw-r-- 1 julien julien  0 Sep 20 14:18 hello
  julien@ubuntu:/tmp/h$ sudo ./3-new_owner 
  julien@ubuntu:/tmp/h$ ls -l
  total 4
  -rwxrw-r-- 1 julien julien 30 Sep 20 14:23 3-new_owner
  -rw-rw-r-- 1 betty  julien  0 Sep 20 14:18 hello
  julien@ubuntu:/tmp/h$
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `3-new_owner`
---
#### 4
###### [Table of Contents](#table-of-contents)
**4. Empty!**
- Write a script that creates an empty file called `hello`.
<br></br>

- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `4-empty`
---
#### 5
###### [Table of Contents](#table-of-contents)
**5. Execute**
- Write a script that adds execute permission to the owner of the file `hello`.
	- The file `hello` will be in the working directory
<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 28 Sep 20 14:26 5-execute
  -rw-rw-r-- 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ ./hello
  bash: ./hello: Permission denied
  julien@ubuntu:/tmp/h$ ./5-execute 
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 28 Sep 20 14:26 5-execute
  -rwxrw-r-- 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `5-execute`
---
#### 6
###### [Table of Contents](#table-of-contents)
**6. Multiple permissions**
- Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file `hello`.    
    - The file `hello` will be in the working directory

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 36 Sep 20 14:31 6-multiple_permissions
  -r--r----- 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ ./6-multiple_permissions 
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 36 Sep 20 14:31 6-multiple_permissions
  -r-xr-xr-- 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `6-multiple_permissions`
---
#### 7
###### [Table of Contents](#table-of-contents)
**7. Everybody!**
- Write a script that adds execution permission to the owner, the group owner and the other users, to the file `hello`
    - The file `hello` will be in the working directory
    - You are not allowed to use commas for this script

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 28 Sep 20 14:35 7-everybody
  -rw-r----- 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ ./7-everybody 
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 28 Sep 20 14:35 7-everybody
  -rwxr-x--x 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `7-everybody`
---
#### 8
###### [Table of Contents](#table-of-contents)
**8. James Bond**
- Write a script that sets the permission to the file `hello` as follows:
    - Owner: no permission at all
    - Group: no permission at all
    - Other users: all the permissions
- The file `hello` will be in the working directory You are not allowed to use commas for this script

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 28 Sep 20 14:40 8-James_Bond
  -rwxr-x--x 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ ./8-James_Bond 
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 28 Sep 20 14:40 8-James_Bond
  -------rwx 1 julien julien 23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `8-James_Bond`
---
#### 9
###### [Table of Contents](#table-of-contents)
**9. John Doe**
- Write a script that sets the mode of the file `hello` to this:
    ```
    -rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
    ```
    - The file `hello` will be in the working directory
    - You are not allowed to use commas for this script

<br></br>
<pre>
  <code>
  -rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `9-John_Doe`
---
#### 10
###### [Table of Contents](#table-of-contents)
**10. Look in the mirror**
- Write a script that sets the mode of the file `hello` the same as `olleh`’s mode.
    - The file `hello` will be in the working directory
    - The file `olleh` will be in the working directory
	- Note: the mode of `olleh` will not always be 664. Make sure your script works for any mode.

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 42 Sep 20 14:45 10-mirror_permissions
  -rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
  -rw-rw-r-- 1 julien julien  0 Sep 20 14:43 olleh
  julien@ubuntu:/tmp/h$ ./10-mirror_permissions 
  julien@ubuntu:/tmp/h$ ls -l
  total 8
  -rwxrw-r-- 1 julien julien 42 Sep 20 14:45 10-mirror_permissions
  -rw-rw-r-- 1 julien julien 23 Sep 20 14:25 hello
  -rw-rw-r-- 1 julien julien  0 Sep 20 14:43 olleh
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `10-mirror_permissions`
---
#### 11
###### [Table of Contents](#table-of-contents)
**11. Directories**
- Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.
- Regular files should not be changed.

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 20
  -rwxrwxr-x 1 julien julien   24 Sep 20 14:53 11-directories_permissions
  drwx------ 2 julien julien 4096 Sep 20 14:49 dir0
  drwx------ 2 julien julien 4096 Sep 20 14:49 dir1
  drwx------ 2 julien julien 4096 Sep 20 14:49 dir2
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ ./11-directories_permissions 
  julien@ubuntu:/tmp/h$ ls -l
  total 20
  -rwxrwxr-x 1 julien julien   24 Sep 20 14:53 11-directories_permissions
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `11-directories_permissions`
---
#### 12
###### [Table of Contents](#table-of-contents)
**12. More directories**
- Create a script that creates a directory called `my_dir` with permissions 751 in the working directory.

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 20
  -rwxrwxr-x 1 julien julien   39 Sep 20 14:59 12-directory_permissions
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ ./12-directory_permission s
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien   39 Sep 20 14:59 12-directory_permissions
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
  drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `12-directory_permissions`
---
#### 13
###### [Table of Contents](#table-of-contents)
**13. Change group**
- Write a script that changes the group owner to `school` for the file `hello`
    - The file `hello` will be in the working directory

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien   34 Sep 20 15:03 13-change_group
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
  drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ sudo ./13-change_group 
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien      34 Sep 20 15:03 13-change_group
  drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir0
  drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir1
  drwx--x--x 2 julien julien    4096 Sep 20 14:49 dir2
  drwxr-x--x 2 julien julien    4096 Sep 20 14:59 my_dir
  -rw-rw-r-- 1 julien school   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `13-change_group`
---
#### 14
###### [Table of Contents](#table-of-contents)
**14. Owner and group**
- Write a script that changes the owner to `vincent` and the group owner to `staff` for all the files and directories in the working directory.

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien   36 Sep 20 15:06 100-change_owner_and_group
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir0
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir1
  drwx--x--x 2 julien julien 4096 Sep 20 14:49 dir2
  drwxr-x--x 2 julien julien 4096 Sep 20 14:59 my_dir
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ sudo ./100-change_owner_and_group 
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 vincent staff   36 Sep 20 15:06 100-change_owner_and_group
  drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir0
  drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir1
  drwx--x--x 2 vincent staff 4096 Sep 20 14:49 dir2
  drwxr-x--x 2 vincent staff 4096 Sep 20 14:59 my_dir
  -rw-rw-r-- 1 vincent staff   23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `100-change_owner_and_group`
---
#### 15
###### [Table of Contents](#table-of-contents)
**15. Symbolic links**
- Write a script that changes the owner and the group owner of `_hello` to `vincent` and `staff` respectively.
    - The file `_hello` is in the working directory
    - The file `_hello` is a symbolic link

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien   44 Sep 20 15:12 101-symbolic_link_permissions
  -rw-rw-r-- 1 julien julien   23 Sep 20 14:25 hello
  lrwxrwxrwx 1 julien julien    5 Sep 20 15:10 _hello -> hello
  julien@ubuntu:/tmp/h$ sudo ./101-symbolic_link_permissions 
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien      44 Sep 20 15:12 101-symbolic_link_permissions
  -rw-rw-r-- 1 julien julien      23 Sep 20 14:25 hello
  lrwxrwxrwx 1 vincent  staff    5 Sep 20 15:10 _hello -> hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `101-symbolic_link_permissions`
---
#### 16
###### [Table of Contents](#table-of-contents)
**16. If only**
- Write a script that changes the owner of the file `hello` to `betty` only if it is owned by the user `guillaume`.
    - The file `hello` will be in the working directory

<br></br>
<pre>
  <code>
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien    julien      47 Sep 20 15:18 102-if_only 
  -rw-rw-r-- 1 guillaume julien      23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ sudo ./102-if_only 
  julien@ubuntu:/tmp/h$ ls -l
  total 24
  -rwxrwxr-x 1 julien julien      47 Sep 20 15:18 102-if_only 
  -rw-rw-r-- 1 betty  julien      23 Sep 20 14:25 hello
  julien@ubuntu:/tmp/h$ 
  </code>
</pre>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `102-if_only`
---
#### 17
###### [Table of Contents](#table-of-contents)
**17. Star Wars**
- Write a script that will play the StarWars IV episode in the terminal.

<br></br>
- Repo
    - GitHub repository: `alx-system_engineering-devops`
    - Directory: `0x01-shell_permissions`
    - File: `103-Star_Wars`
---


<br></br>
<div align="right">
  <sub style="font-style: italic"> Dean Robin Otsyeno - deanrobin777@gmail.com</sub>
</div>
