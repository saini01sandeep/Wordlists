# Wordlists
# 🕵️‍♂️ wp-specter-scanlist.txt

A curated WordPress fuzzing and content discovery wordlist for red teamers, bug bounty hunters, CTF players, and penetration testers. This list is designed to uncover **hidden, misconfigured, and sensitive WordPress files, endpoints, and directories**.

---

## 🔍 What is `wp-specter-scanlist.txt`?

**`wp-specter-scanlist.txt`** is a specialized wordlist built to detect:

- Leaked configuration files (`wp-config.php`, `.env`, `.json`)
- Forgotten backups (`.bak`, `.old`, `.zip`)
- Exposed registration and login endpoints (`/wp-login.php`, `/register`, `/api/register`)
- Debug and log files (`debug.log`, `error_log`)
- Public uploads, admin panels, and plugin paths

It covers **default WordPress endpoints** + **custom and developer mistakes**.

---

## 🧰 Usage

Use this wordlist with common fuzzing and enumeration tools like:

### 🔸 FFUF

🔸 Dirsearch
```
dirsearch -u http://example.com -w wp-specter-scanlist.txt -e php,txt,json,zip
```

🔸 Gobuster
```
gobuster dir -u http://example.com -w wp-specter-scanlist.txt -x php,txt,json -t 40
```
FFUF
```
ffuf -w wp-specter-scanlist.txt -u http://example.com/FUZZ -mc 200,204,301,302
```
📁 Categories Included

🧠 Core Sensitive Files
🔐 Login & Registration Pages
🔁 Forced/Custom Register APIs
🧾 JSON/API Leakage
📁 Upload & Exposed Content
💥 Backup & Log Files
🧪 Miscellaneous Enumeration Points
#
🚨 Caution
Some paths in this list may:
Trigger WAF/IDS/IPS systems.
Lead to unintended admin actions if authenticated.
Cause noisy traffic — use responsibly.
Always seek permission before scanning live sites you don’t own.
#
🤝 Contributions
PRs welcome for:
New WordPress endpoints
Plugin-specific leaks
WAF bypass variants
Encoded or obfuscated paths
#
🔗 Related Tools
wpscan – WordPress vulnerability scanner
ffuf – Fast web fuzzer
dirsearch
