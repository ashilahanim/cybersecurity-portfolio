# Command Injection

## Objective
- To understand command injection vulnerabilities which happens when a website lets unsanitized user input get includes with the safe system command, allowing attackers to execute malicious commands on the host operating system.

## What I Learned
- By injecting a special ceparators and followed by commands (e.g. whoami command, be it in Windows or in Linux) in a ping tools, DNS lookup tools, file converters, backup systems, admin panels, network diagnostic pages or image processing wrappers, the attackers can gain access to information in the files. 

## Common Separators
1. ;
2. &&
3. ||
4. |
5. &( )
6. ` `

## Tools Used
- Web browser
- Ping tools

## Steps I Took
- I pinged 127.0.0.1
- I put special characters after the IP, 127.0.0.1 ; and use whoami to see who is running the application on the IP address.
- I used command, 127.0.0.1 ; cat /home/tryhackme/flag.txt to view the file and get the flag.

## Key Takeaway
- Attackers can:
 - 1. Read files
 - 2. Run commands
 - 3. Download malware
 - 4. Create users
 - 5. Steal secrets
 - 6. get reverse shell
 - 7. Full server takeover

## Reflection
- Can lead to RCE (Remote Control Execution)
- Common targets
 - 1. Ping tools
 - 2. DNS lookup tools
 - 3. File converters
 - 4. Backup systems
 - 5. Admin panels
 - 6. Network diagnostic pages
 - 7. Image processing wrappers