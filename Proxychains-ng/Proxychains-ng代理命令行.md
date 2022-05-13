## 下载<br>
`brew install proxychains-ng`<br>
## 使用 proxychains-ng 进行代理，例如 git clone<br>
`procychains4 git clone https://github.com/facebook/react.git`<br>
##编辑 proxychains.conf 文件，将代理加入 [ProxyList] 中。例如：<br>
```
[ProxyList]
socks5  127.0.0.1 1234
http    127.0.0.1 4321
```
## 编辑终端的 rc 文件（例如 .zshrc），添加 proxuchains4 的 alias：<br>
`alias pc="proxychains4"`<br>
## 退出保存，执行 source .zshrc 使别名生效。之后你就可以这样使用 procychains4:<br>
`pc git clone https://github.com/facebook/react.git`<br>