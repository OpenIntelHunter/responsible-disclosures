## Passive Recon: Publicly Exposed Modbus Service – Spain (Cableworld)

**Date Identified:** July 13, 2025  
**Disclosure Status:** Not reported  
**IP Address:** 89.29.160.171  
**Domain/Hostname:** 89.29.160.171.novelda.cableworld.es  
**ISP:** Cable Aireworld S.A.U. (Cableworld)  
**ASN:** AS35394  
**Country:** Spain  
**City:** Novelda  
**Tools Used:** Shodan, masscan, browser test, TCP/IP header inspection  
**Purpose:** SCADA infrastructure exposure mapping

---

## Summary

During passive SCADA reconnaissance, I identified IP `89.29.160.171`—a system hosted by Spanish ISP **Cableworld**—with **port 502 (Modbus TCP)** publicly accessible.
Modbus is a protocol used for **industrial equipment communication**, typically found in:

- Electric grids  
- Factory PLCs  
- HVAC control  
- Water/gas infrastructure

The device did **not respond over port 80 (HTTP)**, indicating no public web interface. However, the Modbus service itself remains reachable, which is a serious concern given Modbus’s **lack of authentication or encryption**.

---

## Technical Findings

- **Open port 502** (Modbus TCP) confirmed via passive scan
- **Port 80 (HTTP)** returned `i/o timeout` (likely filtered or no service running)
- No browser-accessible UI, suggesting a headless device (likely a PLC or gateway)

### Browser Output:

dial tcp4 149.34.248.77:0->89.29.160.171:80: i/o timeout

---

## IP & Ownership

- **IP Address:** 89.29.160.171  
- **Hostname:** 89.29.160.171.novelda.cableworld.es  
- **Domain:** cableworld.es  
- **ASN:** AS35394  
- **ISP:** Cable Aireworld S.A.U.  
- **Organization:** TELENOVELDA, Infraestructure Access Network  
- **Country:** Spain  
- **City:** Novelda

---

## Why This Matters

Port 502 is the default for **Modbus TCP**, a protocol designed for **trusted internal industrial networks**. It:

- Has **no authentication or encryption**
- Allows attackers to **read or manipulate physical equipment**
- Is frequently exploited in critical infrastructure breaches

**Even passive exposure to the public internet** creates a massive surface for:
- Botnet targeting  
- Automated scans  
- Industrial disruption

---

## Ethical Note

This entry was gathered via **100% passive methods**:
- No login attempts or command delivery
- No device interaction or payload submission
- No manipulation or probing of Modbus registers
- This is a documentation effort to highlight SCADA exposure patterns in Europe.

---

## Researcher Note

This marks the beginning of my **SCADA/ICS exposure mapping** work. It demonstrates how even quiet endpoints can represent critical weaknesses — and how overlooked industrial protocols often go unmonitored on public networks.

> Modbus doesn’t knock — it opens the door and walks right in.  
> — **OpenIntelHunter**

---

## Tags

`#modbus` `#scada` `#ics` `#cableworld` `#spain` `#plc` `#infrastructure` `#osint`
