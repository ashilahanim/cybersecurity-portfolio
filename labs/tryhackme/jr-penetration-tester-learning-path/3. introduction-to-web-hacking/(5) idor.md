# IDOR (Insecure Direct Object Reference)

## Objective
To learn about a vulnerability that involves changing the ID perimeter to access others information. 

## What I Learned
Someone can access others' data just by changing the an ID.

## Tools Used
- https://www.base64decode.org/
- https://www.base64encode.org/

## Command(s) Used (If Any)

## Steps I Took
1. I opened a site that lists out emails of a user.
2. This user has placed an order from an online shop.
3. i clicked the link to the order confirmation site and alter the URL by tweaking the order ID from 1234 to 1000.
4. Another user's order from the same shop can be clearly seen.

## Key Takeaway
IDOR is a vulnerability involving a failed authorization but passes authentication

## Reflection
- Three types of IDOR; a. Direct IDOR, b. Indirect IDOR and c. File-based IDOR
- Hashed MD5 and base64 are most common
- Not necessarily in the address bar, sometimes have to inspect the web page on the Network section to find out the AJAZ request or the JSON ID