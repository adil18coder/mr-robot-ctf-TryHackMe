# Privilege Escalation to Root

After obtaining access as the **robot** user, further privilege escalation was required to obtain root access and capture the final key.

## SUID Enumeration

The first step was to search for files with the **SUID permission** set.

Command used:

find / -perm -4000 2>/dev/null

This command searches the entire filesystem for binaries that run with elevated privileges.

During this enumeration, an interesting binary was discovered:

nmap

Since Nmap had the **SUID bit set**, it meant that it could potentially be used to execute commands with elevated privileges.

## Exploiting Nmap Interactive Mode

Older versions of **:contentReference[oaicite:0]{index=0}** allow interactive mode, which can be abused to spawn a shell.

Command used:

nmap --interactive

Inside the interactive Nmap prompt, a shell was spawned using:

!sh

This resulted in a shell running with elevated privileges.

## Root Access

After obtaining the shell, the root directory was accessed.

Commands used:

cd /root
ls

The file containing the final key was located.

Command used to read the flag:

cat key-3-of-3.txt

Status:

Key 3 – Captured
