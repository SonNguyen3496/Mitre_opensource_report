###  In HikaShop Starter 4.7.5 [2308101603] i found stored xss through upload svg file.

HikaShop Starter 4.7.5 [2308101603] 

Demo installation: http://localhost/joomla/administrator/index.php?option=com_hikashop

### Reproduce bug:

Step 1: Access to http://localhost/joomla/administrator/index.php and login with adminstrator account. Go to Components -> HikaShop -> Products. Select specify product and upload images and files. 

![Alt text](image.png)

Step 2: In default , hikashop extensions accept upload svg file so we don't need to config anything. In upload feature, let upload svg file with payload xss.

![Alt text](image-2.png)

Step 3: The image will upload to /joomla/images/com_hikashop/upload/ folder. Send Get Request to file -> XSS trigger

![Alt text](image-3.png)

Check image render from client site -> xss trigger ->  Attacker can steal infomation from user.

![Alt text](image-4.png)