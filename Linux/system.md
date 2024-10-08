# Linux系统使用过程总结

<a href="top">

## 目录

[1. 软件下载](#j1)

[2. 指令相关](#j2)

[3. 磁盘扩容](#j3)


---

### <span id="j1">软件下载</span>

sudo apt-get install
高版本可以使用
sudo apt install

默认下载源有时候下载东西比较慢,你可以手动切换下载源
应用程序-软件与更新-下载自其他,可以选择其他下载源如阿里
之后sudo apt-get update更新一下软件列表
然后再下载你所需要的东西就可以


### <span id="j2">指令相关</span>

---
命令 | 描述
---|---
apt| 安装命令|
dpkg |当你下载了软件的deb包，在对应路径输入dpkg -i 包名安装
ldd |显示可执行模块依赖
df |查看磁盘空间
mount |挂载
netstat-a|查看端口占用情况
chmod -R  777 |将文件下所有文件夹及文件赋权


### <span id="j3">磁盘扩容</span>
<br>
在安装QT时提示磁盘容量不足
<br>首先修改虚拟机设置里的磁盘容量(要将虚拟机关机)
<br>之后打开虚拟机,安装一下gparted(可视化修改磁盘配置可以避免命令行出错)
<br>找到你要扩的盘符右键调整大小在上方对某个分区进行扩容
<br>如果遇到我这种情况:分区只读
<br>右键只读的分区的信息有“挂载于”，将对应路径使用remount重新挂载并且赋予读写权限

<br>

```cpp
sudo mount -o remount -rw /
sudo mount -o remount -rw /var/snap/firefox/common/host-hunspell  
```

20240930

<br>


[回到顶部](#top)



