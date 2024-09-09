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

强烈推荐选择东京节点，延迟较低

![3](https://github.com/user-attachments/assets/9d911a99-e4c7-41ad-8f77-2ad550e204d6)

系统 选择CentOS，方便后续脚本的部署
![4](https://github.com/user-attachments/assets/041c9b9f-980a-4f45-89a1-6c121961557f)

常规继续往下选

![5](https://github.com/user-attachments/assets/6d34be8e-7b37-4ba4-8059-64a3566b7a98)

取消自动备份
![6](https://github.com/user-attachments/assets/fd685b1b-dfe8-4040-8712-1a47d7aca417)

可以看到已经变成5刀一个月了，等待部署完毕就OK啦。

# 第二部 部署SSR服务端
服务端协议就不过多介绍，按照步骤走即可，感兴趣的小伙伴可自行了解

首先使用ssh工具链接vps
接下来关闭防火墙

```# 查看防火墙状态命令：
firewall-cmd --state
# 停止firewall命令：
systemctl stop firewalld.service
# 禁止firewall开机启动命令：
systemctl disable firewalld.service
```

这样就关闭了防火墙，否则从外网访问端口可能会失败

脚本部署，直接执行命令即可

```
yum -y install wget

wget -N — no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh
```

接下来进行部署
```
bash ssr.sh
```
选择1安装SSR，接下来建议全部按照默认，猛猛回车就完事儿了

![image](https://github.com/user-attachments/assets/8e4f4533-87e5-4299-9e37-6c47591a733d)
以上为演示图片，vps已注销

# 3 windows系统下的链接











