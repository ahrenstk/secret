# 🔒 secret.html

> A minimalist, zero-dependency, single-file web tool for 100% client-side text encryption and decryption using the native Web Crypto API.


---

## ✨ Features

- **🛡️ 100% Client-Side:** All cryptographic operations run locally in your browser. No data ever leaves your device.
- **🌐 Zero Dependencies & Offline-Ready:** No external CDNs, tracking scripts, or libraries. Save the file and run it completely air-gapped without an internet connection.
- **🔐 Military-Grade Cryptography:**
  - **Cipher:** `AES-256-GCM` (authenticated encryption ensuring confidentiality and integrity)
  - **Key Derivation:** `PBKDF2` with `SHA-256` and **1,000,000 iterations**
  - **Randomization:** Cryptographically secure random salts (16 bytes) and IVs (12 bytes) per encryption
- **💾 Portable & Self-Replicating:** Download a clean, ready-to-share copy of the file directly from the UI with a single click.
- **🧹 Memory Hygiene:** Clears cryptographic buffers in memory immediately after processing.

---

## 🚀 Quick Start

No build tools, installations, or servers required.

1. **Download** `secret.html` from this repository.
2. **Double-click** the file to open it in any modern web browser (Chrome, Firefox, Safari, Edge).
3. Start encrypting!

---

## 📖 How to Use

### Encrypt a Message
1. Type or paste your plain text into the **Message** field.
2. Enter a strong password.
3. Click **Encrypt / Decrypt**.
4. Copy the resulting ciphertext string (prefixed with `ENC:`).

### Decrypt a Message
1. Paste the ciphertext string (starting with `ENC:`) into the **Message** field.
2. Enter the corresponding password.
3. Click **Encrypt / Decrypt**.
4. Read your decrypted text in the **Result** field.

---

## 🛠️ Technical Specifications

| Parameter | Specification |
|---|---|
| **Encryption Algorithm** | AES-GCM (256-bit key) |
| **Key Derivation (KDF)** | PBKDF2 (`HMAC-SHA-256`) |
| **Iteration Count** | 1,000,000 rounds |
| **Salt Length** | 16 bytes (via `crypto.getRandomValues`) |
| **IV Length** | 12 bytes (96 bits, standard for GCM) |
| **Output Payload Format** | `ENC:<salt_base64>:<iv_base64>:<ciphertext_base64>` |

---

## 🔍 Security & Privacy Model

- **No Remote Calls:** Check your browser's DevTools Network tab—zero HTTP requests are made.
- **Auditable Source Code:** The entire application (HTML, CSS, and vanilla JavaScript) is contained in under 300 lines of readable code in a single file.
- **Tamper Detection:** AES-GCM provides authenticated encryption. If the ciphertext or password is altered by even one bit, decryption will fail rather than return garbled data.

---

## 📄 License

MIT License. Free to use, modify, and distribute.
