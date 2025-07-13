## Passive Recon: Modbus Device Exposure – Telecom Italia Mobile (Vigevano, Italy)

**Date Identified:** July 13, 2025  
**Disclosure Status:** Not reported (minimal exposure, low severity)  
**IP Address:** 2.197.123.44  
**ISP:** Telecom Italia Mobile  
**ASN:** AS6762  
**Location:** Vigevano, Italy  
**Tools Used:** Shodan + passive Modbus inspection  
**Focus:** ICS recon – Modbus handshake confirmation

---
## Summary

A publicly reachable Modbus TCP endpoint was identified in Italy responding to basic Modbus function queries on **port 502**. Though the response was limited, it confirms the presence of an **ICS-related service accessible from the public internet**.

---
## Device Response (Passive Modbus)

Unit ID: 0
→ Slave ID Data: Illegal Function (Error)


This means the device is alive and reachable over Modbus, but rejected the specific query — likely due to disabled function codes or limited visibility. Still, **no firewall or segmentation is blocking access.**

---
## IP & Ownership

- **IP:** 2.197.123.44  
- **ASN:** AS6762  
- **ISP:** Telecom Italia Mobile  
- **Country:** Italy  
- **City:** Vigevano

---
## Exposure Notes

While this case does not reveal specific vendor or hardware information, it is still notable for the following reasons:

- Open Modbus TCP port (502)  
- Protocol response received (non-random)  
- Public internet-facing ICS protocol  
- No authentication, segmentation, or gateway visible

---
## Ethical Note

This interaction was passive and non-invasive:
- Only standard Modbus metadata was queried (via Shodan)  
- No commands, write operations, or probes were issued  
- The goal is awareness, not exploitation

---
## Analyst Note

This case is documented for recon tracking purposes. Should future scans show expanded functionality (e.g., Unit IDs responding with device info), it may warrant reclassification or disclosure.

> "Even quiet Modbus nodes are loud on the internet."  
> — **OpenIntelHunter**

---

## Tags

`#modbus` `#italy` `#ics` `#passive-recon` `#telecomitalia` `#vigevano` `#port502`
