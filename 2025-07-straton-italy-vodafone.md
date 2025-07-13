## Passive Recon: Exposed STRATON T5 SCADA Device – Vodafone Italia (Rome, Italy)

**Date Identified:** July 13, 2025  
**Disclosure Status:** In progress  
**IP Address:** 91.80.173.228  
**ISP:** Vodafone Italia S.p.A.  
**ASN:** AS30722  
**Location:** Rome, Italy  
**Tools Used:** Shodan (passive ICS query)  
**Focus:** Modbus TCP exposure (STRATON Automation)

---
## Summary

A publicly reachable SCADA endpoint was discovered responding on **Modbus TCP port 502**.  
The device exposes detailed vendor and version information from **STRATON AUTOMATION**, specifically version **T5 14.0.240202**, likely an embedded SCADA runtime.

This response was passively retrieved via Shodan. No direct interaction was performed.

---
## Device Response (via Shodan Modbus Metadata)

Unit ID: 0
→ Device Identification: STRATON AUTOMATION T5 14.0.240202

Unit ID: 1
→ Device Identification: STRATON AUTOMATION T5 14.0.240202

---
## What Is STRATON T5?

- **Vendor:** STRATON AUTOMATION (a COPA-DATA company)  
- **Product:** T5 SCADA/PLC runtime environment  
- **Version:** 14.0.240202 (2024 build)  
- **Purpose:** IEC 61131-3 compliant runtime for OEMs, embedded PLCs, field gateways

These runtimes are often deployed inside physical SCADA edge devices that connect to industrial sensors or actuators.

---
## IP & Ownership

- **IP:** 91.80.173.228  
- **ASN:** AS30722  
- **ISP:** Vodafone Italia S.p.A.  
- **Country:** Italy  
- **City:** Rome

---
## Exposure Risks

| Risk Factor                | Description                                      |
|----------------------------|--------------------------------------------------|
| * Modbus TCP public       | Responds over port 502 from the open internet    |
| * No authentication       | Responds with device info to unsolicited query   |
| * Vendor + version leaked | Full software stack exposed (T5 14.0.240202)     |
| * SCADA/PLC component     | STRATON used in live industrial environments     |
| * No segmentation/firewall| No signs of access control or filtering          |

---
## Ethical Note

This finding was made through **passive reconnaissance only**.  
No exploitation or authentication attempts were performed.  
The goal is to responsibly notify the owner and reduce the surface of internet-exposed ICS systems.

---
## Disclosure Status

Disclosure being prepared for Vodafone Italia S.p.A. as the provider of the network space.  
(Previous disclosures to the same ASN are in progress.)

---

## Analyst Note

This device represents a **modern SCADA software stack** exposed to the public. The presence of a **recent version** (2024) suggests it is actively deployed — possibly in an OEM industrial control gateway or PLC environment.

The exposure is subtle but dangerous, as it provides adversaries with:

- Attack surface intelligence  
- Exact vendor and version mapping  
- Entry points for fuzzing or CVE targeting

> “Sometimes, all it takes is a quiet Modbus handshake to light up a critical asset.”  
> — **OpenIntelHunter**

---
## Tags

`#straton` `#scada` `#modbus` `#vodafone` `#italy` `#rome` `#plc` `#ics` `#exposure` `#responsible-disclosure`
