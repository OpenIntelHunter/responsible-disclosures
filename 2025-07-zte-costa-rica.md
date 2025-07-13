Responsible Disclosure Report – ZTE Device Exposed (Costa Rica)

**Date Identified:** July 11, 2025  
**Date Reported:** July 12, 2025  
**Status:** Reported — Awaiting Response  
**IP Address:** 190.61.83.93  
**ASN:** AS52468  
**Organization:** Ufinet Costa Rica S.A.  
**Tools Used:** Shodan, Nmap, curl, OpenSSL


Summary
-------------------

While conducting passive internet reconnaissance using public tools, I identified a ZTE network device exposed to the public internet at IP address `190.61.83.93`. The device presented a login interface over both HTTP and HTTPS, and its SSL certificate revealed indicators of an internal CPE/router unintentionally exposed.



Technical Findings
-------------------

- **Open Ports:**  
  - `80/tcp` – HTTP  
  - `443/tcp` – HTTPS

- **Shodan Fingerprint:**  
  - HTTP Title: `ADC668V`
  - Device: ZTE CPE/router (likely ADC668V model)

- **SSL Certificate Analysis:**

Subject: CN=192.168.1.1, O=ZTE, ST=JiangSu, C=CN
Issuer: CN=192.168.1.1, O=ZTE, ST=JiangSu, C=CN
Validity: 2019–2036
Email: xiaoming@zte.com

- **Exposure Risk:**
- Web interface is accessible over the public internet.
- SSL certificate CN suggests the device was intended for internal LAN use.
- No access control or warning banners observed at the login prompt.

---

Ethical Note

- No authentication attempts were made.
- No unauthorized access, data collection, or modification occurred.
- This report is part of ongoing ethical OSINT and exposure awareness efforts.

---

Disclosure Details

- **Date of Disclosure:** July 12, 2025  
- **Method:** Email to abuse@ifxcorp.com  
- **From:** openintelhunter@proton.me  
- **Public Research Repo:**  
[GitHub – OpenIntelHunter](https://github.com/OpenIntelHunter/responsible-disclosures)

---

Recommendations (for Network Owner)

- Restrict external access to the web interface using firewall or NAT rules.
- Disable or secure remote management features.
- Rotate any default credentials if applicable.
- Replace or regenerate device SSL certificates to prevent fingerprinting.

---

Researcher Notes

This was one of multiple devices identified in Central America during a passive scanning campaign focused on internet exposure and device hygiene. All discoveries are documented and responsibly reported for educational and security awareness purposes.

---

“Not everything online is meant to be — that’s why we document and report.”
— **OpenIntelHunter**


