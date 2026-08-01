# Inodes and Links

## Overview

In unix systems, an inode is the metadata of the file.

You can think that in your file explorer or terminal, the files that you see are just a key-value map with the name of the file and the inode number. 


| File explorer | Inode | File data |
| -------- | -------- | -------- |
| File name and inode number    | size, access timestamp, device number, number of hard links  | File content     |


To see inode data use the stat command.

## Links

### Hard links

Hard links are a new entry in the file explorer that point to the inode. There is no "original" file, theese are just two different places where you point to the inode. You can use a different name.

When a file has no links, the OS automatically deletes its inode and content.

To create a hardlink use:

ln <src> <dest>

You can use this command to ls inodes and check that in fact hardlinks have the same inodes:

ls -i <dir>

### Symbolic Links

While hardlinks create different files that point to the same inode, a symbolic link makes a new type of file (symbolic link) that has his own inode and his content points to the original file. 

To see the filename that the links points to, you can use ls -l or readlink command

You can create a symlink with 

l
