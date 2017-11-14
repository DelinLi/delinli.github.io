##  [Shadowsocks](https://github.com/shadowsocks)  
**用于作者本人同朋友间分享,也欢迎参考**

###  背景知识
shadowsocks是一种socks5的代理，而socks5的代理服务器则是把你的网络数据请求通过一条连接你和代理服务器之间的通道，由服务器转发到目的地。你没有加入任何新的网络，只是http/socks数据经过代理服务器的转发送出，并从代理服务器接收回应。    

###  服务器端
这里我们所用的**代理服务器**位于日本。从16年8月至今运行良好，稳定性强。已经配置好，不需要额外操作。     
账号信息示例：
<pre>
IP:XXX.XXX.XXX.XXX 
Port: XXX
Encryption: aes-256-cfb
Password: XXXXX
</pre>     
    
###  客户端下载
你只需要在自己的手机和电脑下载客户端[https://shadowsocks.org/en/download/clients.html]( https://shadowsocks.org/en/download/clients.html)。建议回国的尽可能在国外设置妥当尽量。如果在国内这些软件很可能墙，可以通过百度云盘分享（*存在版本略旧的可能性*）来下载安装：
1. **Mac**，  百度云盘分享链接: [https://pan.baidu.com/s/1c2IY5Ao](https://pan.baidu.com/s/1c2IY5Ao)  密码: q31q    
2. **Iphone**， 需要在APP store中购买shadowrocket应用作为客户端，价格为6RMB。   
3. **Win**, 百度云盘分享链接: [https://pan.baidu.com/s/1c2tWi0g](https://pan.baidu.com/s/1c2tWi0g)  密码: iart    
4. **Andriod**, 百度云盘分享链接: [https://pan.baidu.com/s/1kVL2jqf](https://pan.baidu.com/s/1kVL2jqf)  密码: 3ipy 


 

####  启用时的两种模式：
**Auto Proxy Mode**: shadowsocks会根据他自己的GFWList选择是否走**代理服务器**，这极大的保证了在国内访问国内网站的速度的同时可以访问Blocked 网站。    
**Global Mode**: 但是难免GFWList会有遗漏，这时你需要选择**Global Mode**模式。此时所有的数据都会经过**代理服务器**。在用Mac的Mail发送邮件时往往需要打开此模式。    


#### Mac上设置示例：    
![OnMac](/pic/shadowsocks.mac.png =100x140)    
进入Sever Preferences,填写账号信息即可。   
####  Iphone 上设置示例：
![OnIphone](/pic/shadowsocks.iphone.jpeg =120x200)     
点击右上侧➕即可进入设置页面，填写必填选项即可。    

####  DropBox客户端的设置    
作为少有的需要额外设置的软件--DropBox需要在其Preferences->Network中更改设置如下：    
*频繁的开关shadowsocks客户端或更换模式会导致Dropbox停止同步，此时只需重启dropbox*    
![OnMacDropbox](/pic/Dropbox_shadowscokets.png =200x140)

