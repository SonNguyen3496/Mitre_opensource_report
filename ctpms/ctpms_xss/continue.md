### In T24 Temenos Core Banking Version R20.26 , I found Reflected XSS in BrowserWeb/jsps/continue.jsp

Affected Version- R20.26

Parameter Affected: cfwstage

### Reproduce bug:

Create request to https://localhost/BrowserWeb/jsps/continue.jsp with payload xss in 'cfwstage' parameter

![](./continue1.PNG)

Check the response from sever. We inject successfully <script> tag with alert(1)
