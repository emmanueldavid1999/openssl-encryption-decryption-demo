# openssl-encryption-decryption-demo
A demonstration of file encryption and decryption using OpenSSL with AES-256-CBC in a command-line environment.
# 🔐 OpenSSL – Quick Setup & Usage Guide

## 📌 Overview

**OpenSSL** is an open-source toolkit used for:

* Secure communication (SSL/TLS)
* Encryption & decryption
* Generating keys and certificates

It’s widely used in web servers, apps, and security systems.

---

## ⚙️ Installation

### 🪟 Windows

1. Download from a trusted source (e.g., Shining Light Productions)

2. Install and note the installation path (e.g., `C:\OpenSSL-Win64`)

3. Add to system PATH:

   * Search **Environment Variables**
   * Edit **Path**
   * Add: `C:\OpenSSL-Win64\bin`

4. Verify installation:

   ```bash
   openssl version
   ```

---

### 🐧 Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install openssl
```

---

### 🍎 macOS

```bash
brew install openssl
```

---

## 🔑 Basic Commands

### 1. Check OpenSSL Version

```bash
openssl version
```

---

### 2. Generate Private Key

```bash
openssl genrsa -out private.key 2048
```

---

### 3. Generate Public Key

```bash
openssl rsa -in private.key -pubout -out public.key
```

---

### 4. Create Certificate Signing Request (CSR)

```bash
openssl req -new -key private.key -out request.csr
```

---

### 5. Generate Self-Signed Certificate

```bash
openssl req -x509 -key private.key -in request.csr -out certificate.crt -days 365
```

---

### 6. Encrypt a File

```bash
openssl enc -aes-256-cbc -salt -in file.txt -out file.enc
```

---

### 7. Decrypt a File

```bash
openssl enc -aes-256-cbc -d -in file.enc -out file.txt
```

---

## 🔐 Common Use Cases

* Securing websites with HTTPS (SSL certificates)
* Encrypting sensitive data
* Generating API keys and tokens
* Testing secure connections

---

## ⚠️ Important Notes

* Keep your **private key safe** — never share it
* Use strong key sizes (2048 or 4096 bits)
* Always verify certificates before using them in production

---

## 🧪 Troubleshooting

### Command not recognized

* Ensure OpenSSL is added to PATH

### Permission errors (Linux/macOS)

```bash
sudo <command>
```

---

## 📂 File Types Explained

* `.key` → Private key
* `.csr` → Certificate Signing Request
* `.crt` / `.pem` → Certificate file

---

## 🚀 Pro Tip

For production systems, use certificates from trusted Certificate Authorities (CAs) instead of self-signed ones.

---

## 📞 Need Help?

If you're using OpenSSL for:

* Web development
* Backend APIs
* Security projects

Ask for a tailored setup — the commands can change depending on your use case.

---
