1、对手机进行截图保存到电脑：
```commandline
adb shell screencap -p /sdcard/screenshot.png
adb pull /sdcard/screenshot.png E:\Picture\VM2\Cold_1.png
```
2、查找当前文件夹下的子文件夹
```adb shell ls /storage```
```adb shell ls /storage/sdcard/Pictures/```

3、将设备中的文件复制到PC

```adb pull /storage/sdcard/Pictures/001.png```

4、删除手机中的文件adb

```adb shell rm /storage/sdcard/Pictures/001.png```

5、使用Logcat导出手机日志
```
   adb logcat -c 清除log缓存
   adb logcat -v threadtime >001.logcat（命令不停止日志会一直打印）
   adb logcat -d >001.logcat（一次打印所有日志，不会继续打印）
```
6、将脚本文件复制到手机
```adb push test.py /mnt/sdcard/```

7、运行脚本文件
```adb shell monkey -v -f /mnt/sdcard/test.py 1```

8、启动指定应用程序
```
   adb shell am start -n Package/Activity
   adb shell  am start -a android.intent.action.VIEW -d /sdcard/Movies/zhanlang.mp4 -n com.android.gallery3d/.app.MovieActivity
```
9、应用已安装，查看包名和类名

1）启动要查看的程序；
    
2）命令行输入：```adb shell dumpsys window w |findstr \/ |findstr name="" ```
    
10、设置文件的执行权限
```
adb shell
chmod 777 文件名
```
11、根据hid三个字符匹配列举设备 
```
adb shell
ls /dev/hid* 
```
12、adb shell getprop获取Android系统属性
```
    ro.build.version.incremental
    ro.build.display.id
    ro.build.inc.ver.inner
    build_num
```
13、```adb shell dumpsys |grep DUMP``` 查看哪些service信息可以dump

```adb shell dumpsys SurfaceFlinger```获取SurfaceFlinger信息
    
```adb shell dumpsys display```获取dispaly manager信息
    
```adb shell dumpsys battery```查看电池信息

```adb shell dumpsys activity（adb shell ps）```获取设备中正在运行的程序

14、```adb shell getevent```  获取坐标

```adb shell getevent -p```

15、```adb shell dmesg```打印内核调试信息

16、设备重启、关机

```adb reboot```重启

```adb reboot bootloader```重启到bootloader，即刷机模式

```adb reboot recovery```重启到recovery，即恢复模式

```adb shell reboot -p``` 关机

17、分辨率相关```adb shell wm ```
```
adb shell wm size 720x1280设置分辨率
adb shell wm size查看分辨率
adb shell wm -h
usage: wm [subcommand] [options]
       wm size [reset|WxH]
       wm density [reset|DENSITY]
       wm overscan [reset|LEFT,TOP,RIGHT,BOTTOM]
```
18、adb 模拟滑动、按键、点击、输入

输入字符：```adb shell input text "NAME"  ```
```
adb shell input text “|&”使用转义字符输入特殊字符（每个特殊字符前都需要加转义字符）
adb shell input text “ &&&&hhd&&&”字符前加一个空格输入特殊字符
adb shell input text “|h” 输入‘\’ 
```
按键：```adb shell input keyevent [options]```
```
adb shell input keyevent 26 模拟点击power键
adb shell input keyevent 82 向设备发送屏幕解锁命令
adb shell input keyevent 62 输入空格
```
点击：```adb shell input tap [x y]```

滑动：```adb shell input swipe [x1 y1 x2 y2]```

19、wifi相关

1）开启关闭wifi
```
adb shell    进入shell指令模式
su           进入ROOT指令模式
svc wifi enable打开WIFI指令
svc wifi disable关闭WIFI指令
```
2)查看wifi密码

```adb shell cat /data/misc/wifi/*.conf ```

3）获取机器MAC地址

```adb shell cat /sys/class/net/wlan0/address```

4）查看wifi状态
```
adb shell dumpsys wifi
```
20、service相关 ```adb shell service```

查看service列表：```adb shell service list```

检查service是否存在：```adb shell service check```

使用service：```adb shell service call ```

21、多设备使用adb，使用参数-s指定设备

查看已连接设备：```adb devices```

获取序列号：```adb get-serialno```

22、等待设备连接:```adb wait-for-device```

23、记录无线通讯日志:```adb shell logcat -b radio```

24、进程相关

查看进程列表：```adb shell ps ```

查看某进程的pid号：```adb shell ps | grep kodi```

杀死一个进程：```adb shell kill [pid] ```

查看指定进程状态：```adb shell ps -x [PID] ```

25、查看当前内存占用

```adb shell cat /proc/meminfo```

26、grep显示前后几行信息

```grep -C 5 foo file``` 显示file文件里匹配foo字符串那行及上下5行

```grep -B 5 foo file``` 显示file文件里匹配foo字符串那行及前5行

```grep -A 5 foo file``` 显示file文件里匹配foo字符串那行及后5行

27、清除用户数据
```
adb reboot bootloader
fastboot -w
```
28、DDMS截图=screencap

uiautomator截图=设备显示

29、
```
adb shell cat /sys/class/power_supply/battery/capacity
adb shell cat /sys/class/power_supply/battery/status
adb shell cat /sys/class/power_supply/battery/uevent
```
30、启动app：

```adb hell  am start -a android.intent.action.VIEW -d /sdcard/Movies/zhanlang.mp4 -n com.android.gallery3d/.app.MovieActivity```

31.获取CPU序列号：```adb shell cat /proc/cpuinfo```

32.安装APK：```adb install <apkfile> ```

33.保留数据和缓存文件，重新安装apk：```adb install -r <apkfile> ```

34.保留数据和缓存文件，卸载app：```adb uninstall -k <package> ```

35.安装apk到sd卡：```adb install -s <apkfile>``` 

36.卸载APK：```adb uninstall <package> ```

37.卸载rom系统自带apk:
```
adb shell 
cd data/app
rm app.apk
```
38.查看设备cpu和内存占用情况：```adb shell top```

39.查看占用内存前6的app：```adb shell top -m 6```

40.刷新一次内存信息，然后返回：```adb shell top -n 1```

41.查询各进程内存使用情况：```adb shell procrank```

42.查看后台services信息：```adb shell service list ```

43.查看IO内存分区：```adb shell cat /proc/iomem```

44.将system分区重新挂载为可读写分区：```adb remount```

45.列出目录下的文件和文件夹，等同于dos中的dir命令：```adb shell ls```

46.进入文件夹，等同于dos中的cd 命令：```adb shell cd <folder> ```

47.重命名文件：```adb shell rename path/oldfilename  path/newfilename ```

48.删除system/avi.apk：```adb shell rm /system/avi.apk```

49.删除文件夹及其下面所有文件：```adb shell rm -r <folder> ```

50.移动文件：```adb shell mv path/file  newpath/file```

51.设置文件权限：```adb shell chmod 777 /system/fonts/DroidSansFallback.ttf```

52.新建文件夹：```adb shell mkdir path/foldelname```

53.查看文件内容：```adb shell cat <file> ```

54.查看bug报告：```adb bugreport```

55.获取设备名称：```adb shell cat /system/build.prop```

56.查看ADB帮助：
```
adb help
adb get-product
```
57.跑monkey：```adb shell monkey -v -p your.package.name 500 ```

58.cpu使用情况
```
top -m 10 -s cpu
dumpsys meminfo Bilibili，
```
58.RSS值:```adb shell ps | find "assistant"```
