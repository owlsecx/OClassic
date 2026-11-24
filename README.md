# 🦉 OClassic

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCipher-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OClassic** — Professional Classical Cipher Suite

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OClassic is a professional classical cipher suite that encrypts, decrypts and analyses text across more than twenty historical schemes. Beyond the common Caesar, Vigenère and Playfair ciphers it adds Four-Square, Homophonic, Running Key, columnar transposition and Morse, with brute-force Caesar, auto-detection and frequency analysis. Operations are available both interactively and from the command line for scripting.

---

## ✨ Features

- 20+ ciphers incl. Caesar, Vigenère, Playfair, Affine, Bacon and Four-Square
- Columnar transposition, Homophonic and Running Key ciphers
- Brute-force Caesar and automatic cipher auto-detection
- Frequency analysis for cryptanalysis
- Command-line mode with cipher, mode, key, shift and rails options
- Session logging of operations

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OClassic --cipher caesar --mode E --text "HELLO" --shift 3
./OClassic --cipher vigenere --mode D --text "RIJVS" --key KEY
./OClassic
./OClassic --help
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
sudo strace -f -e trace=network ./OClassic --help   # watch every network call
firejail --net=none ./OClassic --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
