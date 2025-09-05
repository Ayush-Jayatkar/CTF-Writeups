\# Pickle Rick CTF - Writeup



\## Overview



This CTF is based on a Rick and Morty themed vulnerable machine. The

main goal was to find all ingredients Rick needs to make his potion and

return to human form.



\## Objectives

Access the web application.

Retrieve sensitive files from the server.



------------------------------------------------------------------------



\## Steps \& Enumeration



\### 1. Initial Scanning



\-   Used \*\*nmap\*\* to scan open ports and services.

\-   Found ports: `80 (HTTP)`, `22 (SSH)`.



\### 2. Web Enumeration

\-   Navigate to the provided IP address: http://10.201.xx.xx.

\-   Use the username R1ckRul3s and password Wubbalubbadubdub to log in.

\-   Checked the website on port 80, saw a simple Rick and Morty page.

\-   Used \*\*dirb/gobuster\*\* for directory enumeration.

\-   Found hidden paths like `/robots.txt`, `/login.php`, and

&nbsp;   `/portal.php`.



\### 3. Login Page



\-   Discovered credentials on the site (Rick's hints).

\-   Logged in with username `R1ckRul3s` and password `Wubbalubbadubdub`.



\### 4. Command Panel



\-   Portal page allowed limited command execution.

\-   Tested commands: `ls`, `pwd`, `cat`, `less`.

\-   Found first ingredient flag: \*\*mr. meeseek hair\*\*.



\### 5. Privilege Escalation



\-   Explored files and directories.

\-   Found second ingredient in `/home/rick/second\_ingredient`.

\-   Used `sudo -l` to see available commands.

\-   Rick had `sudo` rights to run `vi` as root.



\### 6. Exploitation



\-   Gained root privileges.

\-   Found final ingredient in `/root/3rd\_ingredient`.



------------------------------------------------------------------------



\## Ingredients (Flags)



1\.  \*\*mr. meeseek hair\*\*

2\.  \*\*1 jerry tear\*\*

3\.  \*\*fleeb juice\*\*



------------------------------------------------------------------------



\## Conclusion



We helped Rick turn back from a pickle by hacking into his system and finding the secret ingredients. Lesson learned: always check your robots.txt, respect your sudo powers, and never underestimate a pickle! 🥒✨

