# IPTABLES CHEATSHEET 
## Read iptables [manual](../manual/iptables.txt)
## 🔍 Basic Commands

### List all rules with line numbers
```bash
sudo iptables -L --line-numbers -v
```

### Save iptables rules (Kali Linux)
```bash
sudo iptables-save > /etc/iptables/rules.v4
```

### Restore iptables rules
```bash
sudo iptables-restore < /etc/iptables/rules.v4
```

### Flush all rules (reset)
```bash
sudo iptables -F
```

### Delete a rule by line number
_Find the rule number using `iptables -L --line-numbers`_
```bash
sudo iptables -D INPUT <RULE_NUMBER>
```

## 🚫 Blocking & ✅ Allowing Traffic

### Block an IP address
```bash
sudo iptables -A INPUT -s <IP_ADDRESS> -j DROP
```

### Allow an IP address
```bash
sudo iptables -A INPUT -s <IP_ADDRESS> -j ACCEPT
```

### Block a specific port (e.g., HTTP 80)
```bash
sudo iptables -A INPUT -p tcp --dport 80 -j DROP
```

### Allow a specific port (e.g., SSH 22)
```bash
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

## 🔄 NAT & Forwarding

### Enable NAT (Masquerade outgoing traffic)
```bash
sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

### Forward traffic from one port to another
```bash
sudo iptables -t nat -A PREROUTING -p tcp --dport 8080 -j REDIRECT --to-port 80
```

### Enable IP forwarding (temporary)
```bash
echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward
```

## 🗑 Deleting & Resetting Rules

### Flush all rules and reset iptables
```bash
sudo iptables -F
```

### Delete a specific rule (find rule number first)
```bash
sudo iptables -D INPUT <RULE_NUMBER>
```

## 💾 Saving & Restoring Rules (Kali Linux)

### Save current rules
```bash
sudo iptables-save > /etc/iptables/rules.v4
```

### Restore rules
```bash
sudo iptables-restore < /etc/iptables/rules.v4
```

### Make rules persistent (Kali Linux)
```bash
sudo apt install iptables-persistent
sudo netfilter-persistent save
sudo netfilter-persistent reload
```
