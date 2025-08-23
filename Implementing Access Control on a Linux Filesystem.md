# Linux Filesystem Access Control (DAC)

Access control is one of the fundamental pillars of information security, ensuring that only authorized users can access specific resources while preventing unauthorized access.
In operating systems, particularly Linux, access control mechanisms are built into the file system and are enforced through users, groups, and permissions.

This project demonstrates how Discretionary Access Control (DAC) can be implemented on a Linux system by creating users, groups, and files, then assigning permissions to enforce different levels of access.

## Overview
The project will essentially go this way, we'll create a directory with a few sub directories that willl serve as our sandbox so no other directory is affected in the process, then we'll create multiple users/groups so the permissions can tested and applied uniquely. Finally we'll create ACLs(Access control lists) which will let us practice fine-grained permission management

### Step 1: Create the test directory
As stated earlier we'll be creating a sandbox environment where we can practice different types of access control methods without affecting the rest of the system.
on to creating the test directory, below is how the folders will be structured
```bash
HABOtech/
├── projects/
│   ├── finance/
│   │   ├── budget.txt
│   │   └── payroll.txt
│   ├── engineering/
│   │   ├── design.docx
│   │   └── prototype.txt
│   └── hr/
│       ├── employees.txt
│       └── contracts.docx
└── shared/
    ├── announcements.txt
    └── policies.txt
```

### Step 2: Creating users and groups
The next step is to create groups for each of the comapanies departments(Hr, Engineering and finance) and then create users who will be assigned to various groups for shared access

#### Create a group
Using the command below we'll be creating groups for the Hr, finance and engineering departments
```bash
sudo groupadd engineering
sudo groupadd finance
sudo groupadd hr
```
we can confirm the groups were created using `cat /etc/group`

#### Creating Users
Using the command below we can create users and add them to anyone of the three groups we previously created
```bash
sudo useradd -m -s /bin/bash -g department account_name
sudo passwd acount_name
```
using the command above we can create accounts and assign them to different groups

| Username | Group       |  Notes        |
|----------|------------|-------------------|
| max      | engineering | Engineer           |
| michael  | engineering | Engineer           |
| charles  | hr          | HR personnel       |
| daniel   | finance     | Accountant         |
| lewis    | finance     | Accountant         |

To confirm the users have been successfully created and are in their respective groups, we can run `id account_name`
