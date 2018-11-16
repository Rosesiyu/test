一、安装 iperf：

1.1 对于 windows 版的 Iperf，直接将解压出来的 iperf.exe 和cygwin1.dll 复制到%systemroot%目录即可；

``` 注 ： %systemroot% 的 具 体 目 录 可 以 通 过 cmd —>echo %systemroot% 查看```

1.2 对于 linux 版的 Iperf，请使用如下命令安装 ： 
```
gunzip -c iperf-<version>.tar.gz | tar -xvf - 
cd iperf-<version>.
/configure 
make 
make install
```
1.3 移动端，安装apk

二、iperf的使用：

1、在windows上面安装以及配置iperf环境

2、移动端安装iperf软件

3、以管理员身份运动cmd

4、PC端输入iperf命令

5、移动端输入iperf命令

上行测试：

PC端：```iperf -s```

手机端：```iperf -c 192.168.88.253 -i 2 -t 100 -w 1M```  (输入PC端的ip)

下行测试：

PC端：```iperf -c 192.168.88.185 -i 5 -t 100 -w 1M```     (输入手机端的ip)

手机端：```iperf -s```

其中-w表示TCP window size，host需替换成服务器地址，-i sec 以秒为单位显示报告间隔，-t 测试时间（秒）
