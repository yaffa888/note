## 1.下载Flutter
&nbsp;&nbsp;&nbsp;`git clone https://github.com/flutter/flutter.git -b stable`

## 2.更新环境变量
&nbsp;&nbsp;&nbsp;`pwd`&nbsp;--查看当前文件的目录<br>
&nbsp;&nbsp;&nbsp;`vim ~/.zshrc`&nbsp;--编辑环境变量配置文件<br>
&nbsp;&nbsp;&nbsp;`export PATH="$PATH:[PATH_OF_FLUTTER_GIT_DIRECTORY]/bin"`&nbsp;--在`.zshrc`文件中增加这一环节变量<br>
&nbsp;&nbsp;&nbsp;`source ~/.bash_profile`&nbsp;刷新当前命令行窗口<br>
&nbsp;&nbsp;&nbsp;`echo $PATH` &nbsp;--查看当前文件的目录<br>
&nbsp;&nbsp;&nbsp;`which flutter`&nbsp;--验证 flutter 命令是否可用<br>
## 3.下载Xcode和Android Studio软件
&nbsp;&nbsp;&nbsp;运行`flutter doctor`检查是否都安装成功，出现错误可以根据提示修复