# X-UI
简体中文|[ENGLISH](./README_EN.md)  

> 声明：该项目仅供个人学习、交流，请遵守当地法律法规,勿用于非法用途;请勿用于生产环境  
> 声明：该项目已闭源，介意者请勿使用；如您需要开源代码，请附上您的Github Profile邮箱联系  

支持单端口多用户、多协议的 xray 面板，究极缝合怪    
通过免费的Telegram bot方便快捷地进行监控、管理你的代理服务  
&#x26A1;`xtls-rprx-vision`与`reality`快速入手请看[这里](https://github.com/FranzKafkaYu/x-ui/wiki/%E8%8A%82%E7%82%B9%E9%85%8D%E7%BD%AE)  
欢迎大家使用并反馈意见或提交Pr,帮助项目更好的改善  
如果您觉得本项目对您有所帮助,不妨给个star:star2:支持我  
或者你恰巧有购买服务器的需求,可以通过文末的赞助部分支持我~ 

# 文档目录  
- [功能介绍](#功能介绍)  
- [一键安装](#一键安装)  
- [效果预览](#效果预览)  
- [快捷方式](#快捷方式)  
- [变更记录](#变更记录)

# 功能介绍

- 系统状态监控
- 支持单端口多用户、多协议，网页可视化操作
- 支持的协议：vmess、vless、trojan、shadowsocks、shadowsocks 2022、dokodemo-door、socks、http
- 支持配置更多传输配置：http、tcp、ws、grpc、kcp、quic
- 流量统计，限制流量，限制到期时间，一键重置与设备监控
- 可自定义 xray 配置模板
- 支持 https 访问面板（自备域名 + ssl 证书）
- 支持一键SSL证书申请且自动续签
- Telegram bot通知、控制功能
- 更多高级配置项，详见面板 


# 一键安装
在安装前请确保你的系统支持`bash`环境,且系统网络正常  

&#x26A1;从原版升级也可使用该命令，数据不会丢失&#x26A1;

```
bash <(curl -L https://raw.githubusercontent.com/z4979511/x-ui/main/install.sh)

```    
For English Users,please use the following command to install English supported version:  
```
bash <(curl -L https://raw.githubusercontent.com/z4979511/x-ui/main/install_en.sh)
_en.sh)
```
如需安装指定的版本,可以在上述命令中指定版本号,如指定版本为`0.3.4.4`,安装命令如下：    
```
bash <(curl -L https://raw.githubusercontent.com/z4979511/x-ui/main/install.sh) 0.0.1  
```

正在启用 BBR 加速...

(standard_in) 1: syntax error
您的内核版本不支持 BBR（需要 4.9 及以上），BBR 加速无法启用。
表明你的服务器内核版本不支持 BBR 加速。BBR 是 Linux 4.9 及以上版本的功能，如果你的内核版本低于 4.9，就无法启用 BBR。
 需要对系统进行升级

一键更新服务器内核（用于 Debian 和 Ubuntu 系统）
sudo apt-get update && sudo apt-get install linux-image-$(uname -r | sed 's/[a-zA-Z]*-[0-9]*-//')-generic
或者按照下面的代码分别输入进行更新
 更新包索引：1.先运行下面代码
 
 sudo apt-get update
 
在运行下面代码 安装新的内核版本（如果你的当前内核版本较低）：

sudo apt-get install linux-image-$(uname -r | sed 's/[a-zA-Z]*-[0-9]*-//')-generic

等待更新
------------------------------------

一键更新服务器内核（用于CentOS 系统）
sudo yum update -y && sudo yum install kernel -y && sudo reboot

或者按照下面的代码分别输入进行更新
 在 CentOS 上安装内核更新的正确步骤：
1.运行以下命令来更新系统：
sudo yum update

2.安装新内核： CentOS 使用 yum 包管理工具，安装内核的命令为：
sudo yum install kernel

3.重启系统： 安装完成后，重启系统以便使用新内核：
sudo reboot

4检查当前内核版本： 重启后，你可以使用以下命令来检查当前内核版本：
uname -r

这样，你就可以在 CentOS 系统上安装并更新内核了

确认 BBR 是否已启用：
运行命令sysctl net.ipv4.tcp_congestion_control


如果反馈出现是：

net.ipv4.tcp_congestion_control = bbr

说明开启成功


# 效果预览  
`面板使用`:  
<details>
<summary><b>点击查看效果预览</b></summary>  
  
![image](https://user-images.githubusercontent.com/38254177/180629631-f76a05c8-ecf0-4685-bbc7-a7058747d213.png)  
![image](https://user-images.githubusercontent.com/38254177/180629662-b7a325fc-1ebb-47c9-992c-1e7c758a326b.png)


 </details>  
 
`Bot使用`:  
<details>
<summary><b>点击查看效果预览</b></summary>  
  
![image](https://user-images.githubusercontent.com/38254177/178551055-893936b7-b75f-4ee8-a773-eee7c6f43f51.png)  
 
</details>  

`流量提醒`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/180039760-dc987a30-e21c-49a3-8e03-19666566a822.png)

</details>  

`SSH提醒`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/180040129-2ec1a7c0-abd3-41dc-aab0-8cd22415c943.png)

</details>  

`限额提醒`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/180040521-af6e9ef8-d7e5-44e8-834e-25b3b8e3e1b5.png)

</details>  

`到期提醒`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/180041690-90ca4b1f-3a2d-470b-bc0c-eca9261a739a.png)

</details>  

`登录提醒`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/180040913-b8bf2fe1-6fc1-43ab-a683-ae23db1866b2.png)  
![image](https://user-images.githubusercontent.com/38254177/180041179-a5f4cd52-a1ba-4aa9-abb2-b94e36722385.png)

</details>  

`用户速览`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/230761101-20431dd7-5bce-489e-9139-0ceb9ab9a2dc.png)

</details>  

`用户查询`:  
<details>
<summary><b>点击查看效果预览</b></summary> 
  
![image](https://user-images.githubusercontent.com/38254177/230761252-c283c02d-82a4-46ce-a180-dfab4048180d.png)

</details>  



# 快捷方式
安装成功后，通过键入`x-ui`进入控制选项菜单，目前菜单内容：
```
  x-ui 面板管理脚本
  0. 退出脚本
————————————————
  1. 安装 x-ui
  2. 更新 x-ui
  3. 卸载 x-ui
————————————————
  4. 重置用户名密码
  5. 重置面板设置
  6. 设置面板端口
  7. 查看当前面板设置
————————————————
  8. 启动 x-ui
  9. 停止 x-ui
  10. 重启 x-ui
  11. 查看 x-ui 状态
  12. 查看 x-ui 日志
————————————————
  13. 设置 x-ui 开机自启
  14. 取消 x-ui 开机自启
————————————————
  15. 一键安装 bbr (最新内核)
  16. 一键申请SSL证书(acme申请)
 
面板状态: 已运行
是否开机自启: 是
xray 状态: 运行

请输入选择 [0-16]: 
```
# 配置要求  
## 内存  
- 128MB minimal/256MB+ recommend  
## OS  
- CentOS 7+
- Ubuntu 16+
- Debian 8+

# 变更记录   
- 2023.07.18：随机生成Reality dest与serverNames,去除微软域名;细化sniffing配置  
- 2023.06.10：开启TLS时自动复用面板证书与域名;增加证书热重载设定;优化设备限制功能  
- 2023.04.09：支持Reality;支持新的telegram bot控制指令  
- 2023.03.05：支持用户到期时间限制;随机用户名、密码与端口生成
- 2023.02.09：支持单端口内用户流量限制与统计；支持VLESS utls配置与分享链接导出  
- 2022.12.07：添加设备并发限制;细化tls配置,支持minVersion、maxVersion与cipherSuites选择    
- 2022.11.14：添加xtls-rprx-vision流控选项;定时自动更新geo与清除日志  
- 2022.10.23：实现全英文支持;增加批量导出分享链接功能；优化页面细节与Telegram通知    
- 2022.08.11：实现Vmess/Vless/Trojan单端口多用户；增加CPU使用超限提醒  
- 2022.07.28：增加acme standalone模式申请证书;增加x-ui自动保活机制;优化编译选项以适配更多系统  
- 2022.07.24：增加自动生成面板根路径，节点流量自动重置功能，设备IP接入变化通知功能
- 2022.07.21：增加节点IP接入变化提醒，Web面板增加停止/重启xray功能，优化部分翻译
- 2022.07.11：增加节点到期提醒、流量预警策略，增加Telegram bot节点复制、获取分享链接等
- 2022.07.03：重构Telegram bot功能，指令控制不再需要键盘输入;增加Trojan底层传输配置
- 2022.06.19：增加Shadowsocs2022新的Cipher，增加节点搜索、一键清除流量功能
- 2022.05.14：增加Telegram bot Command控制功能，支持关闭/开启/删除节点等
- 2022.04.25：增加SSH登录提醒、面板登录提醒
- 2022.04.23：增加更多Telegram bot提醒功能
- 2022.04.16：增加面板设置Telegram bot功能
- 2022.04.12：优化Telegram Bot通知提醒
- 2022.04.06：优化安装/更新流程，增加证书签发功能，添加Telegram bot机器人推送功能

