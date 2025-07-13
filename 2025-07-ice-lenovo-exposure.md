# Passive Recon: Misconfigured Web Service (Lenovo Cert) on ICE IP – Costa Rica

**Date Identified:** July 13, 2025  
**Disclosure Status:** Not reported  
**IP Address:** 201.205.227.26  
**Host:** Instituto Costarricense de Electricidad y Telecom. (ICE)  
**Tools Used:** Shodan, curl, OpenSSL, whois  
**Purpose:** Passive identification of legacy or misconfigured infrastructure

---

## Summary

Passive recon revealed a public-facing service on ICE’s network at IP `201.205.227.26` serving content over HTTP/HTTPS with the following anomalies:

- A **self-signed SSL certificate** showing `CN=Lenovo`, issued by a strange organization string: `bjasljsgs`
- **Legacy TLS support**: TLSv1 and TLSv1.2
- **PHP 5.6.37** running — an outdated version unsupported since 2018

No login or interaction was attempted. The system appears misconfigured and potentially abandoned, but still reachable over the public internet.

---

## Technical Findings

### HTTP Headers:
```http
HTTP/1.1 200 OK
X-Powered-By: PHP/5.6.37
Set-Cookie: PHPSESSID=09b5e4838d69eeae861456a6038b7c34; path=/
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-cache,must-revalidate
Pragma: no-cache
Content-type: text/html; charset=UTF-8

## SSL Certificate

Subject: CN = lenovo
Organization: bjasljsgs
Issuer: CN = lenovo, Organization = bjasljsgs
Type: Self-signed
TLS Supported: TLSv1, TLSv1.2

## IP & Ownership

    IP: 201.205.227.26
    ASN: AS11830
    Organization: Instituto Costarricense de Electricidad y Telecom.
    Country: Costa Rica
    Region: Alajuela

## Observations

    Self-signed SSL cert with unverifiable issuer (bjasljsgs)
    Legacy TLSv1 enabled (considered insecure)
    Deprecated PHP 5.6.37 running (no longer maintained)
    No branding or business headers, suggesting internal or forgotten deployment
    These signals point to exposure of internal services or development environments, unintentionally public.

## Ethical Note

    This was a fully passive reconnaissance effort:
    No login, scanning, or enumeration performed
    No attempt to bypass protections or interact with endpoints
    All findings gathered from public headers and certificate data

## Researcher Note

  Discoveries like this highlight the presence of legacy systems or internal dev servers exposed to the internet. These are often soft targets for automated scanners and require inventory hardening from host organizations.

    Old tech doesn’t disappear — it drifts onto the public net.
    — OpenIntelHunter

## Tags

#legacy-systems #ice #php5 #osint #tlsv1 #self-signed-cert #costa-rica
