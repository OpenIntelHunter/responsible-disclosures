## Passive Recon: Exposed COPA-DATA SCADA Device – Vodafone Italia (Gessate, Italy)

**Date Identified:** July 13, 2025  
**Disclosure Status:** In progress  
**IP Address:** 91.80.152.4  
**ISP:** Vodafone Italia S.p.A.  
**ASN:** AS30722  
**Location:** Gessate, Italy  
**Tools Used:** Shodan (passive ICS metadata query)  
**Focus:** SCADA / Modbus TCP exposure (COPA-DATA zenon T5)

---
## Summary

A publicly accessible SCADA device was identified responding to Modbus TCP on port 502.  
The device revealed **COPA-DATA France T5 version 9.4.200210** — likely part of the **zenon industrial HMI/SCADA platform** used in energy and process automation systems.

This exposure was confirmed via passive recon using Shodan. No direct interaction with the host was performed.

---

## Device Response (via Shodan Modbus Metadata)

Unit ID: 0
→ Device Identification: COPA-DATA France T5 9.4.200210

Unit ID: 1
→ Device Identification: COPA-DATA France T5 9.4.200210


This indicates that the system is live, reachable over Modbus TCP, and leaking vendor/version data without authentication.

---
## What Is COPA-DATA T5?

- **Vendor:** COPA-DATA (France)  
- **Product Family:** zenon T5  
- **Function:** HMI and SCADA systems for industrial automation  
- **Use Cases:** Power distribution, water treatment, pharmaceuticals, manufacturing

Exposing a SCADA acquisition or control layer to the internet over port 502 creates serious cyber-physical risks.

---
## IP & Ownership

- **IP:** 91.80.152.4  
- **ASN:** AS30722  
- **ISP:** Vodafone Italia S.p.A.  
- **Country:** Italy  
- **City:** Gessate

---

## Exposure Risks

| Risk Element                  | Description                                      |
|------------------------------|--------------------------------------------------|
| * Port 502 open              | Public access to Modbus TCP                      |
| * No authentication          | Responds freely to metadata requests             |
| * Software version exposed   | T5 9.4.200210, helpful for targeted exploitation |
| * Sensitive ICS stack        | zenon platform used in critical infrastructure   |
| * No segmentation/firewall   | Device is publicly reachable via IPv4            |

---

## Ethical Note

This case was discovered through **passive recon only**.  
No queries were sent from my systems; all data comes from public Shodan results.  
No exploitation or interaction occurred.

---
## Disclosure Status

Disclosure is being prepared for Vodafone Italia S.p.A., the AS holder and ISP for the exposed endpoint.

---
## Analyst Note

Exposed SCADA components like this pose a **high risk for targeted attacks**, especially given:

- Unauthenticated protocol exposure  
- Known software version  
- SCADA vendor tied to energy and automation systems

> "The quietest systems on the internet often control the loudest things in real life."  
> — **OpenIntelHunter**

---
## Tags

`#scada` `#modbus` `#copadata` `#zenon` `#italy` `#gessate` `#vodafone` `#ics` `#hmi` `#passive-recon`
