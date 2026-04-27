# Introduction of SSFR (Server-Side Request Forgery)

## Objective
To understand how SSRF vulnerabilities allow attackers to make requests from a server to gain access to internal or external resources.

## What I Learned
SSFR is a vulnerability in which the server is tricked by attacker to do unintended services for the attacker by requesting for internal or external resources.

## Tools Used
- Web browser
- URL

## Steps I Took
1. I interacted with a web browser that accepts URL input.
2. I learned different web URLs and their respective server behaviours.
3. I attempted to access the internal resources by altering the URL by inputing '&x='.
4. The server made requests on my behalf and the server returned the response.

## Key Takeaway
SSRF is different with FI as it tricks the server to actually do something for attacker without getting into the server by its own. However FI attackers can gain access and potentially overrule the website itself.

## Reflection
- Always validate and restrict user input
- SSRF can be highly damaging to cloud data (or metadata)
- User-controlled inputs should not expose internal resources