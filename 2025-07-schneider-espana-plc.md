# Passive Recon: Exposed Schneider Electric Modicon PLC – Madrid, Spain

**Date Identified:** July 13, 2025  
**Disclosure Status:** Under consideration (high-value ICS exposure)  
**IP Address:** 81.47.104.83  
**Hostname:** 83.red-81-47-104.staticip.rima-tde.net  
**ISP:** Telefónica de España S.A.U.  
**ASN:** AS3352  
**Location:** Madrid, Spain  
**Tools Used:** Shodan (Modbus), passive protocol enumeration  
**Focus:** Critical infrastructure exposure (ICS/SCADA)

---

## 🧭 Summary

This case documents a **publicly exposed industrial PLC** identified as:

Vendor: Schneider Electric
Model: TM221CE24R
Version: V1.0

### Issue:


The device is **directly reachable over the internet via port 502 (Modbus TCP)** with **no authentication**, and responds to **Modbus Device Identification queries**. This is an industrial-grade device typically used in **manufacturing, building automation, energy**, or **utilities**.
The IP address is owned by **Telefónica de España**, indicating this PLC may be operating in a live facility connected via a major national ISP.

---

## 🔍 Device Response (Passive Modbus ID)

Unit ID: 0
→ Schneider Electric TM221CE24R V1.0

Unit ID: 1
→ Schneider Electric TM221CE24R V1.0

Unit ID: 255
→ Schneider Electric TM221CE24R V1.0

***** All units returned clear manufacturer identification — no credentials required.*****
---

## IP & Ownership

- **IP:** 81.47.104.83  
- **Hostname:** 83.red-81-47-104.staticip.rima-tde.net  
- **ASN:** AS3352  
- **ISP:** Telefónica de España S.A.U.  
- **Country:** Spain  
- **City:** Madrid

---

## Why This Matters

- **Direct Modbus exposure** of Schneider PLCs is dangerous: Modbus has no built-in security  
- The device may be connected to live industrial processes  
- If write access is enabled, attackers could **disrupt physical infrastructure**  
- **No segmentation or gateway** appears to be protecting this device

This is the **exact kind of target** threat actors scan for in ICS campaigns.

---

## Ethical Note

This information was collected using **fully passive techniques**:
- No writes, payloads, or authentication attempts were made  
- Only standard Modbus ID queries were interpreted from open-source data  
- The goal is exposure awareness and public safety

---

## Researcher Note

This is my first confirmed **live industrial PLC exposure**, and demonstrates how SCADA systems — even from trusted vendors — often reach the public internet unprotected.

> "If Modbus answers the door, it's already too late."  
> — **OpenIntelHunter**

---

## Tags

`#ics` `#plc` `#modbus` `#schneider-electric` `#telefónica` `#spain` `#tm221ce24r` `#passive-recon` `#osint`
