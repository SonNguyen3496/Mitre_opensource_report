### In T24 Temenos Core Banking Version R20.26 , I found Reflected XSS in BrowserWeb/jsps/customMessage.jsp

Affected Version- R20.26

Parameter Affected: Message

### Reproduce bug:

Create request to https://localhost/BrowserWeb/jsps/customMessage.jsp with payload xss in 'Message' parameter

Payload : `<img src=1 onerror=alert('xss')>`

![](./image1.png)

After that xss payload trigger 

![](./image2.png)
