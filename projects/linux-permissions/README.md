# Linux — File and Directory Permissions

**Context:** Google Cybersecurity Certificate coursework / simulation.  
**Status:** Typed commands based on supplied permissions; expected results only.


## Project description

In this course scenario, a research team needs file and directory permissions to match each person's authorized access. This report explains how to inspect permissions and use chmod to remove access that is not needed. It uses the supplied Current file permissions document and typed commands; the commands and expected results below were not run or captured in the lab for this report.

## Check file and directory details

Start in the researcher's projects directory:
```text
cd /home/researcher2/projects
ls -la
```
The -l option shows detailed information, including permissions, owners, and groups. The -a option includes hidden entries whose names begin with a dot. Based on the supplied document, the permission strings are:
```text
-rw-rw-rw-  project_k.txt
-rw-r-----  project_m.txt
-rw-rw-r--  project_r.txt
-rw-rw-r--  project_t.txt
-rw--w----  .project_x.txt
drwx--x---  drafts
```
These are permission strings reconstructed from the course material, not captured terminal output.

## Describe the permissions string

For project_t.txt, the permission string is -rw-rw-r--. Character 1 is -, which means it is a regular file; d would mean a directory. Characters 2–4 (rw-) describe the owner's permissions, characters 5–7 (rw-) describe the group's permissions, and characters 8–10 (r--) describe permissions for other users. The letters r, w, and x mean read, write, and execute; a dash means that permission is absent. Here, the owner and group can read and write, while others can only read. Nobody has execute permission. For a directory, execute permission allows traversal, or entering/accessing entries by name.

## Change file permissions

project_k.txt gives other users write permission, which the organization does not allow. From the projects directory, use:
```text
chmod o-w project_k.txt
ls -l project_k.txt
```
The o means other users, and -w removes their write permission without changing the owner's or group's permissions. The expected new permission string is -rw-rw-r--. A successful chmod normally prints nothing; the ls command is used to check the result.

## Change file permissions on a hidden file

The hidden file .project_x.txt starts with a dot. Its original permissions are -rw--w----: the owner can read and write, the group can write, and others have no access. The archive should be readable by the owner and group, with no write or execute access:
```text
chmod u=r,g=r,o= .project_x.txt
ls -la .project_x.txt
```
This sets the owner and group to read-only and removes all permissions for others. The expected new permission string is -r--r----. The file being hidden does not itself provide access protection; its permissions control access.

## Change directory permissions

The drafts directory belongs to researcher2 and starts with drwx--x---. The group has execute permission, but only researcher2 should have access. Use:
```text
chmod g-x drafts
ls -ld drafts
```
The command removes the group's execute permission. Since the group has no read or write permission and others already have no permissions, the expected result is drwx------. researcher2 keeps read, write, and execute access. The -d option lists the directory itself rather than its contents. This restricts access through this directory for ordinary users; it does not change ownership or permissions on every file inside it, and privileged administrators can still have access.

## Summary

This report uses ls -la to explain how to check permissions, including hidden files, and chmod to show how to correct access in the supplied scenario. The proposed changes remove other users' write access to project_k.txt, make .project_x.txt read-only for its owner and group, and restrict drafts to researcher2. The expected results follow the course permission list; verifying them in the authorized Linux lab would provide execution evidence.

## Evidence and attribution

Adapted from the Drive document “File permissions in Linux”. Source response text and supplied scenario material may coexist in course templates. This portfolio was organized and edited with AI assistance; it does not claim independent authorship of course materials or production security work. See [source register](../../docs/source-register.md).

[Back to portfolio](../../README.md)
