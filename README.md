# Daily learning🚀
该项目目的：  
督促每日积累  ✔  
记录学习心得  ✔  
记录每日学习内容，涉及范围如下：  
CTF  ✔  
内网学习  ✔  
代码审计   ✔  
每日文章学习总结  ✔
## 2020-11-28
### Moriarty Corp靶场攻略 - [原文链接](https://mp.weixin.qq.com/s/aSbrmWYU-zB41_h0Bf-51w)
#### 积累：
一次比较常规的内网靶场渗透(非域)，通过MSF开启socks代理，然后proxychains代理nmap进入内网扫描开放22端口主机，在对开放ssh服务的主机进行弱口令爆破  
这里也可以用上MSF的ssh扫描模块  
比如
```
auxiliary/scanner/ssh/ssh_version  扫描开放ssh服务的主机
auxiliary/scanner/ssh/ssh_login    口令猜解
```
#### 发散：
同靶场文章中发现有人用Netdiscover工具  
![image-20201129015921550](https://github.com/hui1314/Daily-learning/blob/master/images/image-20201129015921550.png)  
该工具有段描述说明DHCP对于该ARP探测工具有一定的影响，于是就去复习了下主机、端口扫描的原理，学习文章也放在下面了

#### Tips:
MobaXterm可以添加代理  
Nmap -sn -PR  
-PR：ARP Ping  
-sn：只进行主机发现，不进行端口扫描
#### 杂记:
git第一次推送
```
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:hui1314/Daily-learning.git
git push -u origin master
```
git自动换行转换问题
```
git config --global core.autocrlf false
最终解决：行末加两个空格
```
恢复到某个commit
```
git reset --hard cmmit_id
git push origin HEAD --force
```
#### 附上学习文章：
- [ssh_login模块实操](https://www.khow.me/blog/scanner-ssh-auxiliary-modules.html)
- [Metasploit常用辅助模块](https://www.dazhuanlan.com/2020/01/15/5e1e807451bca/)
- [扫描探测](https://www.freebuf.com/articles/network/105036.html)
- [端口扫描](https://nmap.org/man/zh/man-port-scanning-techniques.html)

## 2020-11-29
### 利用Avast 杀软自带组件Avdump转储lsass.exe进程 - [原文链接](https://mp.weixin.qq.com/s/bHDMTlY-YZxx9dS-MqQfRA)
AvDump.exe是Avast杀毒软件中自带的一个程序，可用于转储指定进程（lsass.exe）内存数据，因为它带有Avast杀软数字签名，所以不会被反病毒检测和查杀  
[AvDump复现文章](https://www.cnblogs.com/BOHB-yunying/p/14059179.html)
## 2020-11-30
内网渗透frp反向socks5代理  
[内网穿透工具frp](https://www.cnblogs.com/BOHB-yunying/p/12693675.html)