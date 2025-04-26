# XSStrike: XSS Vulnerability Detection and Exploitation Tool

## Introduction

**XSStrike** is an advanced tool used to detect and exploit **Cross-Site Scripting (XSS)** vulnerabilities in web applications. XSStrike is capable of identifying XSS vulnerabilities across various attack vectors, including **reflected**, **stored**, and **DOM-based XSS**. It provides powerful fuzzing techniques, payload generation, and automated testing for XSS vulnerabilities.

This document explains how to use XSStrike and highlights the different types of parameters that XSStrike targets in its attacks.

---

## Features of XSStrike

- **Comprehensive XSS Detection**: Detects reflected, stored, and DOM-based XSS vulnerabilities.
- **Smart Payload Generator**: Generates and tests various XSS payloads.
- **Parameter Analysis**: Identifies vulnerable parameters susceptible to XSS attacks.
- **Fuzzing Capabilities**: Performs fuzzing on different parameters to uncover vulnerabilities.
- **Advanced Techniques**: Includes techniques to bypass filters and Web Application Firewalls (WAFs).
- **Custom Payloads**: Users can craft and test custom XSS payloads.
- **Intercept and Replay**: Integrates with intercepting proxies like Burp Suite to test requests with injected XSS payloads.

---
## Go to github [page](https://github.com/s0md3v/XSStrike.git)

## Installation

To install XSStrike, follow these steps:

   ```bash
   git clone https://github.com/s0md3v/XSStrike
   cd XSStrike
   pip install -r requirements.txt --break-system-packages
   ```

## Options

### Target Specification
- `-u`, `--url` : Specify the target URL
- `--data` : Send payload via POST (e.g., `--data "q=query"`)
- `-t`, `--threads` : Number of threads to use (default: 16)
- `-l`, `--level` : Level of crawling (default: 2)

### Payload Options
- `-e`, `--encode` : Encode payloads
- `-f`, `--file` : Custom payload file (default: payloads.txt)
- `--path` : Inject payload in path (e.g., `http://example.com/search/<script>alert(1)</script>/`)

### Detection Options
- `--skip` : Skip confirmation prompts
- `--skip-dom` : Skip DOM scanning
- `--blind` : Inject blind XSS payloads

### Proxy Options
- `--proxy` : Use proxy (e.g., `--proxy http://127.0.0.1:8080`)
- `--timeout` : Request timeout in seconds (default: 7)

### Crawling Options
- `-c`, `--crawl` : Crawl the target website
- `--depth` : Maximum crawl depth (default: 5)

### Miscellaneous
- `--update` : Update XSStrike
- `-v`, `--verbose` : Verbose output
- `-h`, `--help` : Show help message

#  Using Custom Headers & Cookies
How to Send Headers with Requests
## 1. Basic Header Injection
```bash
python3 xsstrike.py -u "http://example.com/search?q=test" 
```
-  --headers "User-Agent: XSStrike/1.0" 
-  --headers "Accept-Language: en-US"
## 2. Sending Cookies
```bash
python3 xsstrike.py -u "http://example.com/login" 
-  --headers "Cookie: session_id=abc123; csrf_token=xyz456"
```
## 3. Multiple Headers
```bash
python3 xsstrike.py -u "http://example.com/api" 
-  --headers "Authorization: Bearer token123" 
-  --headers "Content-Type: application/json" 
-  --headers "X-Custom-Header: value"
```
## 4. With POST Data
```bash
python3 xsstrike.py -u "http://example.com/submit" 
```
-  --data "username=admin&password=test" 
-  --headers "Content-Type: application/x-www-form-urlencoded" 
-  --headers "Cookie: auth=yes"
## 5. Using Proxy with Headers
```bash
python3 xsstrike.py -u "http://example.com" 
```
-  --headers "User-Agent: Mozilla/5.0 (Windows NT 10.0)" 
-  --proxy "http://127.0.0.1:8080"


### Example
```bash
python3 xsstrike.py -u "http://example.com/search.php?q=test" --headers "Cookie: sessionid=1234abc; auth_token=xyz"
```



