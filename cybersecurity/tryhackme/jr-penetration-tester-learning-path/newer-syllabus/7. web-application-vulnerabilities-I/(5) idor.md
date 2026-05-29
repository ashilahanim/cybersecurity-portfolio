# IDOR (Insecure Direct Object Reference)

## Objective
To understand how IDOR vulnerabilities allow unauthorized access to other users' data by manipulating identifiers.

## What I Learned
IDOR occurs when an application does not properly check authorization. This allows a user to access other users' data by modifying an ID parameter.

## Tools Used
- https://www.base64decode.org/
- https://www.base64encode.org/

## Steps I Took
1. Accessed a web application that displays a user's order details.
2. Observed that the URL contained an order ID parameter.
3. Modified the order ID in the URL (e.g., from 1234 to 1000).
4. Successfully accessed another user's order information.

## Key Takeaway
IDOR is an authorization vulnerability where authentication is present, but proper access control is missing.

## Reflection
- There are different types of IDOR:
  - Direct IDOR
  - Indirect IDOR
  - File-based IDOR
- Encoded values such as Base64 or hashed IDs (e.g., MD5) are sometimes used but do not guarantee security.
- IDOR may not always be visible in the URL and can sometimes be found in network requests (e.g., AJAX or JSON responses).