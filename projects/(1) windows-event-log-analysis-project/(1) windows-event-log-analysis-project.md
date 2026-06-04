# Windows Event Log Analysis: Detect Suspicious Login Activity

## Incident Title: Suspicious Login Activity Detected

## Summary:
- At 17th May 2025, multiple login attempts from a same IP address were detected using Event Log on Windows. The first attempt started at 10:53:26PM and followed by failed attempts for 14 times. Investigation of the authentication events identified indicators consistent with a potential brute-force attack. The findings and recommendations are summarized below.
- The evidence of the 14 attempts:
![alt text](image-2.png)

## Findings:
- The figure below showed failed authentication attempts (Event ID 4625) originated from source IP address 10.10.53.248.
![alt text](image-1.png)
- Inspection of the event details for the final Event ID 4625 entry revealed the source IP address 10.10.53.248.
![alt text](image.png)
- 14 failed login attempts since 10:53:26PM (Event ID 4625).
- 1 successful login (Event ID 4624) after the last 14th attempt on 10:53:30PM.
![alt text](image-4.png)
- Source IP: 10.10.53.248
- Time window: Short burst activity (in 4 seconds)

## Assessment:
- The short time interval between the failed authentication attempts (14 attempts within approximately 4 seconds), followed by a successful login from the same source IP address, is consistent with brute-force password guessing activity.

## Recommendation:
- Monitor future authentication attempts from the source IP.
- Review the affected account for suspicious activity.
- Enable account lockout policies to mitigate brute-force attacks.
- Verify whether the successful login was authorized.
- Implement multi-factor authentication (MFA) to reduce the risk of unauthorized account access.