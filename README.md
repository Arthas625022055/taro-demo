# taro-demo
## 简介
👽 Taro['tɑ:roʊ]，泰罗·奥特曼，宇宙警备队总教官，实力最强的奥特曼。

Taro 是一套遵循 React 语法规范的 多端开发 解决方案。现如今市面上端的形态多种多样，Web、React-Native、微信小程序等各种端大行其道，当业务要求同时在不同的端都要求有所表现的时候，针对不同的端去编写多套代码的成本显然非常高，这时候只编写一套代码就能够适配到多端的能力就显得极为需要。

使用 Taro，我们可以只书写一套代码，再通过 Taro 的编译工具，将源代码分别编译出可以在不同端（微信/百度/支付宝/头条小程序、H5、React-Native 等）运行的代码。

### 1.微信小程序转多端踩坑
 
转换原有微信小程序应用非常简单，只需要安装 Taro 命令行工具，定位到待转项目根目录，运行命令：

    taro convert

即可完成转换。转换后的代码保存在根目录下的 taroConvert 文件夹下。你需要定位到 taroConvert 目录执行 npm install 命令之后就可以使用 taro build 命令编译到对应平台的代码。

#### 第一道坑
   
   打点的url拼接，.jpg字符串的赋值会被当做图片处理，然后路径找不到，直接报错。解决方式：字符串赋值去掉字符串后缀

   npm install 之后使用taro build 命令编译成h5

 	npm install
	taro build --type h5 --watch

#### 第二道坑
   
   1.commonJS规范和es6规范的问题
   export 的报错, 部分module.exports会报错，改成export

   2.部分组件还没有，会直接导致报错，例如cover-view
   		
