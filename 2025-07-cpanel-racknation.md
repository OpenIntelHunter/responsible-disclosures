# Passive Recon: CPanel Login Interface on Racknation Network – Costa Rica

**Date Identified:** July 13, 2025  
**Disclosure Status:** Not reported — expected public access  
**IP Address:** 143.202.161.80  
**Domain:** ns.unidosxm.com  
**Tools Used:** Shodan, curl, OpenSSL, whois  
**Purpose:** Infrastructure mapping and exposure documentation

---
## Summary

During passive reconnaissance of login interfaces in Costa Rica, I identified a **CPanel login interface** hosted on the domain `ns.unidosxm.com`, associated with the IP `143.202.161.80` and the Racknation S.A. network.

The panel is served over HTTPS with a valid domain-matching certificate from Let's Encrypt. This is a **standard and expected configuration**, but documented here as part of public-facing infrastructure mapping.

---
## Technical Findings

### HTTP Response (Port 2083 - HTTPS CPanel):
```http
HTTP/1.1 200 OK
Connection: close
Content-Type: text/html; charset="utf-8"
Date: Sun, 13 Jul 2025 03:45:09 GMT
Cache-Control: no-cache, no-store, must-revalidate, private
Pragma: no-cache
Set-Cookie: cprelogin=no; HttpOnly; expires=Thu, 01-Jan-1970 00:00:01 GMT; path=/; port=2083; secure

## SSL Certificate

Subject: Common Name = ns.unidosxm.com
Issuer:  Let's Encrypt / R10
Valid TLS Version: TLSv1.2
Certificate Status: Valid, domain-matched, not self-signed

## IP Ownership

IP Address: 143.202.161.80
ASN: AS266699
ISP/Host: Racknation S.A.
Country: Costa Rica
Region: San José
Domain: ns.unidosxm.com

## Observations

    Login interface served on standard CPanel HTTPS port (likely 2083)
    Proper SSL deployment using Let's Encrypt with domain match
    No default certificate, internal IP leakage, or headers of concern
    Panel appears hardened and configured correctly

## Ethical Note

    This is a passive reconnaissance entry:
    No login attempts were made
    No brute-force, scanning, or tampering occurred
    No vulnerabilities are alleged or implied
    This case is documented purely for educational and OSINT infrastructure analysis.

## Researcher Note

    This case helps build familiarity with typical infrastructure layouts in Latin America, especially in web hosting environments. While not vulnerable or misconfigured, such entries build a picture of attack surfaces, host hygiene, and vendor behavior.
    Document the normal to recognize the abnormal.
    — OpenIntelHunter

## Tags

#cpanel #racknation #osint #exposure-mapping #costa-rica #infrastructure
