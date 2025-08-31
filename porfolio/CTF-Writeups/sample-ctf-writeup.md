# Sample CTF Write-up: "Simple Web Challenge"

Curated by Jeff Mungai (jeffmungai2023@gmail.com)

## Goal
Gain access to a vulnerable web server and capture the flag.

## Tools Used
- Kali Linux
- Nmap
- Recon-ng
- Nessus
- Python

## Reconnaissance & Enumeration

**Nmap Scan:**
```bash
nmap -sV -A 10.10.10.10
```
Results:  
- Port 80/tcp open (Apache httpd 2.4.29)
- Port 22/tcp open (OpenSSH 7.6p1)

**Recon-ng:**
- Launched recon-ng and added the target domain.
- Used modules to enumerate users and directories.

## Vulnerability Scanning

**Nessus Scan:**
- Discovered outdated Apache version with known vulnerabilities (CVE-2019-0211).

## Exploitation

- Researched CVE-2019-0211 and found a public exploit.
- Used Python script to exploit the vulnerability and gain a shell.

## Post-Exploitation

- Enumerated system for flag location.
- Found `/var/www/html/flag.txt`.

## Flag / Proof

```
THM{sample_flag_redacted}
```

## Lessons Learned & Remediation

- Outdated software can be a major risk.
- Regular patching and vulnerability scanning are essential.
- Limit public exposure of sensitive services.

## References

- [Nmap Documentation](https://nmap.org/book/man-briefoptions.html)
- [Nessus Vulnerability Scanner](https://www.tenable.com/products/nessus)
- [CVE-2019-0211](https://nvd.nist.gov/vuln/detail/CVE-2019-0211)
