# Structured Lattice KEM: Security Reduction to NSLD

This repository contains the evaluation executable and formal documentation for a Key Encapsulation Mechanism (KEM) based on structured lattices. The project demonstrates a tight security reduction to the **Noisy Structured Lattice Decoding (NSLD)** problem.

## 📑 Project Overview
The research provides a complete, implementation-aligned security reduction. Key contributions include:
* **NSLD Problem**: Introduction of a new computational problem capturing the decoding task induced by structured message embedding.
* **Formal Proofs**: Rigorous tail bounds for structured noise using Bernstein’s inequality.
* **Beam Search Analysis**: Formal lemma bounding the failure probability (Edec ≤ 2^-80) for specific parameters.
* **RLWE Hardness**: Security is reduced to the Decisional Ring-LWE problem under the Random Oracle Model (ROM).

## 📄 Technical Documentation
For detailed mathematical proofs, variance computations, and parameter analysis, please refer to the included PDF: 
* [**pqckem.pdf**](./pqckem.pdf)

The scheme operates in the ring Rq = Zq[x]/(x^N + 1) with q = 12289 and N in {256, 512, 1024, 2048}.
### 🌐 Official Academic Publication (Zenodo)
The theoretical foundations and full technical specifications of this research have been officially published and archived on **Zenodo**:

👉 **[Read the official paper on Zenodo](https://zenodo.org/records/20282875)**

**How to cite:**
Rufo, D. (2026). Structured Lattice KEM: Security Reduction to NSLD. Zenodo. https://doi.org/10.5281/zenodo.20282875
## 💻 Usage Guide (Windows 11 64-bit)
The executable td53_full_msvc_A2.exe implements the protocol using the optimized parameters (Rrep = 18, WMAX = 60, TOPK = 4) discussed in the paper.

### 1. Key Generation
Generate the public and secret key pair:
./td53_full_msvc_A2.exe keygen alice.pk alice.sk

### 2. Encapsulation & Decapsulation
Generate a shared secret and recover it:

# Sender: generates ciphertext (ct.bin) and shared key (key_sender.raw)
./td53_full_msvc_A2.exe encapsulate alice.pk ct.bin key_sender.raw

# Receiver: recovers the shared key from the ciphertext
./td53_full_msvc_A2.exe decapsulate alice.sk ct.bin key_receiver.raw

### 3. File Encryption & Decryption
Example of encrypting a file using the public key:

# Encrypt the file
./td53_full_msvc_A2.exe encrypt-file alice.pk file.bin file.enc

# Decrypt the file
./td53_full_msvc_A2.exe decrypt-file alice.sk alice.pk file.enc file_decrypted.bin

## ⚖️ Academic Evaluation License
This software is provided exclusively for academic evaluation, benchmarking, and verification of the claims in pqckem.pdf.

* **Target OS**: Windows 11 (64-bit).
* **Restrictions**: Reverse engineering, decompilation, and commercial redistribution are strictly prohibited.
* **No Warranty**: The software is provided "as is" for research purposes.

## 🤝 Commercial Inquiries & Collaborations
This work is part of a potential patent disclosure. For inquiries regarding commercial licensing, production-grade implementations, or research collaborations, please contact the author at:
xdaniele.rufox@gmail.com

---
*© 2026 - Structured Lattice KEM Project*
---

---

### Support my Research 🚀
If you find this project useful for your benchmarks or academic evaluation, consider supporting my independent research:

[![Donate with PayPal](https://img.shields.io/badge/Donate-PayPal-blue.svg)](https://paypal.me/xdanielex272)
[![Donate with BTC](https://img.shields.io/badge/Donate-Bitcoin-orange.svg)](#)
[![Donate with USDT](https://img.shields.io/badge/Donate-Tether-green.svg)](#)

* **Bitcoin (BTC):** `bc1q4l9v8welwr6mp4g6uc2t7ex0n274malynq6yqj`
* **Tether (USDT - TRC20):** `TA3m7pqk1mTgZtFQHf7KufAqnaqsN95kPh`

---
