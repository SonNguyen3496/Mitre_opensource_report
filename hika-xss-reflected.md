###  In HikaShop Starter 4.7.5 [2308101603] i found reflected xss in error response from server when upload fail in product upload feature

HikaShop Starter 4.7.5 [2308101603] 

Demo installation: http://localhost/joomla/administrator/index.php?option=com_hikashop

### Reproduce bug:

Step 1: Access to http://localhost/joomla/administrator/index.php and login with adminstrator account. Go to Components -> HikaShop -> Products. Select specify product and upload images and files. 

![Alt text](image.png)

Step 2: In upload feature, let upload abitrary file with payload xss in filename.

![Alt text](image-5.png)

Step 3: Server response error contains file name and execute xss payload

![Alt text](image-7.png)
