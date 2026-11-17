# Password Cracking & Cryptographic Hash Analysis Lab

A hands-on cybersecurity lab focusing on password auditing, hash extraction, and dictionary-based cracking techniques using **John the Ripper (JTR)** on Kali Linux CLI and **Networkwalks Browser Tools**.

---

## Tools & Technologies Used
* **Operating System:** Kali Linux
* **Cracking Tools:** John the Ripper (JTR) / `pdf2john`
* **Web Utilities:** Networkwalks Hash Calculator & Password Cracker (Browser-based)
* **Target File:** Password-protected PDF (`My Locked PDF1.pdf`)

---

## Project Structure
```text
password-cracking-lab/
├── README.md               # Project documentation
└── screenshots/            # Visual proofs of successful cracking
```

## Lab Overview & Methodology
### John the Ripper (JTR) via Kali Linux CLI
**Hash Extraction:** Extracted the cryptographic hash from the password-protected PDF using the built-in `pdf2john` utility:
```bash
pdf2john "My Locked PDF1.pdf" > pdf_hash.txt
```

**Dictionary Attack:** Executed John the Ripper using the standard wordlist (`rockyou.txt`) to crack the PDF hash:
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt pdf_hash.txt
```
**Result Verification:** Displayed the recovered plaintext password using:
```bash
john --show pdf_hash.txt
```

### Networkwalks Browser-Based Tools
**Hash Calculator:** Uploaded the encrypted PDF locally via the browser tool to parse and extract the ```$pdf$``` format hash.

**Password Cracker:** Fed the extracted hash into the dictionary attack module to simulate brute-forcing against common wordlists, successfully unlocking the file to retrieve the security flag.


### Key Security Takeaways
**Hashing vs. Encryption:** Encryption is a two-way reversible function using keys, whereas hashing is a one-way cryptographic function used for verification.

**Password Complexity:** Short or common dictionary words ```(e.g., password1)``` are cracked within seconds, emphasizing the critical need for long, complex, and mixed-character passwords.


### Author
**Samiullah**

