# week-3-project-JTR-networkwalks-
⚠️ Disclaimer: This write-up is part of an authorized training lab using a sample file provided by Networkwalks for educational purposes only. Password cracking techniques should only ever be applied to systems and files you own or have explicit, documented permission to test. Unauthorized access to protected data is illegal.

W3-PM-FINAL | Cybersecurity | Networkwalks
Field Detail
Pentester Name (Cybersecurity Professional) Ajmi Senda
Program / Batch B084 – Networkwalks Cybersecurity Internship
Date 20/11/2026
Modules completed Week 3 (Password Cracking: John the Ripper / Johnny vs. Networkwalks Hash Calculator & Password Cracker)
Attacker machine Windows (local) running John the Ripper + Johnny; browser-based Networkwalks tools (no VM required)
Targets Sample encrypted PDF file provided by Networkwalks for training purposes
Overview
This project compares two approaches to recovering a password from an encrypted PDF file: a traditional offline tool (John the Ripper, via its GUI Johnny) and a modern browser-based alternative (Networkwalks' Hash Calculator + Password Cracker). The goal was to understand the mechanics of password cracking — hash extraction, dictionary attacks, and why weak passwords fail almost instantly — and to compare the practical trade-offs between a local tool and a zero-install web tool.

Background: Why This Matters
When a file is password-protected, the actual password usually isn't stored anywhere — instead, a hash (a one-way scrambled representation of it) is stored. To recover the password, you extract that hash and run it through a cracking tool that tries candidate passwords (from a wordlist, or brute force) until one produces a matching hash. This is exactly how real attackers — and real defenders doing security audits — test password strength.

Method 1: John the Ripper + Johnny (Local Tool)
Tools: John the Ripper (JTR) · Johnny (GUI) · Windows

Steps:

Installed John the Ripper and Johnny on Windows.
Extracted the PDF's crackable hash using an online PDF-to-hash converter (equivalent to the pdf2john utility bundled with JTR).
Saved the hash to a text file in the format John the Ripper expects ($pdf$...).
Pointed Johnny to the John the Ripper executable (john.exe) and loaded the hash file.
Ran the attack.
Result: Password recovered — password1

Method 2: Networkwalks Hash Calculator + Password Cracker (Browser-Based)
Tools: Hash Calculator · Password Cracker — both run entirely client-side in the browser.

Steps:

Uploaded the same encrypted PDF to the Hash Calculator, which extracted the $pdf$... hash locally (no file ever leaves the browser).
Copied the hash into the Password Cracker tool.
Ran a dictionary attack against a built-in 100-word list.
Result: Same password recovered — password1 — confirming the result from Method 1.

Comparison
John the Ripper + Johnny Networkwalks Tools
Setup Requires installing two separate programs Zero install, runs in any browser
Platform Windows/Linux/Mac binary needed Works anywhere with a browser
Flexibility Supports many hash types, custom wordlists, rule-based attacks Simpler, built-in wordlist (upload your own .txt for more)
Best for Deeper, customizable cracking sessions Quick checks, teaching, zero-setup demos
Both approaches reached the identical result, which is a useful sanity check: the hash extraction and the underlying dictionary-attack logic are doing the same thing either way — only the interface and setup overhead differ.

Key Takeaway
The password cracked here, password1, is a textbook example of a weak password — a common dictionary word plus a single digit. It was matched almost instantly because it sits near the top of any basic wordlist. This is the core lesson of the lab: password strength isn't about feeling secure, it's about resisting exactly this kind of automated guessing. A password combining length, unrelated words, numbers, and symbols pushes cracking time from seconds to years.

Skills Demonstrated
Hash extraction from encrypted files (pdf2john-equivalent workflow)
Dictionary attacks using John the Ripper / Johnny
Comparing local vs. browser-based security tooling
Practical understanding of password hashing vs. encryption
Part of the Networkwalks Cybersecurity & Ethical Hacking internship (Oct–Nov 2026).
