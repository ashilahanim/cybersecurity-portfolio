# Protocols and Servers 2

## What Is This Room About?
- This room is about the attacks involved in the protocols commonly used in network.

## Objective
- To understand the attacks involved in the protocols most common in network.

## What I Learned
- Sniffing 
    - Tools used: 
        - 1. Wireshark
        - 2. Tcpdump
- Man-in-the-Middle (MITM) 
    - An attack that occurs when a victim (A) believes they are communicating with a legitimate destination (B) but is unknowingly communicating with an attacker (E).
    - Techniques:
        - ARP Spoofing is effective on local networks. The attacker sends forged ARP (Address Resolution Protocol) messages to associate their MAC address with the IP address of the default gateway or target system. As a result, traffic intended for those systems is sent to the attacker instead.
        - DNS Spoofing involves providing false DNS responses to redirect victims to attacker-controlled servers. This can happen through compromised DNS servers, DNS cache poisoning, or by responding to DNS queries faster than the legitimate server.
        - Rogue Access Points are fake wireless access points set up by attackers. When victims connect to these networks (often named to look like legitimate networks such as Airport_WiFi_Free), all their traffic flows through the attacker's system.
        - BGP Hijacking operates at the internet routing level, where attackers announce false BGP routes to redirect traffic through their infrastructure. This is a more sophisticated attack, typically targeting specific organisations or regions.

    - Tools used:
        - Bettercap is the modern successor to Ettercap and is actively maintained. It supports ARP spoofing, DNS spoofing, HTTP/HTTPS proxying, and has a modular architecture for various attack scenarios.
        - Ettercap(opens in new tab) is a classic tool for MITM attacks on LANs. While still functional, Bettercap is generally preferred for modern assessments.
        - mitmproxy is an interactive HTTPS proxy that allows inspection and modification of traffic. It is particularly useful for analysing and manipulating HTTP/HTTPS communications.
        - Responder is designed for Windows environments and exploits name resolution protocols such as LLMNR (Link-Local Multicast Name Resolution) and NBT-NS (NetBIOS Name Service). These are fallback protocols that Windows systems use when standard DNS resolution fails. Responder listens for these broadcast queries and responds with its own IP address, tricking victims into sending authentication credentials to the attacker. This is a common technique during internal penetration tests of Active Directory environments.

- Protocol - Default Port / Secured Protocol - Default Port with TLS
    - HTTP - 80 / HTTPS - 443
    - FTP	- 21 / FTPS-990
    - SMTP - 25 / SMTPS - 465
    - POP3 - 110 / POP3S - 995
    - IMAP - 143 / IMAPS - 993
    - DNS - 53 / DNS over TLS (DoT) - 853 / DNS over HTTPS (DoH) - 443

## Steps I Took


## Key Takeaway


## Reflection