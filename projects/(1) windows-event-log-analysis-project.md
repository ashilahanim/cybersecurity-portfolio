# Windows Event Log Analysis: Detect Suspicious Login Activity

## Incident Title: Suspicious Login Activity Detected

## Summary:
- At 17th May 2025, multiple login attempts from a same IP address were detected using Event Log on Windows. The first attempt started at 10:53:26PM and followed by failed attempts for 14 times. 

- 14 attempts
![alt text](image-2.png)

## Findings:
![alt text](image-1.png)
- The first attempt with event code of 4625 was originated from the IP address of 10.10.53.248.
![alt text](image.png)
- Upon clicking the 'Details' tab of one of the 4625 event ID code on the last attempt (10:53:30PM) the IP address was  10.10.53.248.
- 14 failed login attempts since 10:53:26PM (Event ID 4625).
- 1 successful login (Event ID 4624) afterward last 14th attempt on 10:53:30PM.
![alt text](image-4.png)
- Source IP: 10.10.53.248
- Time window: Short burst activity (in 4 seconds)

## Assessment:
- Possible brute-force attack

## Recommendation:
- Monitor IP
- Enable the lockout policy of the account
- Further investigate the upcoming activity