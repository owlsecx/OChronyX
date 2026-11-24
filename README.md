# 🦉 OChronyX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
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

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OChronyX --help   # watch every network call
firejail --net=none ./OChronyX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
