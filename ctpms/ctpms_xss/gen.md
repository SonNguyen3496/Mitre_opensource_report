### In T24 Temenos Core Banking Version R20.26 , I found Reflected XSS in BrowserWeb/jsps/gendocrequest.jsp

Affected Version- R20.26

Parameter Affected: enqid, imageId, isPopUp

### Reproduce bug:

Create request to https://localhost/BrowserWeb/jsps/gendocrequest.jsp with payload xss in 'enqid' parameter

![](./gen1.PNG)

check the response from server, injected <script> tag with alert()
