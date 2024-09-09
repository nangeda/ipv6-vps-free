# ipv6-vps-free
如何通过ipv6实现校园网免流（速通版）

学校校园网每个月只有免费的40g流量，超额部分购买居然要1元1g，how dare you！作为计算机专业的穷哥们要被气昏了，且网上一些教程有点落后，或者根本实现不了，遂结合网上的帖子以及自己的经验整理出个简单版。。。

# 前期准备工作以及成本
首先了解一下工作原理，首先校园网使用ipv6访问ipv6的网站是免费的，但是我们常用的一些网站都是使用的ipv4，如果使用纯ipv6的话是访问不了的，所以我们就要找到一台同时拥有ipv4和ipv6的vps做中转，这样可以使用本地ipv6访问vps，通过
vps的ipv4代理上网，然后在通过ipv6将数据传回本地，便可实现免费上网啦。

成本：一台日本的vps，10美元可用4个月，测试过4个人同时用是可以保证看视频不卡的。  大概5r/人/月。
结果: 免费使用校园网and网络附带魔法

![1](https://github.com/user-attachments/assets/dd5920cf-7a1e-4b95-babf-0ad0c21cf5aa)

# 第一步 购买VPS
推荐选能找到最便宜vps  [vurtl](https://www.vultr.com/?ref=9652363)

平台有很多常驻活动（但是我没找到）常驻活动有冲10刀送10刀，够用四个月
注册完毕后开始购买服务器流程
![2](https://github.com/user-attachments/assets/c6ae92d9-cec1-4cb4-9642-fb229aa946a0)

![3](https://github.com/user-attachments/assets/9d911a99-e4c7-41ad-8f77-2ad550e204d6)
