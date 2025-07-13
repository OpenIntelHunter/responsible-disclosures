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
## Case Studies June (2025)

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

- [`2025-07-modbus-open-spain.md`](2025-07-modbus-open-spain.md)  
  → Discovered a live Modbus TCP service (port 502) exposed on Spanish IP `89.29.160.171` (Cableworld). No web interface present. Public exposure of unauthenticated ICS protocol documented for passive recon analysis.

- [`2025-07-schneider-espana-plc.md`](2025-07-schneider-espana-plc.md) (ICS - SCADA)
  → Confirmed internet-facing Schneider Electric Modicon TM221CE24R PLC exposed via Modbus TCP (port 502) on IP `81.47.104.83`. No auth required. Device responds to multiple Unit ID queries. Case flagged as high-value ICS exposure.

- [`2025-07-siemens-espana-plc.md`](2025-07-siemens-espana-plc.md)  (ICS - SCADA)
  → Exposed Siemens SIMATIC S7-300 PLC discovered on IP `80.26.159.23` (Telefónica de España). Device responded to passive protocol queries with full hardware and firmware identification. Disclosure sent July 13, 2025.

- [`2025-07-modbus-italy-telecom.md`](2025-07-modbus-italy-telecom.md) (ICS - SCADA)
  → Passive recon confirmed a live Modbus TCP service on IP `2.197.123.44` (Telecom Italia). Returned “Illegal Function” error on Unit ID 0. No vendor ID, documented for tracking only.

- [`2025-07-schneider-italy-ebx510.md`](2025-07-schneider-italy-ebx510.md) (CRITICAL - ICS - SCADA)
  → Identified a discontinued Schneider Electric EBX510 (Com’X 510) gateway exposed on port 502 in Barletta, Italy. Device responded with firmware and product data. Disclosure to AIRLAN in progress.
  
- [`2025-07-copadata-italy-vodafone.md`](2025-07-copadata-italy-vodafone.md)  
  → COPA-DATA zenon T5 SCADA component exposed over Modbus TCP in Gessate, Italy (Vodafone). Publicly returned vendor and software version. Disclosure in progress.

- [`2025-07-straton-italy-vodafone.md`](2025-07-straton-italy-vodafone.md)  
  → STRATON T5 (v14.0.240202) SCADA runtime exposed over Modbus TCP in Rome, Italy (Vodafone). Passive recon confirmed open device ID leak. Disclosure in progress.






---
## Disclosure Tracking

| Case ID                         | IP Address       | Country     | Target / Vendor                 | Disclosure Sent | Status            | Notes                                                  |
|----------------------------------|------------------|-------------|----------------------------------|------------------|--------------------|---------------------------------------------------------|
| 2025-07-siemens-espana-plc       | 80.26.159.23     | Spain       | Siemens SIMATIC S7-300 PLC       | ✅ 2025-07-13     | ⏳ Awaiting reply  | Publicly accessible industrial PLC (S7)                 |
| 2025-07-schneider-espana-plc     | 81.47.104.83     | Spain       | Schneider Electric TM221CE24R    | ✅ 2025-07-13     | ⏳ Awaiting reply  | Modbus TCP on real PLC, no auth                         |
| 2025-07-zte-costa-rica           | 190.61.83.93     | Costa Rica  | ZTE CPE (ADC668V)                | ✅ 2025-07-12     | 📭 Bounced        | IFX/UFInet Costa Rica, default creds found              |
| 2025-07-checkpoint-costa-rica    | 201.205.119.186  | Costa Rica  | Check Point Firewall             | ❌ Not sent      | 📝 Documented only | No clear vulnerability, logged for research             |
| 2025-07-modbus-open-spain        | 89.29.160.171    | Spain       | Unknown (Modbus open)            | ❌ Not sent      | 📝 Documented only | Passive exposure, unknown operator                      |
| 2025-07-modbus-italy-telecom     | 2.197.123.44     | Italy       | Modbus TCP (unknown vendor)      | ❌ Not sent      | 📝 Documented only | “Illegal Function” response on port 502                 |
| 2025-07-schneider-italy-ebx510 | 185.152.148.247 | Italy | Schneider Electric EBX510 (Com'X) | ❌ Not deliverable | 📭 All contacts bounced | No working email found at AIRLAN. Logged for awareness.
| 2025-07-copadata-italy-vodafone | 91.80.152.4      | Italy       | COPA-DATA zenon T5 SCADA       | ❌ Not sent      | 📝 Documented only | Public Modbus TCP leak of vendor + version metadata |




---

## Ethics & Disclosure

All findings are from **public sources** only.  
I do **not exploit**, modify, or harm any system.  
If login access is encountered (e.g., via default credentials), I document and **exit immediately**, then report it to the owner or ISP.

---

## Contact

Want to collaborate or verify a disclosure?  
Reach out via [GitHub](https://github.com/OpenIntelHunter) or submit an issue in this repo.

