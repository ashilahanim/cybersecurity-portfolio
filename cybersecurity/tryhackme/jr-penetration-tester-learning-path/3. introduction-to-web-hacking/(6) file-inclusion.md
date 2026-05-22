# File Inclusion

## Objective
To understand how file inclusion vulnerabilities allow attackers to gain access on files that are not supposed to be authorized on a web server both internally and externally.

## What I Learned
Web application or web developers sometimes unintentionally failed to validate users input  and includes files in the web server that is not meant for public access. However without proper validation usually on old PHP websites, attackers can access to secret files, execute malicious code by altering the URL or read sensitive files both on the local website (LFI) or in other website (RFI)

## Types of File Inclusion
- Local File Inclusion (LFI) - access file on local server
- Remote File Inclusion (RFI) - access files on other website or outer sources
- Directory transversal - unauthorized access escalate up the path till it meets with the unauthorized directory like /root and can access files like /etc/passwd.

## Tools Used
- Web browser
- TryHackMe AttackBox

## Steps I Took
1. Accessed a web application with a parameter that loads files (e.g., '?page=')
2. Tested different inputs by modifying the parameter value.
3. Attempted diretory transversal using payloads like '../../../../etc/passwd'.
4. Successfully accessed sensitive files on the server.

## Key Takeaway
- Improper input validation can lead attackers to alter the URL to access files that are not supposed to be on open and also can execute malicious code from the URL.

## Reflection
- This vulnerability often appears on old PHP website and on website that is not properly validated. File inclusion vulnerability often trusts user input too much and can let attackers read secret files, see passwords, run malicious code and even take ever website.
