# Passive Recon: Check Point Security Gateway Exposed – Costa Rica

**Date Identified:** July 13, 2025  
**Disclosure Status:** Not reported — informational exposure  
**IP Address:** 201.205.119.186  
**Tools Used:** Shodan, curl, OpenSSL, masscan  
**Purpose:** Exposure hygiene awareness

---

## Summary

During passive reconnaissance of login interfaces exposed in Costa Rica (`http.title:"Login" country:"CR"`), I discovered a publicly accessible web portal on port `80` that redirects to a **Check Point Security Gateway** on port `4434`.

The device uses a **self-signed certificate**, with default internal naming (`my.firewall_7FADAD68_e432af98f3`), and does not present custom branding or protection headers.

While no vulnerability or unauthorized access was attempted, this exposure may pose a **soft risk** due to poor configuration hygiene and external accessibility.

---

## Technical Findings


### HTTP Headers (Port 80):

HTTP/1.1 301 Moved Permanently
Location: https://201.205.119.186:4434
Server: Check Point SVN foundation


### SSL Certificate (Port 4434):
```plaintext
Subject: CN=my.firewall_7FADAD68_e432af98f3
OU=Check Point Security Gateway
O=Check Point
C=US

Issuer: Self-signed
Valid: 2021–2031

Redirect Behavior:

    HTTP on port 80 → redirects to HTTPS 4434
	SSL served on 4434 instead of standard port 443


## Whois / IP Info

    IP: 201.205.119.186

    ASN: AS11830

    ISP: Instituto Costarricense de Electricidad (ICE)

    Country: Costa Rica

## Analysis

Although the device is not immediately exploitable:

    It exposes a sensitive remote access interface to the internet
    Uses a self-signed SSL cert with default naming
    Lacks clear hardening or obfuscation measures
    May be brute-forceable if login exists behind it

This represents a risk of targeting by automated scanners, phishing toolkits, or brute-force attempts.

## Ethical Note

This is a passive reconnaissance case.
No login, brute force, vulnerability scan, or intrusion was attempted.
This report is intended for educational purposes and infrastructure awareness only.


##Researcher Note

This case was part of an ongoing project exploring exposed infrastructure in Latin America.
By documenting common device exposures, I aim to raise awareness about internet-facing attack surfaces.

    "Sometimes, visibility is the vulnerability."
    — OpenIntelHunter

##Tags

#osint #checkpoint #recon #costa-rica #exposure #responsible-disclosure #ethical-analysis
