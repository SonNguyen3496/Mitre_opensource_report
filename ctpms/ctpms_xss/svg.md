### In T24 Temenos Core Banking Version R20.26 , I found Reflected XSS in BrowserWeb/jsps/svgInstall.jsp

Affected Version- R20.26

Parameter Affected: skin

### Reproduce bug:

Create request to https://localhost/BrowserWeb/jsps/svgInstall.jsp with payload xss in 'skin' parameter

![](./svg1.PNG)

Check the reponse i see skin parameter reflected. I injected successful <script> tag with alert()
