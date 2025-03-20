# 🔵 l2ping Cheatsheet

## 📌 What is `l2ping`?
`l2ping` is a command-line tool used in Linux to test Bluetooth connectivity by sending **L2CAP echo requests** to a remote Bluetooth device. It works similarly to the `ping` command for network testing but is specifically designed for Bluetooth devices. It helps in diagnosing **Bluetooth reachability** and **latency issues**.

## Read l2ping user [manual](../manual/l2ping.txt)
---

## 🔧 Basic Commands

### 🔍 Check if `l2ping` is installed
```bash
l2ping --help
```
If not installed, install it using:
```bash
sudo apt install bluez
```

### 📡 Scan for nearby Bluetooth devices
```bash
hcitool scan
```
_Note the MAC address of the target device._

### 📶 Ping a Bluetooth device (Basic Test)
```bash
sudo l2ping -c 5 <MAC_ADDRESS>
```
- `-c 5`: Sends **5 ping packets** to test connectivity.

### 🚀 Continuous ping test
```bash
sudo l2ping <MAC_ADDRESS>
```
_(Runs indefinitely, use `Ctrl + C` to stop)_

### ⚡ Send high-speed pings
```bash
sudo l2ping -s 1000 -c 10 <MAC_ADDRESS>
```
- `-s 1000`: Packet size (1000 bytes).
- `-c 10`: Send **10 packets**.

### ❌ Troubleshooting: Reset Bluetooth adapter
```bash
sudo hciconfig hci0 reset
```

---

## 🎯 Example Usage:
```bash
sudo l2ping -c 3 -s 600 00:1A:7D:DA:71:13
```
📌 This sends **3 packets** of **600 bytes** to **00:1A:7D:DA:71:13** to check Bluetooth reachability.

---

Let me know if you need more details! 🚀
