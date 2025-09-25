mac抓包工具：[Charles](https://www.charlesproxy.com/download/latest-release/)---青花瓷
![[Pasted image 20250925213226.png]]
**一、Charles使用30分钟自动关闭解决方法**
点击点击help的第一个选项 Enter Charles License
==Registered Name:== https://zhile.io
==License Key:== 48891cf209c6d32bf4
![[Pasted image 20250925213936.png]]
**二、HTTP抓包**
1. 查看电脑ip地址![[Pasted image 20250925214631.png]]
2. 设置手机HTTP代理
手机连接上电脑，设置->无线局域网->连接的wifi，设置HTTP代理
端口：8888
![[Pasted image 20250925224105.png]]
3. 设置后，在电脑上打开charles进行抓包：
手机上打开某个app或者浏览器的网址，点击“allow”，出现手机的http请求列表
![[Pasted image 20250925224436.png]]
![[Pasted image 20250925224534.png]]
**三、HTTPS抓包**
HTTPS抓包是在HTTP的基础上：
- 安装SSL证书到手机：

-点击 Help->SSL Proxying ->Install Charles Root Certificate on a Mobile Device
![[Pasted image 20250925225553.png]]
出现弹窗得到地址：
![[Pasted image 20250925225738.png]]