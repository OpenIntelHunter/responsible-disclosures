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
  → Reported a publicly exposed ZTE router (ADC668V) on `190.61.83.93` (Ufinet Costa Rica). Login panel was accessible with default credentials.  
  ✅ Disclosure sent to abuse@ifxcorp.com and dparral@ufinet.com — **bounced / no reply**

- [`2025-07-checkpoint-costa-rica.md`](2025-07-checkpoint-costa-rica.md)  
  → Check Point firewall at `201.205.119.186` redirected to a custom port login over HTTPS.  
  ❌ No disclosure sent — **logged for research only**

- [`2025-07-modbus-open-spain.md`](2025-07-modbus-open-spain.md)  
  → IP `89.29.160.171` responds on Modbus TCP port 502, leaks no vendor ID. Unknown operator.  
  ❌ No disclosure sent — **undocumented device**

- [`2025-07-schneider-espana-plc.md`](2025-07-schneider-espana-plc.md)  
  → Schneider TM221CE24R Modbus device exposed at `81.47.104.83` (Madrid, Spain).  
  ✅ Disclosure sent on 2025-07-13 — **awaiting reply**

- [`2025-07-siemens-espana-plc.md`](2025-07-siemens-espana-plc.md)  
  → Siemens S7-300 PLC exposed on `80.26.159.23` (Spain). Passive fingerprint shows full hardware & firmware stack.  
  ✅ Disclosure sent on 2025-07-13 — **awaiting reply**

- [`2025-07-copadata-italy-vodafone.md`](2025-07-copadata-italy-vodafone.md)  
  → COPA-DATA zenon T5 system exposed via Modbus TCP at `91.80.152.4` (Vodafone, Italy).  
  ❌ Disclosure not yet sent — **in progress**

- [`2025-07-schneider-italy-ebx510.md`](2025-07-schneider-italy-ebx510.md)  
  → Com'X 510 (EBX510) SCADA/energy monitor exposed at `185.152.148.247` (AIRLAN, Italy).  
  ❌ All disclosure attempts bounced — **no working contact found**

- [`2025-07-modbus-italy-telecom.md`](2025-07-modbus-italy-telecom.md)  
  → IP `2.197.123.44` responded to Modbus with “Illegal Function”. Device type unknown.  
  ❌ Not reported — **low-confidence finding**

- [`2025-07-straton-italy-vodafone.md`](2025-07-straton-italy-vodafone.md)  
  → STRATON AUTOMATION T5 (v14.0.240202) exposed via Modbus TCP at `91.80.173.228` (Vodafone, Italy).  
  ❌ Disclosure in preparation — **to Vodafone Italia**







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
| 2025-07-straton-italy-vodafone | 91.80.173.228 | Italy | STRATON AUTOMATION T5 (v14.0.240202) | ❌ Not sent | 📝 Disclosure in prep | Public SCADA device exposed via Modbus TCP with full software ID |


---

## Ethics & Disclosure

All findings are from **public sources** only.  
I do **not exploit**, modify, or harm any system.  
If login access is encountered (e.g., via default credentials), I document and **exit immediately**, then report it to the owner or ISP.

---

## Contact

Want to collaborate or verify a disclosure?  
Reach out via [GitHub](https://github.com/OpenIntelHunter) or submit an issue in this repo.

