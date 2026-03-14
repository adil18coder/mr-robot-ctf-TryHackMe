# Nmap Scan

The first step was performing a network scan to discover open ports and services.

Command used:

nmap -sC -sV -T4 <TARGET-IP>

Results showed:

Port 80 – HTTP Web Server

Since only a web service was exposed, the attack surface was focused on the web application.
