2021/1/11\
通知：活动列表有所变化，已部署的朋友请执行最新的更新一键更新脚本命令，教程在下方第四部分第3条。

***

# 《京东薅羊毛》一键部署脚本 For Linux
## 用途：通过参与京东商城的各种活动白嫖京豆，目前每个账号日均100~200京豆
## 适用系统：Ubuntu 20 & CentOS 8 _简体中文_
- Ubuntu正在完善中,但现在仍可用，建议优先使用Ubuntu系统
- CentOS本人测试环境为最新CentOS 8.3，不适用7及更低版本，系统装完后联网即可，如果是最小化安装，请通过SSL方式进入到终端

***

## 原作者GitHub项目地址：
### https://github.com/lxk0301/jd_scripts  #此项目核心JavaScript京东活动脚本原作者
### https://github.com/EvineDeng/jd-base   #此项目Linux环境原作者，已授权，在其Issues有分帖
    
***

# 下面进入正题，部署教程共三步，请认真阅读下面的内容
    
***

## 一、环境一键部署
### Ubuntu
    wget --no-check-certificate -O install.sh https://raw.githubusercontent.com/SuperManito/JD-FreeFuck/main/install-ubuntu.sh && chmod +x install.sh && bash install.sh
### CentOS
    wget --no-check-certificate -O install.sh https://raw.githubusercontent.com/SuperManito/JD-FreeFuck/main/install-centos.sh && chmod +x install.sh && bash install.sh
_注：请根据你的操作系统，选择上面对应的命令复制到终端并执行_\
\
__附：如果没有科学上网方式可为Github添加解析记录，命令如下。__

    echo "199.232.96.133 raw.githubusercontent.com" >> /etc/hosts
    
***

## 二、接下来我们需要您京东账户的“身份证”，它由`Cookie部分内容`组成，在[Wiki](https://github.com/SuperManito/JD-FreeFuck/wiki/GetCookies)有详细的图文教程，请点击链接自行获取

***

## 三、配置脚本
### 根据[Wiki](https://github.com/SuperManito/JD-FreeFuck/wiki/GetCookies)教程将获得的`Cookie部分内容`填入下面命令中的“双引号”内，复制完整命令到终端并执行。（必填）
    sed -i '27c Cookie1=""' /home/myid/jd/config/config.sh
_参考命令：sed -i '27c Cookie1="pt_pin=xxxxx;pt_key=xxxxxxx;"' /home/myid/jd/config/config.sh_
\
#### 附1.如果需要同时运行多个账号（最多6个），请按顺序填入下面命令中的“双引号”内，用几个就执行几条对应的命令。（选择步骤）

    sed -i '28c Cookie2=""' /home/myid/jd/config/config.sh
    sed -i '29c Cookie3=""' /home/myid/jd/config/config.sh
    sed -i '30c Cookie4=""' /home/myid/jd/config/config.sh
    sed -i '31c Cookie5=""' /home/myid/jd/config/config.sh
    sed -i '32c Cookie6=""' /home/myid/jd/config/config.sh
#### 附2.如果需要使用微信消息推送功能，将`SCKEY`填入下面命令的”双引号“内，复制完整命令到终端并执行。（选择步骤）

    sed -i '70c export PUSH_KEY=""' /home/myid/jd/config/config.sh
_注：详细教程请访问[Server酱官网](http://sc.ftqq.com/3.version/)_
#### _到此部署就结束了，是不是很快OvO_

***

## 四、如何使用与更新
### 1.如何运行脚本开始白嫖京豆？
    bash run-all.sh
### 2.如何更新京东活动脚本？
    bash manual-update.sh
_注：建议每次执行脚本前或者几天内执行一次，京东活动变化无常。_
### 3.如何更新一键更新脚本？
    wget --no-check-certificate -P /home/myid/jd -N https://raw.githubusercontent.com/SuperManito/JD-FreeFuck/main/manual-update.sh && chmod +x manual-update.sh
### 4.一键部署后遇到报错怎么办？
- 多次执行`manual-update.sh`更新脚本尝试
- 删除/home/myid整个目录后重新一键部署
_注：如果仍然报错导致项目无法正常运作，说明是原作者环境库的问题，请换个时间重试。_
    
***

## 五、脚本定义
`run-all.sh`为本人编写的一键执行所有活动脚本，`manual-update.sh`为本人编写的一键更新脚本，其余均为原作者脚本。
## 六、项目需知
### 1.该项目运行主目录为/home/myid/jd
### 2.为了保证脚本的正常运行，请不要更改任何组件的位置以避免出现未知的错误
### 3.run-all.sh为执行所有活动脚本，仍可通过原作者 bash jd.sh 命令查看教程并执行特定活动脚本
### 4.执行脚本期间可能会卡住或运行挂机脚本，可通过命令 Ctrl + Z/C 跳过继续执行剩余活动脚本
### 5.由于京东活动一直变化所以会出现无法参加活动等正常现象，可手动更新JavaScript活动脚本
### 6.如果需要更新核心JavaScript活动脚本，请执行 bash manual-update.sh 命令进行一键更新即可
### 7.之前填入的Cookie部分内容具有一定的时效性，若提示失效请根据教程重新获取并通过命令手动更新
### 8.因为本人每天也在使用，遇到错误会在第一时间解决，遇到任何与部署和环境相关的问题都可访问本项目寻求帮助





