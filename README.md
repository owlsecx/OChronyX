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

OChronyX is an offline, read-only auditor for time-synchronization configuration, covering chrony, ntpd/ntpsec, systemd-timesyncd and OpenNTPD. It parses each daemon's configuration (including includes and drop-ins) and checks for amplification exposure, spoofing/time-skew risks, control-plane exposure and weak authentication, with every secret masked. Findings map to CWE and MITRE ATT&CK with a score, grade and hardened templates.

---

## ✨ Features

- Offline parsers for chrony.conf, ntp.conf, timesyncd.conf and OpenNTPD
- Amplification checks: open allow 0/0, mode 7, monitor/MRU, missing ratelimit (T1498)
- Spoofing/time-skew checks: unauthenticated sources, broadcast clients, step limits (T1557)
- Control-plane checks: cmdallow, bindcmdaddress, Autokey, trustedkey
- Key-file permission and weak-digest checks with secrets masked
- CWE + MITRE ATT&CK mapping, hardened templates and export TXT/MD/JSON/CSV/SARIF

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OChronyX --scan
./OChronyX --chrony /etc/chrony/chrony.conf --format json -o report.json --fail-on high
./OChronyX --root /mnt/image --scan
./OChronyX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled.s.Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
