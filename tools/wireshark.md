# WireShark

### [Read](../manual/wireshark.txt) wireshark manual 

# Wireshark Filtering, Commands, and Shortcuts

## Filtering Packets (Display Filters)

| **Operator** | **Description**         | **Example**                      |
|--------------|--------------------------|----------------------------------|
| eq or ==     | Equal                    | `ip.dest == 192.168.1.1`         |
| ne or !=     | Not equal                | `ip.dest != 192.168.1.1`         |
| gt or >      | Greater than             | `frame.len > 10`                 |
| lt or <      | Less than                | `frame.len < 10`                 |
| ge or >=     | Greater than or equal    | `frame.len >= 10`                |
| le or <=     | Less than or equal       | `frame.len <= 10`                |

---

## Filter Types

| **Filter Type**    | **Description**                     |
|--------------------|-------------------------------------|
| Capture filter      | Filter packets during capture       |
| Display filter      | Hide packets from a capture display |

---

## Wireshark Capturing Modes

| **Mode**           | **Description**                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Promiscuous mode   | Capture all packets on the associated network segment                                   |
| Monitor mode       | Capture all wireless traffic (Unix/Linux only)                                          |

---

## Miscellaneous Features

| **Name**               | **Description**                          |
|------------------------|------------------------------------------|
| Slice Operator          | `[ … ]` - Range of values               |
| Membership Operator     | `{ … }` - In                            |
| CTRL+E                 | Start/Stop Capturing                     |

---

## Capture Filter Syntax

| **Syntax**  | **Protocol** | **Direction** | **Hosts**      | **Value** | **Logical Operator** | **Expressions**                     |
|-------------|--------------|---------------|----------------|-----------|---------------------|------------------------------------|
| Example     | tcp          | src           | 192.168.1.1    | 80        | and                 | `tcp dst 202.164.30.1`            |

---

## Display Filter Syntax

| **Syntax**  | **Protocol** | **String 1** | **String 2** | **Comparison Operator** | **Value** | **Logical Operator** | **Expressions**           |
|-------------|--------------|--------------|--------------|-------------------------|-----------|---------------------|--------------------------|
| Example     | http         | dest         | ip           | ==                      | 192.168.1.1 | and               | `tcp port`              |

---

## Keyboard Shortcuts - Main Display Window

| **Accelerator**      | **Description**                                        | **Accelerator**        | **Description**                                  |
|----------------------|--------------------------------------------------------|------------------------|--------------------------------------------------|
| Tab or Shift+Tab     | Move between screen elements                           | Alt+→ or Option+→      | Move to the next packet in the selection history |
| ↓                    | Move to the next packet or detail item                 | →                     | Open the selected tree item in the packet detail |
| ↑                    | Move to the previous packet or detail item             | Shift+→               | Opens the selected tree item and all subtrees    |
| Ctrl+↓ or F8         | Move to the next packet (even if not focused)          | Ctrl+→                | Open all tree items                              |
| Ctrl+↑ or F7         | Move to the previous packet (even if not focused)      | Ctrl+←                | Close all tree items                             |
| Ctrl+.               | Move to the next packet of the conversation            | Backspace             | Jump to the parent node in the packet detail     |
| Ctrl+,               | Move to the previous packet of the conversation        | Return or Enter       | Toggle the selected tree item                    |

---

## Protocols - Values

| **Protocols**                |
|------------------------------|
| ether, fddi, ip, arp, rarp   |
| decnet, lat, sca, moprc      |
| mopdl, tcp, udp              |

---

## Common Filtering Commands

| **Usage**                      | **Filter Syntax**                                |
|--------------------------------|--------------------------------------------------|
| Wireshark Filter by IP         | `ip.addr == 10.10.50.1`                         |
| Filter by Destination IP        | `ip.dest == 10.10.50.1`                         |
| Filter by Source IP             | `ip.src == 10.10.50.1`                          |
| Filter by IP range              | `ip.addr >= 10.10.50.1 and ip.addr <=10.10.50.100` |
| Filter by Multiple IPs          | `ip.addr == 10.10.50.1 and ip.addr == 10.10.50.100` |
| Filter out IP address           | `! (ip.addr == 10.10.50.1)`                     |
| Filter subnet                   | `ip.addr == 10.10.50.1/24`                      |
| Filter by port                  | `tcp.port == 25`                                |
| Filter by destination port      | `tcp.dstport == 23`                             |
| Filter by IP and port           | `ip.addr == 10.10.50.1 and tcp.port == 25`      |
| Filter by URL                   | `http.host == "host name"`                      |
| Filter by timestamp             | `frame.time >= "June 02, 2019 18:04:00"`        |
| Filter SYN flag                 | `tcp.flags.syn == 1 and tcp.flags.ack == 0`     |
| Wireshark Beacon Filter         | `wlan.fc.type_subtype = 0x08`                   |
| Wireshark broadcast filter      | `eth.dst == ff:ff:ff:ff:ff:ff`                  |
| Wireshark multicast filter      | `(eth.dst[0] & 1)`                              |
| Host name filter                | `ip.host = hostname`                            |
| MAC address filter              | `eth.addr == 00:70:f4:23:18:c4`                 |
| RST flag filter                 | `tcp.flag.reset == 1`                           |

