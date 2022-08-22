## 1，安装shadowsocks客户端<br>
&nbsp;&nbsp;&nbsp;下载地址 [https://github.com/shadowsocks/ShadowsocksX-NG/releases](https://github.com/shadowsocks/ShadowsocksX-NG/releases)<br/>
## 2，购买服务器<br>
&nbsp;&nbsp;&nbsp;建议网站 [https://www.vultr.com/](https://www.vultr.com/),$6一个月<br/>
&nbsp;&nbsp;&nbsp;大概配置如下<br>
![image](/Shadowsocks/image/1.png)<br>
&nbsp;&nbsp;&nbsp;成功后可以用终端ping下IP,看是否稳定，如果一直访问超时，建议停到这个再选一个<br>
&nbsp;&nbsp;&nbsp;`ping 你的IP`<br>
## 3，配置docker启动服务器<br>
&nbsp;&nbsp;&nbsp;1，登录你的服务器，提示需要输入的密码可复制购买的服务器中配置上的密码<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`ssh root@你的IP`
&nbsp;&nbsp;&nbsp;2，创建一个文件，文件名随意<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`mkdir docker-server`<br>
&nbsp;&nbsp;&nbsp;3，进入刚刚创建的文件,并创建一个docker-compose.yml<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`cd docker-server`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`touch docker-compose.yml`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`vim docker-compose.yml`<br>
&nbsp;&nbsp;&nbsp;4，复制下面的内容后保存并退出,这里的密码是用在shadowsocks客户端的，改成自己容易记的就行<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`version: '3'`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`services:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`  ss:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`    image: shadowsocks/shadowsocks-libev`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`    restart: always`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`    command: ss-server -s 0.0.0.0 -p 8080 -k 密码 -m aes-256-gcm -u`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`    ports:`<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`     - "10813:8080"`<br>
&nbsp;&nbsp;&nbsp;5，执行<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`apt install docker-compose`<br>
&nbsp;&nbsp;&nbsp;6，启动服务<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`docker-compose up -d`<br>

## 4，Shadowsocks客户端的配置<br>
&nbsp;&nbsp;&nbsp;找到服务器设置，地址就是你买的IP，密码是你在docker—compose.yml 设置的密码，这里的端口和加密方式都是参考这个文件<br>
![image](/Shadowsocks/image/2.png)<br>
## 5，到这里说明你已经翻墙成功了<br>
&nbsp;&nbsp;&nbsp;Shadowsocks可以多人使用，也有手机版的，接下来就用[www.google.com](www.google.com) 验证一下吧<br>