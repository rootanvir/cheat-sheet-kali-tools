# HPING3
### [Read](../manual/hping3.txt) hping3 manual 
## Example
### use your target ip instead
```bash
sudo hping3 --icmp --flood 192.168.247.131
```
```bash
sudo hping3 --icmp --flood --data 1200  192.168.247.131
```
```bash
sudo hping3 --icmp --flood --data 1200 --spoof 192.168.3.65  192.168.247.131
```
```bash
sudo hping3 --udp --flood -p 53   192.168.247.131 
```
```bash
sudo hping3 --ack --flood -p 21  192.168.247.131
```
```bash
sudo hping3 --icmp --flood --rand-source 192.168.247.131
```

---

# hping3 Command Options

## General Options

| **Option**    | **Description**                                                                     |
|---------------|-------------------------------------------------------------------------------------|
| -h, --help    | Show help                                                                          |
| -v, --version | Show version                                                                       |
| -c, --count   | Packet count                                                                       |
| -i, --interval| Wait (uX for X microseconds, e.g., `-i u1000`)                                     |
| --fast        | Alias for `-i u10000` (10 packets per second)                                      |
| --faster      | Alias for `-i u1000` (100 packets per second)                                      |
| --flood       | Send packets as fast as possible; no replies shown                                 |
| -n, --numeric | Numeric output                                                                     |
| -q, --quiet   | Quiet mode                                                                         |
| -I, --interface | Specify the network interface (default: routing interface)                       |
| -V, --verbose | Verbose mode                                                                       |
| -D, --debug   | Show debugging information                                                         |

---

## Modes

| **Mode**    | **Description**                                                                      |
|-------------|--------------------------------------------------------------------------------------|
| Default     | TCP mode                                                                             |
| -0, --rawip | RAW IP mode                                                                          |
| -1, --icmp  | ICMP mode                                                                            |
| -2, --udp   | UDP mode                                                                             |
| -8, --scan  | SCAN mode (`hping3 --scan 1-30,70-90 -S www.target.host`)                            |
| -9, --listen| Listen mode                                                                          |

---

## IP Options

| **Option**         | **Description**                                                               |
|--------------------|-------------------------------------------------------------------------------|
| -a, --spoof        | Spoof source address                                                          |
| --rand-dest        | Random destination address mode                                               |
| --rand-source      | Random source address mode                                                    |
| -t, --ttl          | Set Time to Live (TTL) (default: 64)                                          |
| -N, --id           | Set packet ID (default: random)                                               |
| -W, --winid        | Use Windows-style ID byte ordering                                            |
| -r, --rel          | Relativize ID field (to estimate host traffic)                                |
| -f, --frag         | Fragment packets                                                              |
| -x, --morefrag     | Set the "More Fragments" flag                                                 |
| -y, --dontfrag     | Set the "Don't Fragment" flag                                                 |
| -g, --fragoff      | Set fragment offset                                                           |
| -m, --mtu          | Set virtual MTU (implies --frag if packet size > MTU)                        |
| -o, --tos          | Set Type of Service (default: 0x00)                                           |
| -G, --rroute       | Record route option and display the route buffer                              |
| --lsrr             | Loose source routing and record route                                         |
| --ssrr             | Strict source routing and record route                                        |
| -H, --ipproto      | Set IP protocol field (only in RAW IP mode)                                   |

---

## ICMP Options

| **Option**         | **Description**                                                               |
|--------------------|-------------------------------------------------------------------------------|
| -C, --icmptype     | ICMP type (default: echo request)                                             |
| -K, --icmpcode     | ICMP code (default: 0)                                                        |
| --force-icmp       | Send all ICMP types (default: only supported types)                           |
| --icmp-gw          | Set gateway address for ICMP redirect (default: 0.0.0.0)                      |
| --icmp-ts          | ICMP timestamp (alias for `--icmp --icmptype 13`)                             |
| --icmp-addr        | ICMP address subnet mask (`--icmp --icmptype 17`)                             |

---

## UDP/TCP Options

| **Option**         | **Description**                                                               |
|--------------------|-------------------------------------------------------------------------------|
| -s, --baseport     | Base source port (default: random)                                            |
| -p, --destport     | Destination port (default: 0)                                                |
| -k, --keep         | Keep still source port                                                       |
| -w, --win          | Window size (default: 64)                                                    |
| -F, --fin          | Set FIN flag                                                                 |
| -S, --syn          | Set SYN flag                                                                 |
| -R, --rst          | Set RST flag                                                                 |
| -P, --push         | Set PUSH flag                                                                |
| -A, --ack          | Set ACK flag                                                                 |
| -U, --urg          | Set URG flag                                                                 |
| -X, --xmas         | Set X unused flag (0x40)                                                     |
| -Y, --ymas         | Set Y unused flag (0x80)                                                     |
| --tcpexitcode      | Use last `tcp->th_flags` as exit code                                        |

---

## Common Options

| **Option**        | **Description**                                                               |
|-------------------|-------------------------------------------------------------------------------|
| -d, --data        | Data size (default: 0)                                                        |
| -E, --file        | Send data from a file                                                        |
| -e, --sign        | Add signature                                                                 |
| -j, --dump        | Dump packets in hex                                                           |
| -T, --traceroute  | Traceroute mode (implies `--bind` and `--ttl 1`)                              |
| --tr-stop         | Exit on first non-ICMP response in traceroute mode                            |
| --tr-keep-ttl     | Keep source TTL fixed (monitor a single hop)                                  |
| --tr-no-rtt       | Don't show RTT information in traceroute mode                                 |

