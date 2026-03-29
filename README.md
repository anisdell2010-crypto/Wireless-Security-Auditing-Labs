🛡️ Wireless-Security-Auditing-Labs
Practical demonstration of Wi-Fi penetration testing and network hardening techniques 🛡️

Network Security Analysis:
Wi-Fi Penetration Testing & Defense Simulation

Author:
r4ouf_s(Abderaouf)

Credentials:

ISC2 Candidate

IBM Cybersecurity Fundamentals Certifi

CISCO introduction Introduction to Cybersecurity:

To verify:
https://www.credly.com/badges/20f257e0-af1c-4ff4-8cb4-f2443229b77d/public_url
https://www.credly.com/badges/e80a886c-352e-4c89-9374-f1c222fab989/public_url
https://www.credly.com/badges/287b2ee6-cff8-4d87-ad7c-c494ad518ccf/public_url

⚠️ LEGAL & ETHICAL DISCLAIMER
Educational Purposes Only:
This project and its documentation are created strictly for educational purposes and security research.

Authorized Testing Only:
The techniques demonstrated here must only be performed on networks and devices that you own or have explicit, written permission to test.

No Liability:
The author (Abdraouf Sendid) is not responsible for any misuse of this information or any damage caused by its application.

Legal Warning:
Unauthorized access to computer systems or networks is illegal and punishable by law. Always act ethically and stay within legal boundaries.


Phase 1: Environment Preparation
<img width="634" height="410" alt="image" src="https://github.com/user-attachments/assets/0e6ff83b-064f-44d9-baac-cef368e65860" />

The wireless interface is transitioned from Managed to Monitor Mode to allow packet injection and sniffing.
Tool Used: airmon-ng and airodump-ng.
Command: sudo airodump-ng wlan0 to begin scanning the 802.11 spectrum.

Phase 2: Target Reconnaissance
(<img width="772" height="530" alt="image" src="https://github.com/user-attachments/assets/c6a30aaa-3740-43d3-adc0-5083d6409d64" />

Using airodump-ng, I identified target networks and analyzed their parameters:

BSSID: MAC Address of the Access Point.

Channel (CH): The specific frequency channel for targeted sniffing.

Encryption (ENC): Identifying WPA2-CCMP vulnerability points.
<img width="637" height="373" alt="image" src="https://github.com/user-attachments/assets/6ce85497-1dea-4ea5-9319-39b167282450" />

2️⃣ Attack Execution (Step-by-Step)
Passive Monitoring: Locking onto the target BSSID and channel to capture data frames.
Deauthentication Attack: Utilizing aireplay-ng to broadcast deauth packets, forcing a client to disconnect from the target AP.
Handshake Capture: Monitoring for the re-association request to capture the WPA Handshake.
Offline Cracking: Using aircrack-ng to match the captured hash against a high-entropy wordlist to recover the PSK (Pre-Shared Key).

3️⃣ Indicators of Compromise (IoC)
How to detect if your network is under a similar attack:

Frequent Disconnections: Unexpected "Wi-Fi Drops" caused by continuous deauthentication frames.

Network Instability: Sudden degradation in signal quality and internet speed.

Rogue Access Points: Appearance of an identical SSID (Evil Twin) with no encryption.

4️⃣ Defensive Mitigations (Hardening)
To secure the network against these vulnerabilities, the following measures are implemented:

Upgrade to WPA3: Leveraging SAE (Simultaneous Authentication of Equals) to prevent offline dictionary attacks.

Enable PMF: Activating Protected Management Frames to stop unauthorized deauthentication packets.

Strong Passphrase Policy: Using complex passwords with a mix of symbols and high entropy...

Change Default Gateway Credentials: Updated the router's administrative password from the factory default to a strong, unique passphrase to prevent unauthorized configuration changes.
