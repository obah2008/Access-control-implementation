# Linux Filesystem Access Control (DAC)

Access control is one of the fundamental pillars of information security, ensuring that only authorized users can access specific resources while preventing unauthorized access.
In operating systems, particularly Linux, access control mechanisms are built into the file system and are enforced through users, groups, and permissions.

This project demonstrates how Discretionary Access Control (DAC) can be implemented on a Linux system by creating users, groups, and files, then assigning permissions to enforce different levels of access.

## Overview
The project will essentially go this way, we'll create a directory with a few sub directories that willl serve as our sandbox so no other directory is affected in the process, then we'll create multiple users/groups so the permissions can tested and applied uniquely. Finally we'll create ACLs(Access control lists) which will let us practice fine-grained permission management

Step 1: Create the test directory
As stated earlier we'll be creating a sandbox environment where we can practice different types of access control methods without affecting the rest of the system.
on to creating the test directory, below is how the folders will be structured
