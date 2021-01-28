# 使用nativefier把网站打包成应用程序

## 01.安装node.js

首先需要安装Node.js，最新版本默认集成了npm，进入官网下载并安装到计算机。下载地址：https://nodejs.org/zh-cn/

![只需一行代码快速将网站打包成桌面程序 – Nativefier](https://www.smbinn.com/wp-content/uploads/2020/12/02-tuya.jpg)![只需一行代码快速将网站打包成桌面程序 – Nativefier](https://www.smbinn.com/wp-content/uploads/2020/12/03-tuya.jpg)

直接next就好!





## 02.配置环境变量

安装好 Node.js 之后，还需要设置全局变量，因为加载极为缓慢，这里我们使用淘宝源来进行操作会快上不少。找到系统属性 – 高级 – 环境变量 – 新建用户变量。变量名：ELECTRON_MIRROR  变量值：http://npm.taobao.org/mirrors/electron/![只需一行代码快速将网站打包成桌面程序 – Nativefier](https://www.smbinn.com/wp-content/uploads/2020/12/04-tuya.jpg)

安装完之后可以通过下面命令查看是否安装成功

node -v   查看node.js版本

npm -v    查看npm版本





## 03.安装nativefier

只需在cmd命令提示符中输入 npm install  nativefier  -g即可完成安装。![只需一行代码快速将网站打包成桌面程序 – Nativefier](https://www.smbinn.com/wp-content/uploads/2020/12/05-tuya.jpg)

安装完成后使用nativefier 命令查看是否安装成功





## 04.把网站打包成应用程序

例:nativefier "www.baidu.com"    打包好的应用程序会生成在你执行命令的目录下, 找到.exe文件双击打开

也可以自己命名:

nativefier --name "自己起名字"  "url"   

注:第一次打包的时候他会自己下在一个electron的依赖  下载的时间会比较长  请耐心等待!





## 05.nativefier详细配置

```javascript
nativefier –-name “blog” “https://www.leixuesong.cn/”

nativefier –icon <path>：设置图标
icon参数 
Windows环境下为.ico文件
Linux下为.png
Mac下 icon参数可以是a .icns或.png文件

--app-copyright ：应用的版权信息

-p, --platform <value>：指定输出不同系统的应用，可选参数linux、windows、osx。

-m, –show-menu-bar：指定是否应该显示菜单栏。

--disable-context-menu：禁用上下文菜单

--disable-dev-tools:停用Chrome开发者工具

--clear-cache:防止应用程序在两次启动之间保留缓存。

--tray:托盘,防止用户点击右上角关闭按钮后直接关闭程序，而是缩小到右下角的托盘中。

--always-on-top：总是在最前面显示。

--maximize：开始的时候最大化。

--full-screen：使打包的应用全屏启动。

--app-version <value>：应用程序的发行版本。

–width <value>：打包应用程序的宽度，默认为1280px。

–height <value>：打包应用程序的高度，默认为800px。

–min-width <value>：打包应用程序的最小宽度，默认为0。

–min-height <value>：打包应用程序的最小高度，默认为0。

–max-width <value>：打包应用程序的最大宽度，默认为无限制。

–max-height <value>：打包应用程序的最大高度，默认为无限制。

–x <value>：打包的应用程序窗口的X位置。

–y <value>：打包的应用程序窗口的Y位置。

-a, --arch <value> 处理器架构

示例：

 nativefier  
	--arch "x64" 
	--platform "windows" 
	--icon D:\temp\favicon.ico //一定要有图片，不然会报错
	--name "weixin" 
	"https://mp.weixin.qq.com/" //网站地址
	--maximize	//开始最大化
	--always-on-top //最前端显示
	--clear-cache  //防止缓存
	--app-copyright "在这里填自己的就行了，也没找到在哪里显示"
	--app-version 1  //这里好像只能填数字，不过也没啥用，没找到在哪里显示
	--show-menu-bar //英文的，感觉没啥用，还挺丑
	--disable-dev-tools
	--tray //比较有用的
	D:\temp\  //最后指定文件的输出目录
	
	//还有就是不能按上面的这样子，因为cmd不能换行执行一句，会出错...
	
	nativefier --arch "x64" --platform "windows" --icon D:\temp\favicon.ico --name "weixin" "https://mp.weixin.qq.com/" --maximize --app-copyright "微信公众号" --app-version 1 --show-menu-bar --disable-dev-tools --tray D:\temp\
```