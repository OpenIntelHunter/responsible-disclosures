## Passive Recon: Exposed Schneider Electric EBX510 Gateway – Barletta, Italy

**Date Identified:** July 13, 2025  
**Disclosure Status:** Disclosure in progress  
**IP Address:** 185.152.148.247  
**ISP:** AIRLAN S.R.L.  
**ASN:** AS203421  
**Location:** Barletta, Italy  
**Tools Used:** Shodan + passive Modbus inspection  
**Focus:** Critical ICS infrastructure – energy management gateway

---
## Summary

A publicly accessible **Schneider Electric Com'X 510 (EBX510)** energy server was discovered exposed to the internet via Modbus TCP. The device responded to passive queries on **Unit ID 255** and **Unit ID 1**, confirming its identity, model, and firmware.

This device has been **discontinued and is past its end-of-service date**, making it highly vulnerable if left unpatched or exposed.

---
## Device Fingerprint (Modbus TCP)

Unit ID: 1
→ Schneider Electric (EAN13)3303430596806 V8.07

Unit ID: 255
→ Schneider Electric EBX510 6.0.4

---

## 📦 Device Overview

- **Device:** Schneider Electric Com'X 510 (a.k.a. EBX510)  
- **Function:** Edge gateway for industrial energy monitoring  
- **Discontinued:** September 16, 2022  
- **End-of-Service:** March 30, 2024  
- **Firmware (found):** 6.0.4  

The Com’X 510 is typically installed in **factories, substations, or commercial buildings**, and connects to circuit breakers, meters, and building control systems.

---
## IP & Ownership

- **IP:** 185.152.148.247  
- **Hostname:** N/A  
- **ASN:** AS203421  
- **ISP:** AIRLAN S.R.L.  
- **Country:** Italy  
- **City:** Barletta

---
## Exposure Risks

| Risk Element                     | Description                                           |
|----------------------------------|-------------------------------------------------------|
| 🔓 Open port 502 (Modbus TCP)    | ICS protocol directly reachable from the internet    |
| 🧾 Device metadata exposed       | Firmware, serial, and model info fully available     |
| ❌ No authentication             | Responds to public queries without challenge         |
| 📅 Unsupported hardware          | End-of-life and no more security patches             |
| 🎯 Likely operational device     | Unit IDs 1 and 255 confirm production deployment     |

This setup creates a **high-value target for attackers** and represents a typical **edge-layer exposure** — common in power, automation, and energy management networks.

---
## Ethical Note

All data was gathered using **public tools** and **non-invasive methods**:
- No login, write, or configuration attempts  
- Only metadata responses from passive Modbus handshake  
- Goal is educational, not exploitative

---
## Disclosure Status

An email is being prepared for **AIRLAN S.R.L.** with details of the exposure, including technical metadata and risk assessment.

### Disclosure Update
All attempted disclosures to AIRLAN S.R.L. (abuse@, support@, info@, etc.) between July 13–14, 2025 failed due to undeliverable addresses. This case is retained in public logs for visibility and long-term risk awareness.


---
## Analyst Note

This is one of the most significant ICS exposures in this recon project so far, due to:

- Device obsolescence  
- Vendor reputation (Schneider)  
- Protocol (Modbus)  
- No firewall or segmentation  
- Metadata leakage

> *“Old gateways don’t die — they wait for ransomware.”*  
> — **OpenIntelHunter**

---
## Tags

`#ics` `#modbus` `#schneider` `#ebx510` `#comx510` `#italy` `#barletta` `#passive-recon` `#openintelhunter`
