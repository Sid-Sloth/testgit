# ubantu开机启动指定应用程序设定步骤
## __1.__准备需执行服务程序
以简单程序为例(/home/zyl/zyl/code/hello\_server.py):<br>
if \__name__ == '\__main__':<br>
&nbsp;&nbsp;&nbsp;&nbsp;while True:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;print 'hello server'<br>
## __2.__编写sh可执行脚本
脚本名start_server.sh(/home/zyl/zyl/code/start\_server.sh)，脚本内容为：<br>
python /home/zyl/zyl/code/hello\_server.py
## __3.__设置程序开机自启动
>* 打开ubantu终端，执行$sudo vim /etc/rc.local
>* 在rc.lcoal文件最后一条语句(exit 0)上一行添加bash /home/zyl/zyl/code/start_server.sh
>* 保存rc.local
## __4.__验证程序自启动是否成功
>* 重启ubantu系统($reboot)
>* 查看启动的hello\_server.py应用程序($ps -aux | grep hello\_server.py),执行命令后可以看到运行的应用程序hello_server.py
## __参考__
http://www.mryu.top/os/231.html<br>
https://blog.csdn.net/soonfly/article/details/72876001<br>
