# Ethical Hacking & Penetration Testing – Red Team Simulation

## Overview
This research project presents a complete red-team operation targeting DHL, with a focus on simulating **real-world social engineering attacks, payload delivery and post-exploitation scenarios**. The goal was to design, stage and test a spear phishing campaign against DHL employees using **cloned login portals, fake Microsoft authentication flows, and targeted payloads**. No actual deployment occurred: all activity was conducted in a **controlled lab environment** for academic purposes.

The highlight of this project is the development of a **PowerShell-based attack chain** capable of **capturing webcam snapshots** from the victim's machine while **bypassing Windows Defender and Kaspersky**, showcasing the limitations of traditional antivirus systems.

## Project Highlights

### Target Recon & OSINT (Ch. 2–3)
- Mapped DHL internal and employee login portals through deep search and subdomain enumeration.
- Gathered hundreds of emails using tools like **theHarvester**, **Hunter.io**, **LeakRadar**, and **Expired Domains**.
- Showcased ways to spoof or buy expired domains (e.g., `phishing-dpdhl@dhl.com`, `support@verificationdhl.com`) to gain credibility.

### Credential Harvesting (Ch. 4–5)
- Cloned DHL’s Microsoft SSO login portal using **SET, Zphisher, BlackEye**, and **custom HTML/CSS templates**.
- Created **HTML-phishing emails** mimicking official DHL correspondence (SSO expiry, login alerts, compliance reviews).
- Hosted cloned pages on **Ngrok**, masked using **MaskPhish** to create realistic links.

### Campaign Simulation with GoPhish (Ch. 6)
- Designed and configured a complete phishing campaign using **GoPhish**, including:
- Email templates with spoofed headers
- Landing pages with credential logging
- SMTP profiles and fake Microsoft domains

### Payload Engineering & Obfuscation (Ch. 7–10)
- Created **reverse HTTPS Meterpreter payloads** using **Veil-Evasion**, **msfvenom** and **Metasploit**.
- Packaged payloads into `.exe` and `.msi` files (e.g., `WindowsSecurityUpdate.exe`) with:
- **Fake Microsoft code signing**
- **Custom metadata spoofing**
- **Resource Hacker-based icon replacement**

- Delivered payloads via:
- **Phishing emails with Bit.ly links**
- **BadUSB (Rubber Ducky script)**
- **Bettercap MITM JavaScript injection**

### Final Stage – Stealthy PowerShell Webcam Exploit (Ch. 12)
- Designed and executed a **zero-file PowerShell reverse shell** using only native Windows commands.
- Captured webcam snapshot and exfiltrated it from a target system **without detection by Windows Defender or Kaspersky**.
- No administrative privileges, no external binaries used — **pure native obfuscation + socket redirection**.
- The payload was manually obfuscated using native PowerShell constructs, inspired by the methods presented in the [PowerShell Obfuscation Bible by t3l3machus](https://github.com/t3l3machus/PowerShell-Obfuscation-Bible).

## Key Tools Used
- `theHarvester`, `Hunter.io`, `Social-Engineer Toolkit`, `Zphisher`, `Ngrok`, `Bettercap`, `GoPhish`, `Veil-Evasion`, `Metasploit`, `msfvenom`
- `openssl`, `osslsigncode`, `encoder.jar`, `Ngrok`, `Resource Hacker`, `PowerShell`, `Revshells.com`

## Legal Disclaimer
This project was conducted in a **controlled lab environment** on self-owned systems for **educational purposes only**. It does not promote or support unauthorized access, data theft, or cybercrime. All techniques were executed with full legal and ethical compliance.

## Contact
- **LinkedIn**: [Konstantinos Zafeiropoulos](https://www.linkedin.com/in/konstantinos-zafeiropoulos/)
- **Email**: ice20390293@uniwa.gr
