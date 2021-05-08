<h2 align="center"> Task: </h2>

Setup the mail server on rhel 6

</br>


<h2 align="center"> Test cases: </h2>

|S.NO|Test Cases|Test Case Description|Expected Result|Test Status|
|:----:|:-----:|:-----:|:-----:|:-----:|
|1 |**Install postfix** |Install postfix by using this command **yum install postfix -y** |Postfix should be installed |**PASS** |
|2 |**Start the postfix** |I started the postfix by using this command **service start postfix**  |Postfix should be start |**PASS** |
|3 |**Enable the postfix** |I enable the postfix by using **chkconfig postfix on** |Postfix should be enable should be downloaded |**PASS** |
|4 |**Configure postfix** | I configured the postfix by using its configuration file and the path of configuration file is **/etc/postfix/main.cf** |Postfix should be configured |**PASS** | 
|6 |**Testing postfix by using telnet** |I tested the postfix working by using **telnet localhost smtp** |Postfix should work properly |**PASS** | 
|7 |**Install dovecot** |Install dovecot by using this command **yum install dovecot -y** |dovecot should be installed |**PASS** |
|8 |**Start the dovecot** |I started the dovecot by using this command **service start dovecot**  |dovecot should be start |**PASS** |
|9 |**Enable the dovecot** |I enable the dovecot by using **chkconfig dovecot on** |dovecot should be enable |**PASS** |
|10|**Configure dovecot** | I configured the dovecot by using its configuration file and the path of configuration file is **/etc/dovecot/dovecot.conf** </br> **/etc/dovecot/conf.d/10-mail.conf** </br> **/etc/dovecot/conf.d/10-auth.conf** </br> **/etc/dovecot/conf.d/10-master.conf** |dovecot should be configured |**PASS** | 
|11|**Testing dovecot by using telnet** |I tested the dovecot working by using **telnet localhost pop3** |dovecot should work properly |**PASS** |
|12|**Install squirrelmail** |Install squirrelmail by using this command **yum install squirrelmail -y** |squirrelmail should be installed |**PASS** |
|13|**Configure postfix** | I configured the postfix by using the path **/usr/share/squirrelmail/config** and run the command on terminal </br> **./conf.pl** |squirrelmail should be configured |**PASS**|
|14|**Install the httpd** |I installed the httpd by using this command **yum install httpd**  |httpd should be installed |**PASS** |
|15|**Configure httpd** | I configured the httpd by using its configuration file and the path of configuration file is **/etc/httpd/conf/httpd.conf** |httpd should be configured |**PASS** |
|16|**restart the httpd** |I started the httpd by using this command **service restart httpd**  |httpd should be restart |**PASS** |
|17|**Enable the httpd** |I enable the httpd by using **chkconfig httpd on** |Postfix should be enable |**PASS** |
|18|**Testing the squirrelmail** |Go to the browser and search **ip address/mywebmail** and login with user and send the mail and receive the mail |squirrelmail should work properly |**PASS** |
```sh
Thanks
Pravesh
```
