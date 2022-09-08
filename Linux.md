# 在VMware安装Ubuntu系统

> 因为在去年大一时的很多工作室招新中都有虚拟机作为小题目，所以当时就下载了VMware并且使用Ubuntu系统映像安装好了。不过并没有什么实际的使用，也没有很好的保存文件路径，导致无限吃灰(
>
> 这次属于再了解过程，主要了解Linux系统下的命令行操作，以及如何在本地和虚拟机服务器进行连接，后续的服务器相关知识也会慢慢了解。

![image-20220908092816357](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908092816357.png)

![image-20220908092832104](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908092832104.png)

![image-20220908113956016](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908113956016.png)

![image-20220908114107855](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908114107855.png)

![image-20220908114126474](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908114126474.png)

```sh
#!/bin/sh

echo "Into ty/test"
cd /home/ty/test
echo "Add new"
mkdir new
cd new
mv /home/ty/test/testNew newTest 

```

## Linux常见命令

1. cd 切换当前目录 

   1. cd /home/ty 
   2. cd ../返回父级目录
   3. cd (不带参数时，表示返回主目录)

2. pwd 显示当前目录

3. ==ls(常用)== :列出文件和文件夹

   1. ls -l 列出当前目录下所有项 ，-l 参数表示详细模式
   2. ls -ld /opt ，其中 -ld表示列出一个目录本身，而非目录下的子项

4. mkdir 创建目录 (加-p 可以一次性创建多级目录)

5. rmdir 删除非空目录**(不常用)**

6. rm 

   1. rm -rf abc 删除abc目录连同所有子项
   2. rm -rf abc/* 删除abc目录下所有子项
   3. rm -rf /*  : ) 删库跑路

7. cp 复制文件或者目录

8. mv 移动文件或目录 (重命名)，即 move 

   mv hello helloworld

...tar useradd userdel groupadd chmod sudo等等

## SSH服务器

> 使用XShell和Xftp实现远程连接服务器，并可视化文件传输
>
> > 遇到问题：XShell和Xftp要求最新版，无法启动。
> >
> > 解决：在CSDN上找到一个脚本文件，能以管理员权限启动，能修改系统时间让程序正常运行
> >
> > ````shell
> > @echo off
> > setlocal EnableDelayedExpansion
> > color 3e
> > title Xshell启动器
> > %1 mshta vbscript:CreateObject("Shell.Application").ShellExecute("cmd.exe","/c "^&chr(34)^&"%~0"^&chr(34)^&" ::","%cd%","runas",1)(window.close)&&exit
> > 
> > ::改成你的xshell启动路径
> > set XSHELL="D:\NetSarang\Xshell 6\Xshell.exe"
> > set cTime=%date:~0,4%-%date:~5,2%-%date:~8,2%
> > date 2020-12-31
> > echo ---------------------------------------------------------------
> > echo Xshell启动器
> > echo Author	: PJW
> > echo Time	: 2022/04/20
> > echo Ver	: V1.0
> > echo ---------------------------------------------------------------
> > echo 启动软件中，完成后自动关闭窗口...
> > start ""  %XSHELL%
> > choice /t 1 /d y /n >nul
> > date %cTime%
> > exit
> > 
> > ````

![image-20220908135702170](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908135702170.png)

![image-20220908141727825](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908141727825.png)

![image-20220908141901361](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908141901361.png)

### 以root方式登录

![image-20220908143630298](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908143630298.png)

## vim文本编辑器

![image-20220908144628066](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908144628066.png)

> vim abc.txt :如果是第一次使用，则会新建![image-20220908144859312](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908144859312.png)
>
> 按键:
>
> > i: 编辑模式
> >
> > ESC:命令模式
> >
> > > :wq :保存退出
> > >
> > > q: 退出
> > >
> > > q!:强制退出

## 运行java程序

![image-20220908151747990](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908151747990.png)

> 打包成可运行的jar包，使用java -jar xxx.jar即可运行

## 查看进程

![image-20220908154350860](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908154350860.png)

## VSCode Remote-ssh插件连接

![image-20220908155950621](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908155950621.png)

![image-20220908160246965](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908160246965.png)

![image-20220908161241321](C:\Users\谭宇乔\Desktop\md\Linux.assets\image-20220908161241321.png)

# 总结

> Linux系统主要用于架构服务器，在企业中应该比较常见，目前来说，也仅仅是针对命令行等进行了一个粗略的入门，并且对这方面并没有表现出需求，或许在后面的学习中会用到。

