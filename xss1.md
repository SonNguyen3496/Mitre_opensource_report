###  In Apache JSPWiki 2.12 i found stored xss through upload html file.

Apache JSPWiki 2.12 

Demo installation: http://localhost:8080

### Reproduce bug:

Step 1: Access to http://localhost:8080/Upload.jsp?page=UnusedPages
In default, apache jspwiki accept upload svg file so i try to upload html file with  payload xss in content:
```
<script>alert(document.cookie)</script>
```

![](3.png)

![](5.png)

Step 3: The image will upload to /attach/UnusedPages/$filename/ . Access to file -> XSS trigger

![](4.png)

