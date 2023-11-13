---
category:
  - osint
---
>[!info]
>Tools related to domains and/or IP addresses, ASNs, certificates, etc.

# Domains
## Web Tools
- [URLVoid](https://urlvoid.com) - check domain reputation
- [DNSDumpster](https://dnsdumpster.com/) - query DNS records, geoIP, subdomains, domain map
- [crt.sh](https://crt.sh) - query TLS certificates for a domain
## CLI
- [Amass](https://github.com/owasp-amass/amass)
	- `amass enum -src -ip -brute -d [url]`
	- Slowest, but most thorough
- [Sublist3r](https://github.com/aboul3la/Sublist3r)
	- `python3 sublist3r.py -d [url]`
	- Fast, but only finds common subdomains
- [Photon](https://github.com/s0md3v/Photon)

# IP Addresses
- [IPVoid](https://ipvoid.com)
- [AbuseIPDB](https://abuseipdb.com)