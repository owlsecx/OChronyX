# 🦉 OChronyX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OChronyX** — Time-Synchronization Config Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Offline time-sync (chrony/ntpd/timesyncd/OpenNTPD) configuration auditor

---

## ✨ Features

- Offline, read-only parsers for chrony.conf (with include / confdir / sourcedir), ntp.conf (ntpd and ntpsec), timesyncd.conf (+ drop-ins) and OpenNTPD
- Amplification checks — open allow 0/0, mode 7, monitor / MRU list, missing ratelimit (T1498)
- Spoofing / time-skew checks — unauthenticated sources, broadcast / multicast clients, DHCP NTP, huge step / root distance limits (T1557, Kerberos)
- Control-plane checks — cmdallow, bindcmdaddress, cmdport, Autokey crypto, disable auth, trustedkey
- Key-file permission + weak digest checks, with every secret masked in all output
- Forensic logging checks — logchange, log measurements/statistics/tracking, noclientlog
- systemd unit / drop-in privilege review
- CWE + MITRE ATT&CK mapping, severity, remediation
- Score + grade, hardened templates, self-test demo
- Export TXT / MD / JSON / CSV / SARIF 2.1.0
- Full CLI mode (--chrony, --ntp, --root, --scan …)

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OChronyX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
