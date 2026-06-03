# Penetration Testing Frameworks

## What Is This Room About?
- Frameworks used by pentest team that could improve consistency, compliance, thoroughness and communication. 

## Objective


## What I Learned
- 1. OSSTMM - The Open Source Security Testing Methodology Manual (OSSTMM) aims to change that.
    Developed by the Institute for Security and Open Methodologies (ISECOM), the OSSTMM (currently at version 3) applies the scientific method to security testing. Its defining characteristic is metrics over opinions: rather than delivering subjective risk judgments, OSSTMM produces quantifiable, verifiable, and repeatable results.
    OSSTMM organizes testing around five security channels, reflecting its philosophy that security is not just a network problem: 
    - Human Security (HUMSEC): Social engineering and human-factor vulnerabilities.
    - Physical Security (PHYSSEC): Physical access controls, from badge readers to tailgating.
    - Wireless Communications (SPECSEC): Wi-Fi, Bluetooth, RFID, and other electromagnetic signals.
    - Telecommunications (COMSEC): Phone systems, VoIP, fax, and modem infrastructure.
    - Data Networks (DATASEC): Network services, firewalls, and application-layer protocols.
    An organization might have flawless firewall rules, but if an attacker can tailgate into the server room (PHYSSEC) or social-engineer a credential reset (HUMSEC), those network controls become irrelevant. The five channels ensure nothing is overlooked. At the heart of OSSTMM's quantitative approach are Risk Assessment Values (RAVs). A RAV measures the balance between the total attack surface (exposure) and the controls protecting it. A positive RAV indicates residual risk; a RAV near zero suggests controls are well-matched to exposure. This numeric output means that two testers assessing the same target should arrive at comparable results, much as two engineers measuring the same beam should calculate similar stress tolerances.
    
- 2. OWASP-WSTG - it is a comprehensive, community-driven framework that organizes web application testing into over 90 discrete test cases grouped across twelve categories. Those twelve categories span the full attack surface of a modern web application. They include information gathering, configuration and deployment management, identity management, authentication, authorization, session management, input validation, error handling, cryptography, business logic, client-side testing, and API testing. Each category contains numbered test cases (e.g., WSTG-INPV-01 for reflected cross-site scripting) with step-by-step guidance on what to test and how to test it. The WSTG adopts a risk-based approach: vulnerabilities are prioritized based on their exploitability and impact, not simply cataloged. This approach means the framework helps testers focus their efforts where they matter most.

- 3. National Institute of Standards and Technology-Special Publication-800-115 (NIST-SP-800-115) - a document that provides a foundational framework for systematically evaluating the security posture of information systems. While it originated in the U.S. federal context, its principles are broadly applicable and widely adopted in the private sector, especially by organizations that value structured, repeatable processes.

- 4. Penetration Testing Execution Standard (PTES)

- 5. Information Systems Security Assessment Framework (ISSAF)

- 6. MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK)


## Tools Used


## Steps I Took


## Key Takeaway


## Reflection