# DNS TrustPositif — Internet Sehat Indonesia 2045

> DNS filtering project untuk membangun ekosistem internet yang lebih aman, bersih, dan terkontrol di Indonesia.

---

## Status

![Repo Status](https://img.shields.io/badge/status-active-brightgreen)
![Maintenance](https://img.shields.io/badge/maintenance-automated-blue)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Focus](https://img.shields.io/badge/focus-DNS%20Filtering-red)

---

## Overview

Repository ini menyediakan **domain blocklist terkurasi dan terotomatisasi** untuk:

- DNS Filtering (Unbound, Pi-hole, AdGuard, MikroTik)
- Network security hardening
- ISP / enterprise filtering
- Personal / home network protection

Tujuan utama: mendukung **Internet Sehat Indonesia menuju 2045** dengan filtering berbasis DNS yang cepat dan ringan.

---

## Features

- Aggregation multi-source blocklist
- Auto deduplication (1 domain = 1 entry)
- Clean output (no comments, no noise)
- Ready-to-use formats:
  - Plain domain list
  - RPZ / Unbound zone format
- Auto update pipeline (CI/CD friendly)
- Whitelist override support
- Production-ready filtering dataset

---

## Supported Sources

- TrustPositif Indonesia
- StevenBlack Hosts
- OISD Blocklists
- Hagezi DNS Blocklists
- Abuse.ch (URLHaus)
- Community curated feeds

---

## Output Format

### Plain Domain List
yapidea.com
yapifest.com
yapifilo.com
yapikrd.click
yapikredi-katilimmbasvurumtrgiris.xn--fiqz9s
yapikredi.ru
yapikronline.com
yapikur.com.tr
yapilo.pw
yapimek.com
yapimobill.com
yapins.com
yapisalkonutlar.baby
yapisalkonutlar.lol
yapisalkonutlar.mom
yapisalkonutlar.pics
yapiskanli.com
yapmakicinyapanlardadavar.sbs
yapmancowson.com
yapmanhubio.digital
yaponika.com
yappa.shop
yappenglish.com.br
yappertree.com
yapplanetsterritory.com
yaprakdolmayekeyfet1.com
yaprakmenfez.com
yapraktakvim.com

### RPZ / Unbound

local-zone: "example.com" redirect
local-data: "example.com A 0.0.0.0"


---

## Deployment

### Unbound (RPZ)

response-policy:
zone:
name: "trustpositif"
zonefile: "/etc/unbound/blocklist.conf"


---

### Pi-hole

pihole -b -f https://raw.githubusercontent.com/USER/REPO/main/domains.txt


---

### MikroTik RouterOS v7

/ip dns static
add name=example.com address=0.0.0.0


---

## Automation

Pipeline mencakup:

- Fetch upstream sources
- Normalize domain format
- Remove duplicates
- Whitelist filtering
- Auto commit & push to GitHub

---

## Project Goal

- Network-level protection by default
- Lightweight DNS filtering for all devices
- Scalable for ISP & enterprise deployment
- Clean internet ecosystem for Indonesia 2045

---

## Support

- Star repository
- Fork & contribute rules
- Submit issue / domain report
- Share ke komunitas network security

---

## Disclaimer

Project ini bersifat open-source untuk edukasi dan keamanan jaringan. Penggunaan sepenuhnya menjadi tanggung jawab pengguna.

---

Maintained for DNS security, filtering research, and internet hygiene systems.
