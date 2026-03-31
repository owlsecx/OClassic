# 🦉 OClassic

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OCipher%20%2F%20Classical%20Ciphers-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/No%20Dependencies-Stdlib%20Only-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OClassic** is a classical cipher CLI tool — encrypt and decrypt text using 11 historical cipher algorithms, brute-force all Caesar shifts, or auto-detect the likely cipher type from unknown ciphertext. Designed as a companion to OCrypt.

---

> ⚠️ Classical ciphers are **not secure** for protecting real data. Use **OCrypt** for modern encryption.
>
> 💡 **Workflow tip:** Encrypt with **OCrypt** first, then encode the output with **OClassic** for an extra obfuscation layer.

---

## 📌 Overview

OClassic implements every major classical cipher from scratch using Python's standard library only — no external dependencies. Each cipher supports Encrypt and Decrypt modes, displays a formatted result, and offers JSON/TXT/log export to `oclassic_` prefixed files.

---

## 🔐 Ciphers

| # | Cipher | Type | Key | Symmetric |
|---|--------|------|-----|-----------|
| **[1] Caesar** | Shift substitution | Shift 1–25 | Yes | ✔ with inverse shift |
| **[2] ROT13** | Caesar fixed shift 13 | None | — | ✔ self-inverse |
| **[3] Atbash** | Reverse alphabet substitution | None | — | ✔ self-inverse |
| **[4] Vigenere** | Polyalphabetic key-based | Letters keyword | Yes | ✗ |
| **[5] Beaufort** | Vigenere variant | Letters keyword | Yes | ✔ same key for E/D |
| **[6] Affine** | Mathematical `(a·x + b) mod 26` | Two integers: `a`, `b` | Yes | ✗ |
| **[7] Playfair** | Digraph substitution via 5×5 matrix | Keyword | Yes | ✗ |
| **[8] Rail Fence** | Zigzag transposition | Number of rails (2–10) | Yes | ✗ |
| **[9] Bacon** | 5-bit binary substitution (A/B groups) | None | — | ✗ |
| **[10] Polybius** | 5×5 coordinate grid substitution | None | — | ✗ |
| **[11] XOR** | XOR each byte with repeating key | Any string | Yes | ✔ same key for E/D |

---

## 🔍 Analysis Tools

### [12] Brute Force Caesar
Tries all 26 Caesar shifts and prints each result. Highlights shifts 3 and 13 as common candidates.

### [13] Auto-Detect
Analyses unknown ciphertext and returns confidence-scored suggestions:

| Confidence | Detection Method |
|------------|-----------------|
| **HIGH** | ROT13 — decoded text is >70% ASCII alphabetic |
| **HIGH** | Bacon — all tokens are 5-char groups of A/B |
| **HIGH** | Polybius — all tokens are 2-digit pairs using only digits 1–5 |
| **MEDIUM** | Rail Fence — all word tokens are equal length |
| **MEDIUM** | XOR — non-ASCII characters detected |
| **LOW** | Atbash — always attempted |
| **LOW** | Caesar — suggests brute force as fallback |

---

## ⚙️ Cipher Notes

| Cipher | Notes |
|--------|-------|
| **Affine** | Valid `a` values (coprime with 26): 1, 3, 5, 7, 9, 11, 15, 17, 19, 21, 23, 25 |
| **Playfair** | J treated as I; duplicate pairs separated with X |
| **Polybius** | 5×5 grid, J treated as I; output is space-separated coordinate pairs |
| **Bacon** | Output is space-separated 5-character A/B groups |
| **XOR** | Symmetric — same key encrypts and decrypts; non-decodeable bytes output as hex |
| **Beaufort** | Symmetric — same operation for encryption and decryption |
| **ROT13** | Symmetric — applying twice returns the original text |

---

## 📤 Export

After every operation:

| Option | Output |
|--------|--------|
| **[J] JSON** | `oclassic_YYYYMMDD_HHMMSS.json` — cipher name, mode, key, input, output |
| **[T] TXT** | `oclassic_YYYYMMDD_HHMMSS.txt` — same fields as plain text |
| **[L] Log** | Appended to `oclassic_log.txt` with timestamp |
| **[N] No** | Skip export |

---

## ⚙️ Requirements

- **Linux or Windows**
- **No Python installation needed** — runs as a standalone executable
- **No external dependencies** — stdlib only

---

## 🚀 Usage

```bash
./OClassic
```

---

## 🔗 Companion Tools

| Tool | Role |
|------|------|
| **OCrypt** | Modern encryption — encrypt with OCrypt first, then encode with OClassic |
| **OCipher** | CLI edition with identical cipher set |
| **OCipherX** | GUI edition with frequency analysis and history |

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
