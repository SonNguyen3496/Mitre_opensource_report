### In Covid 19 Travel Pass Management 1.0 , I found Unauth Reflect XSS via parameters "code" in view_pass.php 

Affected Version- 1.0

Demo installation: https://localhost/ctpms/

### Reproduce bug:

Step 1: Access to https://localhost/ctpms/ and access to verify pass feature in menu.

![](./1.png)

Step 2: In enter pass code field, inject Reflect XSS payload 

`Payload : <script>alert('xss')</script>`

![](./3.png)

Step 3: Continue to Verify Travel Pass -> XSS trigger. 

![](./4.png)

Code do not have any filter for user input in view_pass.php line 136,137

![](./6.png)
