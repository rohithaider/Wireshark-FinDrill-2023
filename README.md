# 🔍 Fin Drill 2023 - Preliminary SOC & CTI Analysis

## 📄 Scenario

Your organization is currently on high alert due to increased ransomware activity. Leadership has received threat intelligence reports related to **Lockbit 3.0** and **CL0p** ransomware. As part of the SOC and CTI teams, you're tasked with analyzing network activity using a provided `.pcap` file to identify Indicators of Compromise (IOCs) and suspicious behavior.

### 🧠 Threat Intelligence Sources:
- [CISA Advisory AA23-075A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-075a)
- [CISA Advisory AA23-158A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-158a)

---

## 📝 Questions & Answers

---

## **Q1.** What are the two prominent domain names in this pcap related to Lockbit 3.0?

**Ans:**  
- `send.exploit[.]in`  
- `transfer[.]sh`  

**🛠️ Filter Used:**
```wireshark
http.host contains "premiumize.com" or
http.host contains "anonfiles.com" or
http.host contains "sendspace.com" or
http.host contains "fex.net" or
http.host contains "transfer.sh" or
http.host contains "send.exploit.in" or
ssl.handshake.extensions_server_name contains "premiumize.com" or
ssl.handshake.extensions_server_name contains "anonfiles.com" or
ssl.handshake.extensions_server_name contains "sendspace.com" or
ssl.handshake.extensions_server_name contains "fex.net" or
ssl.handshake.extensions_server_name contains "transfer.sh" or
ssl.handshake.extensions_server_name contains "send.exploit.in"
```
<img width="1439" alt="Screenshot 2025-07-01 at 10 57 02 AM" src="https://github.com/user-attachments/assets/f6db807a-bb4a-4967-8f65-e327d76b11fc" />

## **Q2.** Which IP addresses were resolved for the two domains for Lockbit 3.0 in Question 1?
Ans:

- 89.22.239.240

- 144.76.136.153
<img width="1439" alt="Screenshot 2025-07-01 at 11 03 47 AM" src="https://github.com/user-attachments/assets/2b78820f-7674-4141-a05d-8ff5f52ec859" />

## **Q3.** What are the domain names of the two failed IOC connection attempts for CL0P ransomware?
Ans:

- qweastradoc[.]com

- jirostrogud[.]com

**🛠️ Filter Used:**
```wireshark
dns.qry.name == "hiperfdhaus.com" ||
dns.qry.name == "jirostrogud.com" ||
dns.qry.name == "qweastradoc.com" ||
dns.qry.name == "connectzoomdownload.com" ||
dns.qry.name == "zoom.voyage" ||
dns.qry.name == "guerdofest.com"
```

<img width="1440" alt="Screenshot 2025-07-01 at 11 09 34 AM" src="https://github.com/user-attachments/assets/7493d9c3-d7e0-454c-836d-8abbbd6735ef" />
<img width="1439" alt="Screenshot 2025-07-01 at 11 14 56 AM" src="https://github.com/user-attachments/assets/008fc758-2ce4-4ee3-add6-399032135c3d" />
<img width="1439" alt="Screenshot 2025-07-01 at 11 17 31 AM" src="https://github.com/user-attachments/assets/0e434d14-a6a6-400c-9f62-21f2cc6d6180" />

```Here, qweastradoc[.]com containing IP 92.118.36.213 and jirostrogud[.]com containing IP 88.214.27.101 are failing to connect```.

## **Q4.** What are the resolved IP addresses for the domains in Q3?
Ans:

- 92.118.36.213

- 88.214.27.101

<img width="1439" alt="Screenshot 2025-07-01 at 11 24 11 AM" src="https://github.com/user-attachments/assets/8b384e63-7bd4-44b1-bbbb-6dc6302ed77c" />
<img width="1439" alt="Screenshot 2025-07-01 at 11 25 13 AM" src="https://github.com/user-attachments/assets/5377db4e-f498-4e92-87f3-9f70413c8734" />




