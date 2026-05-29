# Race Conditions

## Objective
- To comprehend the vulnerability in which two or more actions can happen at the same time and the systems get confused by the repeated action and ended

## What I Learned
- A race condition occurs when multiple processes or requests access shared resources concurrently, causing unintended behavior due to improper synchronization.

## Time of Check To Time Of Use 
- Systems check something but to use it later. In that time, attacker takes something.

## Tools Used
- Web browser
- AttackBox
- Burp Suite

## Steps I Took
- I accessed three bank accounts with all have $100 each inititally, and use one account (A) to transfer a small amount of money to account B.
- I viewed the traffic using Burp Suite and send the successful transaction page to Repeater.
- I put the tab into a group and duplicate it 30 times.
- I sent them all using 'Send using Parallel'.
- I repeat the steps using account B to send to account C.
- Account C ended up with $1400 of money.

## Key Takeaway
- Attackers can abuse this vulnerability for its own benefits such as:
 - Buy items multiple times
 - Double spend credits
 - redeem coupon repeatedly
 - Withdraw money twice
 - Bypass limits
 - Reset password strangely
 - Get duplicate rewards
 - Create multiple accounts

## Reflection
- Developers can prevent race conditions by:
 - 1. Locking - only one request is allowed at one time.
 - 2. Queues - requests are processed one by one.