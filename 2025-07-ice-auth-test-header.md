# Passive Recon: ICE Web Service with `Authentication: test` Header – Costa Rica

**Date Identified:** July 13, 2025  
**Disclosure Status:** Not reported  
**IP Address:** 201.204.177.219  
**Host:** Instituto Costarricense de Electricidad y Telecom. (ICE)  
**Tools Used:** Shodan, curl, whois  
**Purpose:** Document unusual HTTP header behavior on public systems

---

## Summary

While passively enumerating web-accessible systems in Costa Rica, I identified a web server hosted by **ICE** on IP `201.204.177.219`. The service responds with standard HTTP/1.0 `200 OK`, minimal content, and includes a highly unusual HTTP header:


This suggests that either:
- A **placeholder or development build** was deployed to production
- An **internal system** was unintentionally exposed
- Or the server software is misconfigured to leak non-standard headers

The server also identifies itself as `GeoHttpServer`, a lesser-known implementation.

---
## 🔍 Technical Findings

### HTTP Response:
```http
HTTP/1.0 200 OK
Server: GeoHttpServer
Date: Sun, 13 Jul 2025 03:40:11 GMT
Content-type: text/html
Content-length: 5734
Authentication: test
X-Frame-Options: SAMEORIGIN
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
Content-Security-Policy: script-src 'self' 'unsafe-inline'

## IP & Ownership

    IP: 201.204.177.219
    ASN: AS11830
    Organization: Instituto Costarricense de Electricidad y Telecom.
    Country: Costa Rica
    Region: San José


## Observations

    The header Authentication: test is not a valid or standard auth mechanism
    The header may indicate a dev/staging artifact that was not cleaned up
    Response uses HTTP/1.0, an outdated protocol
    Server ID string GeoHttpServer is uncommon, possibly custom or embedded  
    No login page was presented, but the presence of this header may signal underlying API or service components.

## Ethical Note

    This is a fully passive recon effort:
    No login, enumeration, or payload delivery was attempted
    No scanning, exploitation, or bypass effort conducted
    All data was extracted from standard HTTP headers and DNS

## Researcher Note

Headers like Authentication: test can be overlooked — but they’re often breadcrumbs from developers or staging environments that slipped into production. These kinds of observations form the backbone of threat surface mapping.

    Weak signals, when collected consistently, form strong intel.
    — OpenIntelHunter

## Tags

#ice #headers #authentication-test #legacy-http #geohttpserver #passive-recon #costa-rica
