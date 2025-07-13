## Passive Recon: Siemens SIMATIC S7-300 PLC Exposed – Palma, Spain

**Date Identified:** July 13, 2025  
**Disclosure Status:** Disclosure sent to Telefónica (Pending)  
**IP Address:** 80.26.159.23  
**Hostname:** 23.red-80-26-159.staticip.rima-tde.net  
**ISP:** Telefónica de España S.A.U.  
**ASN:** AS3352  
**Location:** Palma, Spain  
**Tools Used:** Shodan, passive S7 protocol fingerprinting  
**Focus:** Critical ICS infrastructure exposure – Siemens PLC

---
## Summary

A publicly accessible Siemens SIMATIC S7-300 series **Programmable Logic Controller (PLC)** was discovered responding to unauthenticated S7 protocol queries from a public IP in Palma, Spain.

The PLC provides detailed hardware and firmware metadata — exposing a **fully identifiable industrial control unit** manufactured by Siemens.

---
## Device Fingerprint (Shodan Output)

Copyright: Original Siemens Equipment
PLC name: SIMATIC 300(1)
Module type: CPU 315-2 DP
Module: 6ES7 315-2AH14-0AB0 v.0.7
Basic Firmware: v.3.3.16
Serial number: S C-L8CB62162019


> This data was returned with **no authentication required** over the Siemens S7 protocol (port 102). No write or configuration attempts were made.

---

## IP & Ownership

- **IP:** 80.26.159.23  
- **Hostname:** 23.red-80-26-159.staticip.rima-tde.net  
- **ASN:** AS3352  
- **ISP:** Telefónica de España S.A.U.  
- **Country:** Spain  
- **City:** Palma

---

## Why This Is Critical

| Factor                            | Risk Description                                     |
|-----------------------------------|------------------------------------------------------|
| * Vendor/Device Identity          | Clear Siemens equipment info exposed                 |
| * Industrial Hardware             | SIMATIC S7-300 PLCs are used in real industrial systems |
| * No Authentication               | Device responds openly to metadata queries           |
| * Public Internet Exposure        | The PLC is reachable from any IP without firewalling |
| * Attack Surface                  | Metadata can assist attackers in creating payloads   |

Deployed ICS device** actively used for automation or control.

---
## Ethical Note

All findings were collected through **passive, non-invasive techniques**:
- No write or configuration commands were sent  
- No credentials were tested  
- The purpose is to raise awareness and improve industrial cybersecurity hygiene

---

## Disclosure Note

A responsible disclosure email was sent to **abuse@telefonica.es** on **July 13, 2025**, providing the technical details and a link to this case report. Awaiting acknowledgment or resolution.

---
## Analyst Note

This is my second confirmed case of **high-value ICS exposure** involving a Tier 1 national ISP. The richness of device metadata and vendor identifiers makes this finding highly sensitive, and a clear example of how vulnerable SCADA infrastructure often remains online — unmonitored and unsegmented.

> *“Industrial protocols speak loudest when no one’s listening.”*  
> — **OpenIntelHunter**

---
## Tags

`#ics` `#plc` `#siemens` `#s7` `#modbus` `#port102` `#spain` `#passive-recon` `#openintelhunter` `#scada`
