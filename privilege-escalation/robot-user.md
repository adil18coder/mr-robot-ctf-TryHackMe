# Privilege Escalation

After gaining shell access to the target system, further enumeration of the filesystem was performed.

## Exploring the Home Directory

Command used:

cd /home
ls

Inside the home directory a user named **robot** was discovered.

## Password Hash Discovery

Inside the robot user's directory a file containing a password hash was found.

The hash appeared to be an **MD5 hash**.

This hash was decoded using an online hash cracking tool.

After decoding the hash, the plaintext password for the robot user was obtained.

## Switching User

The credentials were then used to switch to the robot user.

Command used:

su robot

After entering the decoded password, access to the robot user account was obtained.

## Key 2 Discovery

After switching to the robot user, the directory contents were listed.

Command used:

ls

The file containing the second key was located.

Command used to read the flag:

cat key-2-of-3.txt

Status:

Key 2 – Captured
