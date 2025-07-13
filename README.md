# responsible-disclosures
Passive internet recon and responsible disclosure reports. Focused on OSINT, exposed infrastructure, and ethical analysis.

# Responsible Disclosures by OpenIntelHunter

This repository contains my passive reconnaissance and responsible disclosure reports.

As **OpenIntelHunter**, I focus on identifying misconfigured or exposed internet-facing systems — particularly in Latin America — using **public tools** and **ethical methods** such as:

- Shodan
- Nmap / Masscan
- cURL / OpenSSL / WHOIS
- SSL certificate analysis
- ASN and IP ownership mapping

---

## Purpose

This project is about **learning**, **exposure awareness**, and **responsible security research**. I document these discoveries as part of my growth in cybersecurity and OSINT, while respecting legal and ethical boundaries.

---

## Case Studies ## (2025)

- [`2025-07-zte-costa-rica.md`](2025-07-zte-costa-rica.md)  
  → Reported a publicly exposed ZTE router (model likely ADC668V) on IP `190.61.83.93` belonging to Ufinet Costa Rica. Passive recon confirmed an open login interface over HTTP/HTTPS. Disclosure sent to abuse@ifxcorp.com and dparral@ufinet.com on July 12, 2025.

- [`2025-07-checkpoint-costa-rica.md`](2025-07-checkpoint-costa-rica.md)  
  → Discovered a Check Point Security Gateway at IP `201.205.119.186`, publicly exposed on HTTP port 80 with redirect to HTTPS `4434`. The gateway served a self-signed SSL certificate with default internal CN (`my.firewall_7FADAD68_e432af98f3`). No vulnerabilities found; case documented for exposure awareness. Not reported.

- [`2025-07-cpanel-racknation.md`](2025-07-cpanel-racknation.md)  
  → Identified a CPanel login interface on `ns.unidosxm.com` (Racknation Costa Rica), served over HTTPS with a valid Let's Encrypt certificate. No issues detected; documented for infrastructure mapping.

- [`2025-07-ice-lenovo-exposure.md`](2025-07-ice-lenovo-exposure.md)  
  → Identified a legacy web service running on ICE’s IP `201.205.227.26` with self-signed Lenovo SSL cert (`bjasljsgs`) and PHP 5.6.37. No login attempted; documented for awareness and legacy exposure tracking.

- [`2025-07-ice-auth-test-header.md`](2025-07-ice-auth-test-header.md)  
  → Detected unusual `Authentication: test` HTTP header on ICE IP `201.204.177.219`, returned from a GeoHttpServer running over HTTP/1.0. Documented for awareness of staging or dev-system leakage.



---

## Ethics & Disclosure

All findings are from **public sources** only.  
I do **not exploit**, modify, or harm any system.  
If login access is encountered (e.g., via default credentials), I document and **exit immediately**, then report it to the owner or ISP.

---

## Contact

Want to collaborate or verify a disclosure?  
Reach out via [GitHub](https://github.com/OpenIntelHunter) or submit an issue in this repo.

