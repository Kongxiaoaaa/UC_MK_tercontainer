<p align="center">Dream With Me</p>        
<p align="center">(>_×)</p> 

-----------      

![](https://img.shields.io/github/stars/Moe-hacker/termux-container)
![](https://img.shields.io/github/forks/Moe-hacker/termux-container)
![](https://img.shields.io/github/license/Moe-hacker/termux-container)
![](https://img.shields.io/badge/language-shell-green)
### 关于：      
很久很久以前(好像也就一年前？)，有一只萌新由于tmoe的容器路径太长，自己懒得输，于是写了千行代码，终于可以把容器直接安装在/data里了，就有了这个项目。      
可惜他目前已经润到docker去了。docker pull&docker run真是太好用了😋。         
特色：      
精心设计的输出，虽然你若不喜欢可以关掉。。。。。。      
默认开启mount namespace，就算容器未被卸载也不会删除容器中挂载的系统文件。      
尽可能多的开启namespace隔离容器，不过大部分内核默认支持的namespaces有限。      
在容器中创建dev,sys和proc三个目录，/dev下磁盘设备未被映射，最起码能防手贱。。。      
rm -rf /*在/sdcard未被挂载时只会删除容器本身，宿主机由于已被隔离不会造成损坏(测试于pixel3,A12,chroot-unshare模式，不过建议别试，真寄了我也没办法)            
### 截图：      
脚本大概长这样(懒得上传中文版截图了，凑活看吧):      
![](https://github.com/Moe-hacker/termux-container/raw/main/.Screenshots/Screenshot_20221012-185314_Termux.png)
![](https://github.com/Moe-hacker/termux-container/raw/main/.Screenshots/Screenshot_20221012-185209_Termux.png)
《关于作者为了截图特地安装了自己写的脚本这回事》      
《关于作者本人其实是tmoe老粉，甚至编译10U内核都用的tmoe这回事》
### 准备工作：      
说了这么多，你是不是想试着运行一下这个项目？      
运行前准备：      
- 一部安卓手机，什么你说你是🍎？爬！！！！
- Termux
- 足够的剩余空间，你如果非得装10个甚至9个容器还要GUI的话小姐姐怕是没地方了。。。      
- 一点Linux知识
- 🧠      
### 安装：      
最新源码懒得打包上传release了，想用最新的话：      
```sh
git clone https://github.com/Moe-hacker/termux-container
cd termux-container/package-zh
chmod -R 755 DEBIAN
chmod 777 data/data/com.termux/files/usr/bin/container
dpkg -b . ~/termux-container.deb
apt update
apt install ~/termux-container.deb
```
不过如果用release，下载下来apt install ./xxxx.deb也行。
最新源码修复没有parrot选项问题，添加一个安装动画，不再更新。      
### 创建并运行容器：     
- 运行container -c
- 选择容器类型，有root用chroot-unshare，没有就用proot。      
- 添加一个普通用户，输入用户名密码。      
- 按提示输入容器路径。      
- 如果是chroot-unshare容器，会问你是否使用镜像文件，一般直接选择否。      
- 选择获取rootfs的方式。
- 安装，等。。。。。。。      
- 运行container -run进入容器。      
注：运行chroot-unshare容器崩溃的，可使用container -l运行普通chroot容器。虽然不安全但起码能用？      
### 自定义：      
运行container -s编辑配置文件，有注释这里就不细说了，懒。。。      
### 其他用法：      
```
 container                   #打开菜单
 container -run              #运行容器
 container -l                #运行容器(传统模式) *仅供chroot容器
 container -c                #创建一个新容器
 container -S                #切换容器
 container -s                #设置
 container -r                #删除一个容器
 container -m                #挂载镜像文件 *仅供chroot容器
 container -bk               #备份容器
 container -R [备份文件]     #还原容器
 container -e [函数名]       #执行内置函数 *仅供调试
 container -v                #版本信息
 container -U                #批量删除容器&卸载此脚本
```
### 关于作者：      
高中生，男的，不是🍥用户，不女装(有这想法的爬)，性取向正常。      
等下好像重点不是这个。。。。。。。      
接触Linux时长两年半，真ikun，不是小黑子。      
这都是什么东西啊喂！！！！！！      
算了就这些吧，有号的别白嫖，记得给星标啊(才不是求大家呢！！！！)

-------     
<p align="center">Do Great Things</p>       
