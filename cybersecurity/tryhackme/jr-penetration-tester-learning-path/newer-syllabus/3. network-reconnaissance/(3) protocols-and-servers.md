# Protocols and Servers

## What Is This Room About?
- To understand the protocols and servers that are involved across the networks.

## Objective
- To learn multiple protocols used on network using terminal and telnet.

## What I Learned
Telnet (port 23) - remote machine control - worth noting the version of web server software and operating system being used (e.g. Server: nginx/1.18.0 (Ubuntu)) due to:
    - Specific versions may have known vulnerabilities that can be researched.
    - The OS information helps tailor further attacks.
    - Even knowing the web server software narrows down potential attack vectors.

HTTP/HTTPS (Hypertext Transfer Protocol/Hypertext Transfer Protocol Secure)
    - Most common used web servers
        - 1. Nginx has become the most widely used web server on the internet, known for its performance and efficiency in handling concurrent connections. It is free and open-source.
        - 2. Apache remains extremely popular and powers a large portion of websites. It is highly configurable with a vast ecosystem of modules. It is also free and open-source.
        - 3. Internet Information Services (IIS) is Microsoft's web server, commonly found in Windows enterprise environments. It requires a Windows Server licence.
        - 4. LiteSpeed
        - 5. Caddy (which has automatic HTTPS built in)
        - 6. Node.js for JavaScript-based applications.

    - Most common web servers
        - 1. Chrome by Google (dominant market share)
        - 2. Safari by Apple (default on macOS and iOS)
        - 3. Edge by Microsoft (Chromium-based, replaced Internet Explorer)
        - 4. Firefox by Mozilla (open-source, privacy-focused)

FTP/FTPS (File Transfer Protocol Secure/File Transfer Protocol Secure) and SFTP/SSH
    - Ports:
        - FTP: port 21
        - SFTP/SSH: port 22
        - FTPS: port 990

    - Commands in FTP
        - ftp> ls
        - ftp> get FILENAME
        - ftp> exit

SMTP (Simple Mail Transfer Protocol)
    - Simple Mail Transfer Protocol (SMTP) is used to communicate with an MTA server. The original SMTP uses cleartext, where all commands are sent without encryption. However, modern email infrastructure uses several ports with different security models.

    - Email delivery over the Internet requires the following components:
        - 1. Mail User Agent (MUA): The email client (e.g., Thunderbird, Outlook, a webmail interface).
        - 2. Mail Submission Agent (MSA): Receives mail from the MUA, checks for errors, and forwards it.
        - 3. Mail Transfer Agent (MTA): Routes and delivers mail between servers.
        - 4. Mail Delivery Agent (MDA): Stores the email in the recipient's mailbox for retrieval.

    - Email Protocols
        - 1. Simple Mail Transfer Protocol (SMTP) for sending email
        - 2. Post Office Protocol version 3 (POP3) or Internet Message Access Protocol (IMAP) for receiving email

    - SMTP Ports and Encryption
        - Port 25 is the traditional SMTP port used for server-to-server communication (MTA to MTA). It is often blocked by ISPs for residential connections to prevent spam. On port 25, encryption is optional and negotiated via STARTTLS.
        - Port 587 is the submission port, used by email clients (MUA) to submit messages to their mail server (MSA). This is the recommended port for sending email and typically requires authentication. TLS encryption is negotiated via the STARTTLS command.
        - Port 465 was originally designated for SMTPS (SMTP over implicit TLS), then deprecated, and has since been reinstated. On this port, TLS encryption begins immediately upon connection.
    
    Commands
    - helo hostname
    - mail from:
    - rcpt to:
    - data (then write the email)
    - . (to end the email)

POP3 (Post Office Protocol version 3)
    - designed without encryption
    - a protocol used to download email messages from a Mail Delivery Agent (MDA) server. The mail client connects to   the POP3 server, authenticates, downloads the new email messages, and then (optionally) deletes them from the server.
    - POP3 Ports and Encryption:
        - 1. Port 110 is the default POP3 port using cleartext. Some servers support upgrading the connection to TLS using the STLS command (similar to STARTTLS in SMTP).
        - 2. Port 995 is used for POP3S (POP3 over implicit TLS). The connection is encrypted from the start.

    - Commands
        USER username - Identifies the user
        PASS password - Authenticates with the password
        STAT - Returns the number of messages and the total size
        LIST - Lists all messages with their sizes
        RETR n - Retrieves message number n
        DELE n - Marks message n for deletion
        RSET - Resets (unmarks) messages marked for deletion
        QUIT - Ends the session and deletes marked messages

IMAP (Internet Message Access Protocol)

    - IMAP Ports and Encryption
        - Like other email protocols, IMAP was originally designed without encryption:
        - 1. Port 143 is the default IMAP port using cleartext. Many servers support upgrading the connection to TLS using the STARTTLS command.
        - 2. Port 993 is used for IMAPS (IMAP over implicit TLS). The connection is encrypted from the start.
    
    - Command
        LOGIN username password	- Authenticates the user
        LIST "" "*"	- Lists all mailbox folders
        SELECT folder - Opens a folder for read/write access
        EXAMINE folder - Opens a folder for read-only access
        FETCH n BODY[] - Retrieves message number n
        SEARCH criteria - Searches for messages matching criteria
        STORE n +FLAGS (\Seen) - Marks message n as read
        LOGOUT - Ends the session

## Tools Used
- Linux terminal
- Telnet

## Steps I Took


## Key Takeaway
- SMTP -> Server does not verify the senders' emails, email spoofing often happens due to this
- POP3 -> Credentials sent over cleartext POP3 can be captured through network sniffing, password attacks can be conducted against POP3 authentication, and successful access to a mailbox may reveal sensitive information, credentials for other systems, or password reset links.
- IMAP -> Login credentials sent in cleartext, and anyone observing the network traffic would be able to see the username and password. Emails remain on the server thus an attacker with IMAP credentials can continue reading new emails indefinitely. Historical data: The entire mailbox history is accessible, potentially containing years of sensitive communications. Password reset abuse: Attackers can search for password reset emails to gain access to other accounts. Business email compromise: Access to corporate email enables invoice fraud, impersonation, and data theft. Lateral movement: Emails often contain credentials, internal documentation, and information useful for further attacks.

## Reflection