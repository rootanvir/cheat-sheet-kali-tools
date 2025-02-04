# John the Ripper 

## Introduction
John the Ripper is a fast password cracker used for security auditing and recovery. It supports various password hash types and can perform dictionary attacks, brute-force attacks, and rule-based attacks.
## Read [John the Ripper](../manual/john.txt) Mannual

## Installation
### Linux
```sh
sudo apt update && sudo apt install john
```

### macOS (via Homebrew)
```sh
brew install john
```

### Windows
1. Download John the Ripper from [OpenWall](https://www.openwall.com/john/).
2. Extract the archive and navigate to the `run` directory.

## Basic Usage

### Extracting Hash from a Protected File
To crack a password, we first need to extract the hash from the protected file. For example, to get the hash from a ZIP file:
```sh
zip2john protected.zip > hash.txt
```

### Cracking a Password Hash
Once we have the hash, we can proceed with cracking it:
```sh
john hash.txt
```

### Using a Custom Wordlist for Brute Force
To use a specific wordlist instead of the default one:
```sh
john --wordlist=custom_wordlist.txt hash.txt
```

### Displaying Cracked Passwords
```sh
john --show hash.txt
```

## Advanced Features

### Cracking ZIP File Passwords with Brute Force
```sh
zip2john protected.zip > hash.txt
john --incremental hash.txt
```

### Rule-Based Attacks with a Custom Wordlist
```sh
john --rules --wordlist=custom_wordlist.txt hash.txt
```

## Useful Commands
- Show available hash types:
```sh
john --list=formats
```
- Show cracked passwords:
```sh
john --show hash.txt
```
- Restore a session:
```sh
john --restore=session_name
```

## Supported File Hash Extraction & Cracking

| File Type | Extract Hash Command | Crack Hash Command |
|-----------|----------------------|--------------------|
| ZIP File | `zip2john protected.zip > hash.txt` | `john hash.txt` |
| RAR File | `rar2john protected.rar > hash.txt` | `john hash.txt` |
| PDF File | `pdf2john.pl protected.pdf > hash.txt` | `john hash.txt` |
| Windows SAM | `samdump2 SYSTEM SAM > hash.txt` | `john hash.txt` |
| Linux Shadow | `unshadow /etc/passwd /etc/shadow > hash.txt` | `john hash.txt` |
| SSH Private Key | `ssh2john id_rsa > hash.txt` | `john hash.txt` |
| Word Document | `office2john protected.docx > hash.txt` | `john hash.txt` |
| Excel Spreadsheet | `office2john protected.xlsx > hash.txt` | `john hash.txt` |
| 7-Zip Archive | `7z2john protected.7z > hash.txt` | `john hash.txt` |
---
[see more](https://www.kali.org/tools/john/) file type that can be cracked
---